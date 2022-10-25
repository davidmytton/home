---
title: "Choosing a non-relational database; why we migrated from MySQL to MongoDB"
date: 2009-06-25
modified: 2009-06-25
draft: false
tags: ["Server Density Archive"]
url: choosing-a-non-relational-database-why-we-migrated-from-mysql-to-mongodb
---

_Originally [published on the Server Density
blog](https://blog.serverdensity.com/choosing-a-non-relational-database-why-we-migrated-from-mysql-to-mongodb/)._

**Update 23 Oct 2010**: [A discussion about the value of shortened field
names](http://ayende.com/Blog/archive/2010/10/22/you-saved-5-cents-and-your-code-is-not-readable.aspx)
has generated a lot of traffic to this post over the last 24 hours. [A response
has been posted
here](http://blog.boxedice.com/2010/10/23/on-shortened-field-names-in-mongodb/).

**Update 28 Feb 2010**: A followup was
published [here](http://blog.boxedice.com/2010/02/28/notes-from-a-production-mongodb-deployment/).

Until recently, our [server monitoring application, Server
Density](https://www.serverdensity.com/), was running using MySQL for the
backend. Although we primarily provide it as a hosted service, it has been
written to work as a standalone application for customers that wish to install
on their own servers. This means each customer had their own MySQL database.

We collect a lot of data – the monitoring agent reports back every 60 seconds
and includes various statistics, of which the server snapshot has the most data
(because it is collecting details on every running process). Over time, this
results in millions of rows in the database, even for just 1 month of data, per
server monitored.

Despite this huge amount of data, performance was not a problem. We were able to
tune our queries and servers to ensure that results were returned quickly. The
majority of queries are inserts with a minimal number of reads. We are also not
doing any caching, yet. Once we reach that stage in our scaling plan there will
be even fewer reads directly from the DB because the latest metric values will
be stored in memory.

The problem we encountered was administrative. We wanted to scale using
replication but found that MySQL had a hard time keeping up, especially with the
initial sync. As such, backups became an issue, but [we solved
that](http://blog.boxedice.com/2009/06/14/backing-up-large-mysql-databases/).
However, scaling MySQL onto multiple clustered servers as we plan to do in the
future is difficult. You either do this through replication but that is only
really suited to read-heavy applications; or using MySQL cluster. The cluster
looks very good but I have read about some problems with it and was unsure of
it’s suitability for our needs.

The current fashion is using key/value stores, also known as non-relational
database management systems (non-RDBMS) or schema-less databases. As such I did
some research into the options available.

## The different options

Our requirements were a relatively stable product with a decent access
interface, persistent disk based storage (many are in-memory only), a good
community and some documentation. Based on that, the projects I reviewed were:

- [Cassandra](https://wiki.apache.org/cassandra/)
- [CouchDB](https://couchdb.apache.org/)
- [Hypertable](http://www.hypertable.org/)
- [MongoDB](https://www.mongodb.org/)
- [Tokyo Cabinet](http://tokyocabinet.sourceforge.net/)
- [Project Voldemort](http://project-voldemort.com/)

There
are [several](http://www.metabrew.com/article/anti-rdbms-a-list-of-distributed-key-value-stores/) [good](http://randomfoo.net/2009/04/20/some-notes-on-distributed-key-stores) [blog](https://bcbio.wordpress.com/2009/05/10/evaluating-key-value-and-document-stores-for-short-read-data/) posts
around that go into more detail for each project.

I did not consider “cloud” databases such as [Amazon
SimpleDB](https://aws.amazon.com/simpledb/) because I thought the latency would
be too high.

## Why we chose MongoDB

I tested most of these with real data and eventually
chose [MongoDB](https://www.mongodb.org/) for a number of reasons:

- [Very easy to
  install](https://www.mongodb.org/display/DOCS/Getting+Started).
- PHP [module](http://www.php.net/mongo) [available](https://www.mongodb.org/display/DOCS/PHP+Language+Center).
- Very easy [replication](https://www.mongodb.org/display/DOCS/Replication),
  including [master-master](https://www.mongodb.org/display/DOCS/Master+Master+Replication) support.
  In testing this caught up with our live DB very quickly and stayed in sync
  without difficulty.
- Automated [sharding](https://www.mongodb.org/display/DOCS/Sharding+Internals) being
  developed.
- Good documentation.

## Implementation details

Switching from relational to non-relational is time consuming but it is not
difficult. That said, there are differences that you won’t necessarily be
expecting. Some of these are specific to MongoDB but some will apply generally
too:

### Schema-less

This means things are much more flexible for future structure changes but it
also means that every row records the field names. We had relatively long,
descriptive names in MySQL such as timeAdded or valueCached. For a small number
of rows, this extra storage only amounts to a few bytes per row, but when you
have 10 million rows, each with maybe 100 bytes of field names, then you quickly
eat up disk space unnecessarily. 100 \* 10,000,000 = ~900MB just for field names!

We cut down the names to 2-3 characters. This is a little more confusing in the
code but the disk storage savings are worth it. And if you use sensible names
then it isn’t that bad e.g. timeAdded -> tA. A reduction to about 15 bytes per
row at 10,000,000 rows means ~140MB for field names – a massive saving.

### The database-per-customer method doesn’t work

MongoDB stores data in flat files using their own [binary storage
objects](https://www.mongodb.org/display/DOCS/BSON). This means that data
storage is very compact and efficient, perfect for high data volumes. However,
it allocates a set of files per database and pre-allocates those files on the
filesystem for speed:

> Each datafile is preallocated to a given size. (This is done to prevent file
> system fragmentation, among other reasons.) The first file for a database is
> .0, then .1, etc. .0 will be 64MB, .1 128MB, etc., up to 2GB. Once the files
> reach 2GB in size, each successive file is also 2GB.
>
> Thus if the last datafile present is say, 1GB, that file might be 90% empty if
> it was recently reached.

This was a problem because MongoDB was frequently pre-allocating in advance when
the data would almost never need to “flow” into another file, or only a tiny
amount of another file. This is particularly the case with free accounts where
we clear out data after a month. Such pre-allocation caused large amounts of
disk space to be used up.

We therefore changed our data structure so that we had a single DB, thus making
the most efficient use of the available storage. There is no performance hit for
doing this because the files are split out, unlike MySQL which uses a single
file per table.

### Unexpected locking and blocking

In MongoDB, [removing rows locks and blocks the entire
database](https://groups.google.com/group/mongodb-user/browse_thread/thread/810f410f1c997a52).
Adding indexes also does the same. When we imported our data, this was causing
problems because large data sets were causing the locks to exist for some time
until the indexing had completed. This is a not a problem when you first create
the “collection” (tables in MySQL) because there are only a few (or no) rows,
but creating indexes later will cause problems.

Previously in MySQL we would delete rows by using a wide ranging WHERE clause,
for example to delete rows by date range or server ID. Now in MongoDB we have to
loop through all the rows and delete them individually. This is slower, but it
prevents the locking issue.

### Corruption

In MySQL if a database (more likely a few tables) become corrupt, you can repair
them individually. In MongoDB, you have to repair on a database level. There is
a command to do this but it reads all the data and re-writes it to a new set of
files. This means all data is checked and means you will probably have some disk
space freed up as files are compacted but it also means the entire database is
locked and blocked during the time it takes. With our database being around
60GB, this operation takes several hours.

Corruption will only really occur if you kill the database process whilst it is
in the middle of an operation.

## Performance

Our reasons for moving to MongoDB were not performance, however it has turned
out that in many cases, query times are significantly faster than with MySQL.
This is because MongoDB stores as much data in RAM as possible and so it becomes
as fast as using something like memcached for the cached data. Even non-cached
data is very fast.

We don’t have any precise numbers but in some cases are seeing cached query
times around 7ms and non-cached around 50-200ms, depending on the query. Indexes
help speed up queries in many cases but where our data is write intensive,
indexes can slow things down.

Having a native C PHP module also helps with performance and means that all
interactions are optimised at the code level. [Other drivers are
available](https://www.mongodb.org/display/DOCS/Drivers) for Python, Java, Ruby,
C++ and Perl.

## Community / commercial support

MongoDB is open source but is developed by a New York
company, [10gen](https://www.10gen.com/). This is useful because we can be sure
that development will continue and bugs fixed. Indeed, [the mailing
list](https://groups.google.com/group/mongodb-user/) has been a very useful
source of help for us during the migration. The documentation is good but some
things are still unclear or not documented and being able to get a response from
the mailing list from the developers within hours is very helpful.

MongoDB is quite a new project compared to the likes of MySQL and so there are
fewer experienced people in the community. As such, we have also taken up a
support contract with 10gen for guaranteed 24/7 phone & e-mail coverage so that
should we have a problem, we will be able to get help quickly.

## Test, and choose what is right for your application

[The guys at Friendfeed are using
MySQL](https://bret.appspot.com/entry/how-friendfeed-uses-mysql) and they have a
lot more data than us. However, they use it like a key/value store and have a
different access ratio. Every application is different. Whilst MySQL is suitable
for Friendfeed, we found a better solution. You need to test each one to
discover its suitability for your needs.

Indeed, whilst Server Density is now running entirely on MongoDB, our accounts
system, invoicing and billing remains on MySQL. [MongoDB is
non-atomic](https://www.mongodb.org/display/DOCS/Use+Cases). This doesn’t matter
for our general application code – it’s not critical if a few rows do not get
written – however this is not the same for our billing system. We use
transactions to ensure everything runs correctly (e.g. we don’t bill customers
twice) and so are still using MySQL InnoDB for that.

Our move to MongoDB has been interesting and we have encountered problems, but
nothing that we were unable to work around. Performance has increased, our disk
usage has decreased and we are now in a much better position to continue our
scaling plans.
