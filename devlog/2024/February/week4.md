---
layout: default
title: Week 9
---

# **February Week 9**
## **Thursday: Februrary 29**
- 9:30  AM: Signed in.
- 10:30 AM: Blocked on some issues.
- 12:00 PM: Fixed a huge logic bug in `ShiftPointer`. Submitted `PR #366`
- 2:00  PM: Getting started with the mixpanel API and server-side tracking. (**#143**)

## **Wednesday: Februrary 28**
- 9:40  AM: Signed in.
- 10:40 AM: Added a column in the Render table, used database migration inside API container. (**#90**)
- 3:10  PM: **PR** Merged. Done with the refactoring call with sir on the `inaccurate-pointer` branch. Learned a lot of good refactoring techniques and naming conventions. (**#225**)
- 5:20  PM: Able to run the jobs container without using a separate superisord.conf file. Jobs container picks up the newjob but throws an error. Not able to get the `cfgp`, what's that ?
- 8:20  PM: **PR #364** Submitted. Implemented `Time-to-render` for preemptible jobs.

## **Tuesday: Februrary 27**
- 9:45  AM: Signed in.
- 11:00 AM: Not able to reproduce the issue - `Render status inconsistency when manager errors out`
- 12:00 PM: Stuck. Not able to get renders in development environment. Not able to use `eccli`, even after installing it.
- 1:30  PM: Working on Log cloud updates in emptycup.core.cloud now.
- 2:00  PM: Reboot time. Feeling burned out.
- 5:30  PM: At work now, starting with how to get renders on development environment.
- 8:30  PM: **Fixed:** Containerized render worker. (**#103**)
- 10:30 PM: Tried to run the container as a non-root (worker) user.
- 11:30 PM: Volume mapping in `docker-compose-dev.yml` is causing problems in ownership assignment to the non-root user. **PR #361** Submitted.

## **Monday: Februrary 26**
- 9:30  AM: Signed In.
- 10:30 AM: Done the changes. Review re-requested. **PR #326** Updated. (**#312**)
- 12:00 PM: Understood how render workers are setup in production. Why there is need to containerize `render-manager` ?
- 1:30  PM: Done with the code review call for **PR #230**. (**#225**)
- 3:00  PM: Refactoring ShiftPointer. Removing unnecessary code that makes it complex. (**#225**)
- 4:30  PM: Updated **PR #230**. Refactored `_computeTranslation(x, y)` and installed helper functions to make the code more readable. Worked on scope of transient variables. (**#225**)
- 5:15  PM: Fixed some wrong comments in _computeTranslation() function.
- 7:00  PM: Working out the strategy to work on `Add time to render row in DB.` (**#90**)
- 9:45  PM: Done with the weekly review call with manager and CTO.
