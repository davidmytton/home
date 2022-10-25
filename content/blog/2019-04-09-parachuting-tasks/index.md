---
title: Parachuting tasks because available time is fixed
date: 2019-04-09
modified: 2019-04-09
draft: false
tags: ["Startups", "Company Culture"]
summary: "Available time does not change - you can't add more hours to the day. 
So why do we ignore this when planning work and progressing tasks, especially 
in engineering?"
url: parachuting-tasks-because-available-time-is-fixed
---

There are 24 hours in a day. [8 of those are the standard
length](http://www.todayifoundout.com/index.php/2011/05/why-a-typical-work-day-is-eight-hours-long/) of
the working day, of which [an even shorter
total](https://buffer.com/resources/optimal-work-time-how-long-should-we-work-every-day-the-science-of-mental-strength) make
up the time we can spend actually doing focused work.

The available time does not change. You might be able to develop a system to
increase the number of focus hours but you cannot increase the number of
available hours.

If you read that paragraph in isolation then it is an obvious fact. Of course
you can’t increase the available hours.

So why is this ignored when we’re actually planning work and progressing through
a task list?

An interrupt-driven culture whereby new tasks appear without reducing the pool
of tasks the team are expect to complete is something I see on a regular basis
across many companies.

This is especially prevalent in engineering teams. A sprint or development cycle
will begin with a set number of tasks, and then mid-cycle new tasks will be
dropped in due to critical bugs, customer complaints or other reasons. This
doesn’t necessarily have to be an issue – it becomes a problem when those tasks
are forced in without removing other tasks. The available time is the same but
suddenly there are now more things to do.

The results of this include:

- **Deadlines being missed** – the work still has to be done, it’s just there
  is now more of it than when the original time estimate was discussed.
  Without adjustment then it is inevitable that everything will now take more
  time.
- **Existing work taking longer than expected** – if a critical bug comes in
  that needs to be dealt with immediately, that will cause a context switch
  that has an impact on individual or team productivity.
- **Multiple teams being impacted** – the original work plan may have external
  dependencies from other teams e.g. a marketing campaign launch.
- **Requests for overtime** – the team may be expected to work longer and
  later, [despite this not actually correlating with
  productivity](https://www.economist.com/free-exchange/2014/12/09/proof-that-you-should-get-a-life).

At my company, Server Density, we eventually implemented a solution to this we
called “parachutes”.

- Development cycles were a fixed length.
- All the tasks to be completed were scoped in tickets each of a fixed length.
- Every member of the team had a known level of productivity i.e. how many
  tasks they could complete in a cycle.
- This gave us a total known capacity for the cycle, which allowed us to slot
  in the tickets that would be completed in the cycle.
- We discussed which tickets needed to be done for each cycle, with
  stakeholders across the business sponsoring the tickets they prioritised,
  everyone debating the priorities.
- As a result, each ticket had a priority relative to the other tickets in the
  cycle.
- If an unexpected task came in, it was first triaged to scope and size it.
  Once agreed that it needed to be dealt with urgently, the lowest priority
  ticket in the current cycle was “kicked out” and this new ticket
  “parachuted” in to replace it.

This resulted in knowing what we were sacrificing to get the new ticket solved,
with the stakeholders for the kicked-out ticket being involved in the discussion
about whether to parachute it. The cycle remained a fixed length and meant that
we had a good level of certainty about what was going to be completed and when.

Dropping a new task into an existing cycle always has a cost. If you don’t
acknowledge that time is fixed then the cost ends up being hidden under
overtime, surprise missed deadlines and frustration from supporting teams. It is
better to explicitly incur that cost in a defined way by sacrificing some other
known task than to keep it hidden behind a bad process.

Parachuting tasks is always frustrating, especially for the owners of the kicked
out ticket. But the key is visibility and shared decision-making. Without this,
teams continue to maintain a fiction that everything will still be completed on
time with the same effort, until it isn’t. That’s significantly more
frustrating.
