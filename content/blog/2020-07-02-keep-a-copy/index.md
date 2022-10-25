---
title: "Keep a copy"
date: 2020-07-02
modified: 2020-07-02
draft: false
tags: ["Privacy"]
summary: "The world has moved to a rental model - access is cheaper and content 
available on demand. But what happens to your data when you get locked out, 
stop paying or the service goes down? Better to keep a copy and work locally."
url: keep-a-copy
---

A few weeks ago I went to check the latest updates in my RSS feed
reader, [Feedbin](https://davidmytton.blog/feedbin.com), and it was down. I
searched on Twitter and found a lot of people complaining, so it wasn’t just me.
I couldn’t read any of my subscriptions.

Feedbin is a great service. It is usually reliable, fast, run by an independent
company, can receive email newsletters, lets me save web pages, and [respects
privacy](https://feedbin.com/blog/2018/09/11/private-by-default/). It allows me
to read all the blogs I subscribe to as well as following specific people on
Twitter, because [I don’t use any official Twitter
client](https://davidmytton.blog/a-healthy-reading-diet-removing-the-junk/).

However, it is a SaaS product. I use their web browser client and everything is
hosted on the Feedbin servers. If they’re down, I can’t access anything.

I don’t want to build my own version – replicating all the Feedbin features
would be a waste of my time. I also don’t want to host an open source RSS feed
server. The features wouldn’t match, but I also don’t want the hassle of running
a server. Same as I use Office365 because don’t want to run my own email or file
server. Microsoft does a better job at security, reliability, performance and
functionality than I ever could.

But nothing is available 100% of the time, services don’t last forever, and
there is always the risk of your account being locked out.

## Where is your data?

Compared to the old days of running software natively on your computer and
storing data on your local disk, we now access most things in the cloud.

If you use GMail, chances are you’re accessing your email from the web client.
IMAP / POP3 is not enabled by default so most people are unlikely to use a
native client like macOS Mail which stores all your messages locally.

If you use Google Docs, Sheets, Slides, there isn’t even an option to use a
desktop client.

If you use Apple Photos, the default option is to store all your images in
iCloud. It has an option to download everything locally but starts cloud-first.

What about your music? Most people have now switched to a streaming service,
either Spotify or Apple Music. You pay a monthly subscription to get access to
all the music in the world, but if you cancel the subscription then you lose
access to everything. Files are cached locally, but they are protected by DRM
and cannot be accessed from other clients, or if you cancel your subscription.

Kindle books are the same. They are stored on-device, but in a protected format
that cannot be read except in the Kindle client. When your Kindle runs out of
space, you must delete the older books. You can resync them on demand, but what
happens if your Amazon account is closed, or Amazon revokes access like it
did [with an edition of
1984](https://mashable.com/2009/07/17/amazon-kindle-1984/).

Video is even worse. YouTube is the defacto place for all video content, so it
would be a shame [if your content was
removed](https://www.theverge.com/2020/2/28/21157476/youtube-video-removal-appeal-takedown-community-guidelines-report),
or [your access blocked](https://en.wikipedia.org/wiki/Censorship_of_YouTube).

## Losing access

The world has moved to a “rental” model. In most cases, this is a positive
thing. Access is cheaper and available on demand. You no longer need to hoard
CDs, DVDs or books.

But what happens when something goes wrong?

What if your Google account is suspended, or hacked? All your files, emails,
calendar, todos, videos, photos would
be [unavailable](https://lifehacker.com/i-lost-nine-years-of-photos-by-locking-myself-out-of-my-1841178170).

What if Amazon closed your account? All your books would be inaccessible.

The big tech companies are [almost
unaccountable](https://davidmytton.blog/cloudflare-free-speech-and-the-rule-of-law/) and [lack
transparency](https://davidmytton.blog/sustainability-doesnt-work-without-transparency/) around
how they make decisions about accounts and content. They legitimately take down
a large volume of content, but there is inevitable collateral damage when
accounts are wrongly marked as suspicious.

This applies to any service where your data is in a proprietary format, only
located in the cloud, or the content is protected by DRM.

Ownership of content like video and books has always been a contentious issue.
Technically, you are only “licensing” a copyrighted version of the film you
watch, or book you read. But companies would not raid your house to take back
physical books, DVDs or CDs. Now, they can remotely revoke the license, or
suspend your account.

## Keep a copy

This doesn’t mean you should stop using those services, or switch to only buying
physical copies. It simply means its worth considering how you keep a copy of
your data.

Almost all these services allow you to export and download your data. For
example, [Google Takeout](https://takeout.google.com/) will export all your
files in standardised formats. [Apple lets you request a copy of all your
data](https://privacy.apple.com/), including your photos. Apps like Calendar and
Contacts on Mac let you export all your data to an archive format. And if you
are uploading videos and photos to YouTube or Instagram, you can keep copies of
the originals or export them from those services.

Like an album? Maybe buy a copy of your favourites (from the artist directly to
give them most revenue) and keep the audio files locally. [Spotify can still
find them](https://support.spotify.com/us/article/Listen-to-local-files/).

Digital content needs the equivalent of [legal
deposit](https://en.wikipedia.org/wiki/Legal_deposit), but until then you can do
it yourself. Don’t just rely on a single service. Direct everyone to YouTube,
but upload a copy to [Archive.org](https://archive.org/) – they support all
formats, from [audio](https://archive.org/details/audio) for podcasts
to [photos](https://archive.org/details/image) and [software](https://archive.org/details/software).
Always keep the originals.

## Work locally

If you store and work on a local copy of your files, you can continue even when
that service is down, if you are offline, or if there are any problems with your
account. It also means you can keep backups.

Have you ever looked inside the files that Google Drive creates if you run the
desktop client? They contain a single URL which directs your browser to the web
version. Non-Google formats are downloaded, but anything inside Docs, Sheets or
Slides is entirely in the cloud. This means you can’t back them up like normal
files.

It is better to work in open formats by default. Microsoft Office files can be
opened by [Libre Office](https://www.libreoffice.org/), Google Docs and Apple
Pages/Numbers. All the data is stored inside them, not on some cloud service.
Sometimes you need the superior collaboration functionality of Google Docs. In
that case, regularly downloading copies is sensible – Google downloads in Office
formats by default.

Even better, work in plain text. This was one of the main requirements [when I
was looking for a new note-taking
app](https://davidmytton.blog/the-best-note-taking-apps-for-mac-markdown-open-format-cross-platform/).
Plain text + Markdown means the files can be opened on any system by any app.

At least ensure the service can sync and cache locally. My new feed reading
setup involves using [Reeder](https://reederapp.com/), a local client which
supports syncing with Feedbin. I can still benefit from all the Feedbin
functionality but the app downloads all my updated subscriptions and caches them
locally. Feedbin supports exporting
to [OPML](https://en.wikipedia.org/wiki/OPML) so I can keep a backup of my
subscriptions, but I have now introduced some redundancy by using a local
client.

When selecting SaaS products, consider where the data is stored. Can you export
it easily? How easy it is to work with the exported files? Or better, can you
keep a copy locally whilst still benefiting from all the SaaS functionality?
