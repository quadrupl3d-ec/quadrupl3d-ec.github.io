---
layout: default
title: Week 7
---

# **February Week 2**
## **Thursday: Februrary 15**
- 9:20  AM: Signed In.
- 11:00 AM:
- 12:30 PM:
- 2:00  PM:
- 3:00  PM:
- 4:00  PM: faceIndex = 0 wasted my 1 hour, There is not way to filter out wall specific meshes from the scene.
- 5:00  PM: Able to snap the furnishing to the original position and walls. But the snapping have glitches, movement is not smooth. Why is that ? And is there a way to filter the interior wall from interesected objects.
- 7:30  PM: Where does the point lie on the object from which the ray is casted ?
- 9:00  PM: Perfect snapping along X axis.

## **Wednesday: Februrary 14**
- 9:20  AM: Signed In.
- 10:30 AM: Bypassed media queries and made the code concise and accurate. Now the spinner-container and img-containers are fully responsive.(**#243**)
- 11:00 AM: How to snap the furnishing to its original position ? And the snap means when returning back to the original position, change the positon to the original for already set minimum value of delta (**#222**)
- 12:00 PM: Able to `snap the furnishing to its original position when translated along the x axis`. I Need to implement for other axes and also how to snap the furnishing to wall ?
- 1:30  PM: Shift pointer now snaps to the original position, works for all axes. Refactored a litle.
- 2:30  PM: Submitted **PR #273**. (**#222**).
- 4:00  PM: I have imported the floorplan in my Components.js and I can get pairs of walls which are parallel, but when I move the furnishing, how will I know the walls which are perpendicular to the axis of translation.<br> My idea is that, at any point of time, I want to get the distance of the furnishing from the closest wall. (**#222**)

## **Tuesday: Februrary 13**
- 9:40  AM: Signed In.
- 11:00 AM: Now subdropdowns are also positioned based on the screen height. Updated **PR #265**. Now refactoring the Code.
- 12:00 PM: Undo the changes when the `onLeave` handler is triggered. (**#240**)
- 1:00  PM: **Fixed:** Sometimes door menu is not visible in modular UI. Tested all possible cases, refactored the code. **PR #265** Updated. Going on for the next issue. (**#240**)
- 3:00  PM: Able to make the UV sliders responsive, bit the positioning of sliders is not up to mark when the screen width decreases.
- 5:00  PM: **Fixed:** UV sliders not aligned properly.**PR #268** Submitted. (**#243**)
- 6:00  PM: Changed the color of the spinner to grey and did some minor polishes in the code. Updated **PR #268**.
- 7:00  PM: **Fixed:** Show material ids in the Material Reel. Submitted **PR #269**. (**#248**)
- 8:30  PM: Download the front view images of `TV` and `Door`, `tv.png` works fine but yet I need to confirm the authenticity of the file.
Also, how to reproduce the error - `tv.png not found.` in modular. (**#244**)
- 9:30  PM: I got the door image but seems like the `loadScaledImage()` inside `UnitRenderer.js` is repeating the door to fill the height and width of the actual door fitting. (**#244**).

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

