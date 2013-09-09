---
Title: "Why is server time running ahead/behind of my own?"
---

# Why is server time running ahead/behind of my own?

Our servers use [Coordinated Universal Time](http://en.wikipedia.org/wiki/Coordinated_Universal_Time) (UTC) as their time zone. This has several reasons.

First of all, UTC is the primary time standard by which the world regulates clocks and time.

It is also ideal for running server clocks because it doesn't have the incontinuities introduced by summer time where in spring, one hour is skipped, and in fall, one occurs twice in a row.

Running the internal clocks of our servers in UTC doesn't necessarily mean they also have to report time in that zime zone, though; we're free to chose every time zone we like. But which one? Both our team members and our customers are located in different time zones. And since almost everyone knows how many hours their local time is offset against UTC, we chose UTC as the best common denominator.
