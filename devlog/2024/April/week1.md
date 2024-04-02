---
layout: default
title: Week 14
---

# **April Week 1**
## **Tuesday: April 2**
- 9:30  AM: Signed In.
- 10:00 AM: Understood the request flow for updating/submitting GSTIN details.
- 12:00 PM: Tested the API Endpoint for SQL Injections to `/update_gst`. Used SQL map for almost all type of basic injection attacks. Used burp suite for manual testing through different payloads.
- 2:30  PM: Documented mitigation techniques for SQL Injection attacks. **PR 608** Submitted.
- 3:30  PM: Joined the meet for understanding how to debug renders in production.
- 6:20  PM: Done with the meeting. Now I'm able to SSH into production and debug render jobs.
## **Monday: April 1**
- 9:20  AM: Signed In.
- 10:00 AM: Trying to fix: `Scale and move woodworks not working in Modular after undo.` No luck.
- 12:00 PM: Still not able to figure out why woodwork furns are moving in wrong direction in production. X and Z axis 
- 12:45 PM: If the woodwork is rotated, the furnishing that will be added to the woodwork will also have that rotation incorporated by default and that is causing the problem I guess. So, 90 degree clockwise is interchanging the X and Z axes and so on.
- 3:00  PM: Got the orientation of the woodwork from layout definition and used the `comp.orientation` to rotate the axes object about Y axis, but this ain't helping!
- 5:30  PM: When a woodwork is rotated in the layout planner and then `_loadWoodworkSide()` is called in js/Walkin.js. This will use the angle from comp.orientation and pass it to rotateY(ww, comp.orientation). The rotateY function is in SceneUtils in helpers.js. This function will create a new rotation Matrix and will multiply it to the woodwork's matrix. Now this rotation is with respect to the woodwork, I tried some solutions from the internet to make the rotation absolute to the scene, but couldn't fix this!
- 7:00  PM: How to fix this????
- 8:30  PM: Submitted **PR 605**. **Fixed:** Shift Pointer is not working correctly for woodwork furnishings in some cases.
- 9:00  PM: onClick is updating the `moveby` coordinates if it is a woodwork furnishing object. Updated **PR 605**.
