---
layout: default
title: Week 5
---
# **January Week 5**
## **Friday: Februrary 2**
- 9:30  AM: Signed in.
- 10:30 AM: Strategy for: Issue with move controls when component is too small in Modular.
- 11:30 AM: Debugging session for issue () with sir. (**#167**)
- 12:00 AM: Done with the code review call for **PR #172**
- 1:50  PM: Function `removePartitions()` refactored. (**#43**)
- 3:00  PM: Still trying to fix the dropdown issue. No luck. (**#167**)
- 3:40  PM: Added a comment in `Box.js` and submitted the PR for final review. Will fix the `object:removed` listener later on.
- 4:00  PM: **PR 187** Submitted. Addressing `Error while saving a wardrobe with door type to Pooja.`
- 5:00  PM: Tested `beta.emptycup3d.com` and found 2 critical bugs. Reported to sir.
- 6:30  PM: Working on Issue **#75**, as I interpreted it wrongly ;(
- 7:00  PM: Why the feature `removePartitions()` is not working in AB sir's system ;(
- **SIGNED OUT**

## **Thursday: Februrary 1**
- 9:35  AM: Signed in.
- 11:00 AM: Attaching the `selected` event listener to the canvas object but never removing it, causing errors in `Partition.js`. I think I should remove the delete key listener on `deselected`.
- 11:30 AM: **Fixed:** Once a partition is selected, the delete keylistener is binded to it forever and thereby calling the `removePartition()` even when a different `co` is selected.
- 12:15 PM: **Fixed:**: After removing all the partitions, the cupboard is not scalable. Commit done. **PR #172** updated.
- 2:00  PM: Code refactored. **PR #172** updated.
- 3:15  PM: **Fixed**: Toggle issue in Walk in/ Top view in 3D page. (**#159**). **PR #175** Submitted.
- 5:00  PM: Figuring out the strategy to fix : `Move control in accessible when component in Modular page is too small.`
- 7:00  PM: Stuck on `Modular woodowork section settings menu doesn't disappear on section change.`
- 9:30  PM: I think the `_setControl` inside `showSettings()` is setting the display of the settings icon to `inline` and at the same time it should set the display of the `<ul>` element to `none`, but the catch is - The ul element ( that contains the dropdown ),
It is not accessible outside of `onMenuSelect.set()` through jQuery, even though it is visible on every mouse move / hover.
 
## **Wednesday: January 31**
- 9:25  AM: Signed in.
- 10:00 AM: Pulled the `furnishings` branch and checked a deployment issue with sir, on one of the api containers.
- 11:30 AM: How the partition gets highlighted with red color when it is clicked ? (**#43**)
- 12:30 PM: Stuck ! (**#43**)
- 2:00  PM: Registered the delete key press when a partition is selected. (**#43**)
- 3:00  PM: Able to remove the partition but only when a new partition is added. (**#43**)
- 4:00  PM: `p.remove()` is not removing the partition from the array `b._partitions`. Why is that ?
- 4:30  PM: Called the `render()` method on the UI because the partitions were being updated on delete keypress but were not rendered.
- 5:30  PM: Partition should not be removed if the adjacent sections are of different type. But how these partitions are associated with the corresponding section ?
- 7:30  PM: Implemented the code for: `Partitions that "support" other partitions should not be removable`. (**#43**)
- 10:30 PM: Submitted **PR #172**. Signed out.

## **Tuesday: January 30**
- 9:20  AM: Signed in.
- 10:00 AM: Updated the logic for issue(**#57**). Commited changes. PR(**#88**) updated.
- 11:00 AM: Removed all the commits from the `uv-scaling` branch, rebased with the latest master again, made new commit with the backup code added. Force pushed. PR updated. `uv-scaling` is now in sync with `master`.
- 12:00 PM: **New features (#57 + #56) merged in master ** by sir. Created new branch `rm-partitions`, before I could start with the issues in backlog, I found a new bug in the `Walkin/ Top view` toggler in 3D page. Created the issue, added to issue tracker and Alpha.
- 12:40 PM: **Found** 3 new bugs in `ModularUI`, reported to sir.
- 1:30  PM: **Fixed** 2 old bugs that were already fixed in Modular UI but seems like due to some kind of code migration they were alive again (Door icon was not getting hidden when moving box && Control icons were not being hidden when editing mode enabled (pencil activated)).
- 2:30  PM: **Fixed**: The move controls and icons are still visible after selecting anything from menu (Without moving the mouse).
- 3:00  PM: Pending: Are we supposed to remove split controls if Door Type is Full glass or Door mirror is something ?
- 3:30  PM: Submitted **PR #164** incorporating 4 bug fixes in modular UI.
- 4:30  PM: Developed a broad idea on how to implement support for removing partitions in Modular UI.
- 5:30  PM: Discussed the implementation of (**#43**) on a call.
- 7:00  PM: Resolved merge conflicts in PR.
- 8:00  PM: Found the `remove()` method in Partition but how to request a partition delete from UI ?
- 9:00  PM: `BoxRenderer.js` contains `PartitionRenderer` which calls `partition.remove()` on an event, but that event is never triggered. Additionally, how to display the remove controls to remove a partition ? Signed out.
  
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
