---
layout: default
title: Week 4
---
# **January Week 5**
## **Tuesday: January 30**
- 9:20  AM: Signed in.
- 10:00 AM: Updated the logic for issue(**#57**). Commited changes. PR(**#88**) updated.
- 11:00 AM: Removed all the commits from the `uv-scaling` branch, rebased with the latest master again, made new commit with the backup code added. Force pushed. PR updated. `uv-scaling` is now in sync with `master`.
- 12:00 PM: **New features (#57 + #56) merged in master ** by sir. Created new branch `rm-partitions`, before I could start with the issues in backlog, I found a new bug in the `Walkin/ Top view` toggler in 3D page. Created the issue, added to issue tracker and Alpha.
- 12:40 PM: **Found** 3 new bugs in `ModularUI`, reported to sir.
- 1:30  PM: **Fixed** 2 old bugs that were already fixed in Modular UI but seems like due to some kind of code migration they were alive again (Door icon was not getting hidden when moving box && Control icons were not being hidden when editing mode enabled (pencil activated)).
- 2:30  PM: **Fixed**: The move controls and icons are still visible after selecting anything from menu (Without moving the mouse).
  
## **Monday: January 29**
- 9:20  AM Signed in.
- 10:30 AM Figuring out a way to make the existing sliders responsive. (#57)
- 11:30 AM: Done with the code review call, incorporating changes now (#57).
- 12:30 PM: Incorporated the changes stated by sir in review call (#57).
- 1:00  PM: Why the `resetSliders()` is called everytime a user sets UV scale ?
- 1:30  PM: Commit done. PR updated. Re-requested code review. (#57)
- 3:40  PM: Debugging session with sir + Code review of PR (**#56 + #57**)
- 5:00  PM: Done the changes but not able to set UV scale !!!! Stuck.
- 7:00  PM: Commit done. PR #88 updated. Still not able to bypass cyclic dependency and not able to implement the feature in correct way. (**#57**)
- 7:40  PM: Commit done. PR #84 updated. Changed the key to `Alt` and removed event listeners on `Brush.clean()`. (**#56**)
- 8:30  PM: Trying to figure out a way to bypass cyclic dependency in `MaterialPreview.svelte`.
- 9:00  PM: Done with the weekly review call. Signing out.
