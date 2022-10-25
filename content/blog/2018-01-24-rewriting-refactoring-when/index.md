---
title: "Rewriting, refactoring, rearchitecting - when is the right time?"
date: 2018-01-24
modified: 2018-01-24
draft: false
tags: ["Startups"]
summary: "It's done when it's done simply doesn't work with any real product, 
but the balance of good enough is difficult to get right."
url: rewriting-refactoring-rearchitecting-when-is-the-right-time
---

With any product development, there's always a tension between perfection and
getting things released.

The engineering mindset is geared much more towards architectural, design and
implementation perfection. The phrase "it's done when it's done" is the ultimate
manifestation of this approach but that simply doesn't work with any real
product. Customers expect rapid bug fixes, regular iteration and ongoing
improvements.

It's difficult to get the balance between good engineering and "good enough" to
release. Bugs hurt the customer experience, creaky architecture can result in
poor performance or entire outages, and technical debt wears away at the
happiness of your engineering team. But there are some things which might
indicate you're spending too much time on the engineering!

- **Refactoring, rewriting or rearchitecting code as a project by itself.**
  The best time to refactor is when you're already touching the area of the
  codebase in question. Rewriting code delivers no customer benefit but takes
  up a lot of time, usually introducing new bugs as well. Major rewrite and
  replace is usually only justified once you've hit scale limitations but even
  then, taking a component based approach and delivering small changes sooner
  is better than a grand rewrite over months.
- **Investing time building for a scale you have not yet reached.** Code will
  usually last much longer than you expect and so unless you have
  instrumentation which is showing a customer (or on call) impact either now
  or imminently, this is probably not a good use of time.
- **Rewriting in a new language, or introducing a new language into an
  existing codebase.** Only dramatic changes in usage scope really warrant
  considering writing something in a language that isn't already part of your
  stack. Hitting a scaling limitation might be a reason e.g. shifting from
  Python to Go for a systems problem within a high performance environment may
  make sense, but the right consideration should be given to the ongoing
  maintenance cost . Who else on your team has experience with that language
  for the future? How are you going to maintain the technology? Who is
  responsible for updates? What happens if that team member leaves and you
  have bugs to fix?

Generally speaking, starting a new project or component is the time to consider
new technologies, languages, frameworks and approaches. Anything with the words
"rewrite" or "rearchitect" should be approached with extreme caution and scoped
within an existing project that will deliver customer benefits at the same time.
