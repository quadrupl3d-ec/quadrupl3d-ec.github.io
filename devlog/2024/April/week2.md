---
layout: default
title: Week 15
---

# **April Week 2**
## **Saturday: April 13**
- 9:30  AM: Signed In.
- 11:30 PM: **PR #663** Submitted. **Fixed:** show trash icon in edit mode (ModularUI).
- 12:30 PM: **PR 664** Submitted. **Fixed:** Persisting handleType in all possible cases + refactor.

## **Friday: April 12**
- 9:30  AM: Signed In.
- 1:00  PM: Confused.
- 7:30  PM: Had the encounter with the `Bug of the month`. Bug is tied to Undo manager.

## **Thursday: April 11**
- 9:30  AM: Signed In.
- 12:00 PM: Enabled `handleType` options for section types = basket/tandom/bottle-unit
- 1:00  PM: Stuck badly.
- 2:00  PM: Tested and **Fixed:** handleType options enabled for kitchen. Submitted **PR #650** to `release`.
- 3:15  PM: Who is using the `hotspot-entrance` from `layoutPlanner`? Why the hotspot is broken for first person?
- 6:00  PM: Starting up again with `Hotspot for initializing first person is broken`.
- 9:30  PM: **PR #653** Submitted to release. **Fixed:** Hotspot for initializing first person is broken.

## **Wednesday: April 10**
- 9:30  AM: Signed In.
- 11:00 AM: Updated **PR #636**. Section already has the `getHandleType()` method.  
- 1:10  PM: Done with the meeting about `Implemented: Apply channel selection to entire woodwork`.
- 3:00  PM: Clearing up the stale, coming up with new set of points on how to implement `Apply channel selection to entire woodwork`
- 6:00  PM: Able to set the `handleType` to all the sections in the box. Updating **PR #643**.
- 8:00  PM: **PR #643** Submitted and merged into `release`.

## **Tuesday: April 9**
- 9:30  AM: Signed In.
- 11:00 AM: Got the `.blend` file from beta-render-worker for `76-gbr`. Testing for daylighting in case of less opening area.
- 12:30 PM: Shortlisted daylight rendering parameters for making the render more realistic, visually appealing, brighter. 
- 2:00  PM: Got the `.blend` file of `76-dining` from render worker. Tuning the filtered parameters.
- 3:30  PM: Finalized parameters for daylight renders.
- 5:45  PM: Submitted **PR #636**. **Fixed:** Improve day light renders.
- 7:40  PM: **PR #637** Submitted. **Fixed:** Remember channel selection.

## **Monday: April 8**
- 9:30  AM: Signed In.
- 11:00 AM: Trying to get the `.blend` file from the beta render worker but seems like it is getting removed even if the `clean_up` is removed from `render_worker_startup.sh`
- 12:00 PM: Using the local frontend and cloud backend. `debug = True` will result in presisting the render folder in the VM. Got the `.blend` file. Started testing for day light renders.
- 1:00  PM: Able to move the mouse freely. Pressing `Shift + ~` together to activate fly mode. Using `W S A D` to move the camera as if in a game. Can use the mouse scroll to increase/decrease the camera move speed.
- 4:30  PM: Done with the `tuning-renders` call with Ab sir.
- 5:00  PM: **Fixed: **Not able to scale or move a component in modularUI after undo.
- 7:30  PM: Tuning renders with different parameters through blender GUI.
- 9:00  PM: Got 22 daylight renders in 1080p with different parameters.
