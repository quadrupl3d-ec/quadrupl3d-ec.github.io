---
layout: default
title: Week 7
---
# **February Week 2**
## **Monday: Februrary 12**
- 9:20  AM: Signed In.
- 11:00 AM: Confused. Using the debugger to analyse the bug more deeply.
- 12:30 PM: `onSave()` is resetting the opts. And by default `opts.doorType` is set to `undefined` because we can't set that to `double` always. The real bug lies in the way a woodwork is saved.
- 2:30  PM: If `opts.doorType` is `undefinded` and we try to set it to `double`. One bug gets fixed. But then, everytime `onSave()` is called, `opts.doorType` is again reset to `undefined`, which produces another bug. (**#255**)
