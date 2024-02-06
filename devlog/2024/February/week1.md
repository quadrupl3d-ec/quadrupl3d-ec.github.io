---
layout: default
title: Week 5
---
# **February Week 1**
## **Tuesday: Februrary 6**
- 9:20  AM: Signed In.
- 10:00 AM: **Fixed:** `Show the UV sliders only after the texture is loaded.` (**#192**)
- 12:30 PM: Instead of using `on:load` on the `<img>`, we can fix the dimentions of the container in which the image will be loaded. This is a better fix.
- 1:30  PM: Find out a way of displaying the loader till the image loads.
- 2:30  PM: **Fixed:** Enhancing the UX by displaying a spinner till the image loads, also the positioning of UV sliders is no more causing glitches. Get awesome CSS loaders from `https://cssloaders.github.io/`.
- 3:45  PM: On `Walkin.init()` how do I initialize components ? And most probably this bug occurs from the stale state of previous 3D session.

## **Monday: Februrary 5**
- 9:20  AM: Signed in.
- 10:30 AM: When I click on save, the constructor of Cupboard.js is initialized again, and setting `this._doorType = double`,
Meaning the problem is definitely not inside `Cupboard.js`. `onSave()` calls `saveWoodwork()` and after this point I'm a bit confused like how the function call stack will be executed. 🤔 (**#75**)
- 11:00 AM: **Fixed**: `Show material interface on clicking on 3D`. (**#131**)
- 12:30 PM: Done with the debugging call with sir, fixed the issue ! **;)** (**#75**)
- 1:30  PM: Submitted the PR's for 2 bug fixes. (**#131 and #75**) and opened new issues (**#192, #193, #194**)
- 5:00  PM: Gone through the documentation of `bootstrap v3.3`, why I am not able to fix this bug even after investing a lot of time in this ?
There is definitely some trick which I can't see. I have to read between the lines.
- 7:00  PM: Toggled dropdown menu but why I'm not able to do the same in `onMousemove()` of `SectionRenderer` ?
- 8:00  PM: I'm able to toggle the dropdown menu but not conditionally ;(
- 9:00  PM: Done with the debugging session with sir. Signed out. ()