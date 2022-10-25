---
title: "Dead references"
date: 2020-07-20
modified: 2020-07-20
draft: false
tags: ["Writing"]
summary: "In researching and reading academic papers, even those published this 
year, I have encountered a major problem: dead references. What can we do 
about it?"
url: dead-references
---

Science is built on the work on others. This means researching numbers, methods,
and principles from previous articles, all which must be correctly referenced.
Without referencing, you risk making claims which cannot be substantiated, or
worse, being accused of plagiarism.

Academic course submissions are routinely run through analysis software to
detect unreferenced material. The rules of plagiarism are drilled into every
modern student, made even more important due to the ease of access of online
content, or cheating using paid essay-mills.

I am currently working on a meta-analysis paper which means I have had to read
lots of academic articles. It’s normal to flick back and forth between the main
text and a specific reference. This is like falling into a Wikipedia browsing
hole, but instead your browser tabs are filled with PDFs and journal articles to
come back to.

A few of these papers go back to 2007, which is a long time in computing
history. But even with papers that have been published this year, I have
encountered a major problem: dead references.

This is a solved problem in academic publishing. The [Digital Object
Identifier](https://www.doi.org/) (DOI) is used across more than 5,000
publishers whereby every published item is assigned a unique, permanent
identifier. A DOI is like a URL in that it points to a specific piece of
content, but unlike a URL it is guaranteed to always point to the authoritative
source. Indeed, a DOI redirects the user to that source — it doesn’t host any
content itself — but means that even if the publisher rearchitects their
systems, the DOI can be updated to always point to the correct location. There
are now [over 190 million unique
items](https://www.doi.org/factsheets/DOIKeyFacts.html) referenced since the
system went live in 2000.

“Publication” used to mean a permanent version made available with any changes
or corrections issued as a separate article, or edition. This is true for
academic publications and books, [but does not work like this for the rest of
the internet](https://www.w3.org/Provider/Style/URI). Websites regularly change.
Reports are taken down. Domains expire. [It has been
suggested](https://blogs.loc.gov/thesignal/2011/11/the-average-lifespan-of-a-webpage/) that
the average lifespan of a webpage ranges from
44, [75](https://doi.org/10.1109/2.901164) or 100 days. Ironically, one of the
sources referenced in that article has itself been taken offline.

This internet impermanence is recognised in referencing guidelines. [The Harvard
referencing
system](https://www.imperial.ac.uk/admin-services/library/learning-support/reference-management/harvard-style/your-reference-list/),
for example, requires non-DOI publications to include an “accessed” date. This
at least sets a reference time for when the material was viewed. But what are
readers supposed to do with that information?

## How do we address this?

Firstly, I suggest that authors use the “[save
it](https://web.archive.org/save/)” option of the [Internet Archive Wayback
Machine](https://web.archive.org/) to capture a copy of the referenced page.
Over 451 billion web pages have been saved in this way, and they are regularly
crawled after being saved for the first time. In the article itself the display
URL in the references can show the original URL, but the href location could
point to the Wayback Machine version. This would allow readers to go to the
current version but quickly reference the dated version if necessary.

Secondly, I suggest that academic journals require authors to supply a copy of
all reference material alongside the submitted article. I hope that the Internet
Archive remains available forever, but [they have faced repeated legal attacks
around copyright to the material they
publish](https://blog.archive.org/2020/06/01/four-commercial-publishers-filed-a-complaint-about-the-internet-archives-lending-of-digitized-books/). [You
can help support them in many
ways](https://blog.archive.org/2020/06/14/how-can-you-help-the-internet-archive/),
but we can’t rely on a single copy of reference material. Instead, this could at
least be stored by the article publisher, if not released as part of the
supplementary material that often accompanies papers.

Copyright regulations do not help this situation. The challenge with storing
(and potentially republishing) reference material is the licensing. Academic
publications are traditionally available only through subscription journals.
Open access is gaining popularity, and I aim to publish all my academic writing
under open access licenses, but this is not yet common practice. It is also
expensive. I was able to use the [Imperial College London Open Access
Fund](https://www.imperial.ac.uk/research-and-innovation/support-for-staff/scholarly-communication/open-access/applying-for-funding/),
otherwise I would have had to pay around £1,000 as a processing charge (payable
after acceptance, not like low-quality pay-for-publication journals).

That said, I would argue [the principle of
fair-use](https://www.copyright.gov/fair-use/more-info.html) applies to
re-publishing reference material and journals should do this as standard.

## What I am going to do

In the absence of any action from publishers, authors can [save to the Wayback
Machine](https://web.archive.org/save/) even if their references do not link to
it. This makes a copy ready for someone else to access in the future.

For every article I write, I am going to take a copy of the material for every
reference and then upload it to [a GitHub
repository](https://github.com/davidmytton?tab=repositories) for that paper (to
be made public once any embargo period ends). The repository will contain the
published version of the article and a copy of every reference. The
repository [will be archived to make it read
only](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-archiving-repositories),
I will upload a copy of it to [my Internet Archive
account](https://archive.org/details/@davidmytton), and [trigger a save as part
of the Software Heritage Archive](https://archive.softwareheritage.org/save/).

For WordPress users, you can automate this. I run the [LH Wayback Machine
plugin](https://wordpress.org/plugins/lh-wayback-machine/) which automatically
submits all WordPress content to the Internet Archive when content changes.

[Keeping a copy of everything
important](https://davidmytton.blog/keep-a-copy/) is a necessary step in the
ephemeral world of the internet. That doesn’t mean hoarding data ([like
e-mail](https://davidmytton.blog/email-is-not-a-good-database/)) but it doesn’t
take much to consider what might be relevant reference material in the future.

For more on this topic, have a listen to [this episode of the a16z podcast with
the founder of the Internet Archive](https://overcast.fm/+BlzHCz5RM).
