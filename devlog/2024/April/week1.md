---
layout: default
title: Week 14
---

# **April Week 1**
## **Monday: April 1**
- 9:20  AM: Signed In.
- 10:00 AM: Trying to fix: `Scale and move woodworks not working in Modular after undo.` No luck.
- 12:00 PM: Still not able to figure out why woodwork furns are moving in wrong direction in production. X and Z axis 
- 12:45 PM: If the woodwork is rotated, the furnishing that will be added to the woodwork will also have that rotation incorporated by default and that is causing the problem I guess. So, 90 degree clockwise is interchanging the X and Z axes and so on.
- 3:00  PM: Got the orientation of the woodwork from layout definition and used the `comp.orientation` to rotate the axes object about Y axis, but this ain't helping!
- 5:30  PM: When a woodwork is rotated in the layout planner and then `_loadWoodworkSide()` is called in js/Walkin.js. This will use the angle from comp.orientation and pass it to rotateY(ww, comp.orientation). The rotateY function is in SceneUtils in helpers.js. This function will create a new rotation Matrix and will multiply it to the woodwork's matrix. Now this rotation is with respect to the woodwork, I tried some solutions from the internet to make the rotation absolute to the scene, but couldn't fix this!
- 7:00  PM: How to fix this????
- 8:30  PM: Submitted **PR 605**. **Fixed:** Shift Pointer is not working correctly for woodwork furnishings in some cases.
