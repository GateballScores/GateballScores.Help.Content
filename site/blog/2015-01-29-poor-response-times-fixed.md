---
title: Poor Response Times Fixed
authors: 
- name: Tim Murphy
  email: tim@26tp.com
---
Like so many program bugs the error was quite silly and easy to fix once spotted.

Many thanks to John Yarrall who reported the site was hanging when selecting 8-12 Handicap competition in the [WA GC Summer Nights Doubles](https://croquetscores.com/2015/gc/wa-summer-nights-doubles) tournament. This tournament is a teams event.

My first mistake with teams event is it allows managers to record games where the same team play each other - but this wasn't directly bringing down the site. What was bringing down the site was the program got into an infinite loop when viewing the results.

So there are two fixes to implement:

- Avoid the infinite loop when displaying results and advise the visitor to contact the tournament manager of the problem. This has been implemented and installed.
- Stop tournament managers from entering these bad results. I'll look to implement this tomorrow.

Next week I'll write a report to find any of these bad results and advise the relevant tournament managers. It might explain the high CPU usage earlier this month.

Finally I'd also like to thank Michael Wright for offering to help with a code review. While I didn't need to call on his services I do appreciate the offer.
