---
layout: default
title: Week 7
---

# **February Week 2**
## **Tuesday: Februrary 13**
- 9:40  AM: Signed In.
- 11:00 AM: Now subdropdowns are also positioned based on the screen height. Updated **PR #265**. Now refactoring the Code.
- 12:00 PM: Undo the changes when the `onLeave` handler is triggered. (**#240**)
- 1:00  PM: **Fixed:** Sometimes door menu is not visible in modular UI. Tested all possible cases, refactored the code. **PR #265** Updated. Going on for the next issue. (**#240**)

## **Monday: Februrary 12**
- 9:20  AM: Signed In.
- 11:00 AM: Confused. Using the debugger to analyse the bug more deeply.
- 12:30 PM: `onSave()` is resetting the opts. And by default `opts.doorType` is set to `undefined` because we can't set that to `double` always. The real bug lies in the way a woodwork is saved.
- 2:30  PM: If `opts.doorType` is `undefinded` and we try to set it to `double`. One bug gets fixed. But then, everytime `onSave()` is called, `opts.doorType` is again reset to `undefined`, which produces another bug. (**#255**).
- 4:00  PM: Done with the debugging call with sir, and got a high level overview about the issues I've to address in alpha and beta.
- 6:00  PM: Picking up the issue - `Sometimes door menu is not visible in modular UI` (**#240**)
- 7:30  PM: How to display the dropdown based on screen height ?
- 9:00  PM: **Fixed:** Sometimes door menu is not visible in modular UI (**#240**)
- 10:30 PM: Now refactored and submitted **PR #265**

