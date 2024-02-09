---
layout: default
title: Week 5
---
# **February Week 1**
## **Friday: Februrary 9**
- 9:20  AM: Signed In.

## **Thursday: Februrary 8**
- 9:30  AM: Signed In.
- 11:00 AM: Investigating shiftpointer to create the strategy for updating the layout planner (**#210**)
- 12:00 PM: Done with the `Neeeds Shape` call for issue (**#210**)
- 1:00  PM: Got the data from `scenejs` inside `init()`. Attaching the event listener `layoutChanged` that passes the displacement and furnishing id through the event handler.
- 2:00  PM: Exporting `floorplan` from `floorplanjs`, so as to make use of the OOP.
- 3:00  PM: Able to update the layout planner once the user clicks on save in the 3D page. But why is the `layoutChanged` event is triggered multiple times on a single click ? When to remove the event listener ?
- 4:00  PM: Submitted PR **#212**. Fixing **#210**.
- 4:30  PM: **PR #212** Updated. Refacotred and cleaned up. Ready to go in master.
- 5:30  PM: Now updating the layout automatically when a user moves a furnishing and switches to `2D`. Merged **PR #212** in master.
- 6:30  PM: **Fixed:** onSceneReady in shiftPointer erroring out (**#213**)
- 8:00  PM: **Fixed:**OnkeyDown called when `scene == undefined`.
- 9:00  PM: Made the visible ray casted through `showCastedRay(x, y)`. Submitted **PR #217**.

## **Wednesday: Februrary 7**
- 9:15  AM: Signed In.
- 11:00 AM: listeners are not removed from the document in `ShiftPointer`. Added to the issue tracker (**#201**). Still not able to firgure out why the screen is freezing ! (**#193**)
- 1:00  PM: The problem is definitely not in three.js but I have now a high level overview :<br>
Once using the shift pointer, Now switching from 2D to 3D. The geometryGroups array starts from the index value 34, why is that 🤔, and geometry.id = 2 ( geometry = furnishing's geometry ). Therefore in , `var geometryGroupsList = geometryGroups[ geometry.id ];`
`geometryGroupsList` will remain `undefined`, causing an error.
- 2:00  PM: Still lost in `three.js`, why after switching from `2D` to `3D`, the `CylinderGeometry` causes an error ? And why it doesn't cause any errors when not switching ?<br>
I have completely analysed the call stack, but it appears useless to dig in. ;( (**#193**)
- 3:00  PM: Done with the debugging call with sir. My take from debugging session - `Always define the scope of bug and narrow down bug exposure before starting hunting it.`
- 3:30  PM: **Fixed:** Shift pointer freezes the entire 3D page once a furnishing is hovered. (**#193**)
- 4:00  PM: **PR #205** submitted, Now using `THREE.Line()` instead of `THREE.ArrowHelper()`. The bug was in the `CylinderGeometry` inside `three.js`, this was coming from the arrow helper. So removing the arrow helper fixes the bug.
- 4:30  PM: Done the changes in **PR #205**. Giving a unique attribute to the `AxesGroup` in order to identify it `onKeyDown`.
- 5:45  PM: Done with closing some merged PR's.
- 7:00  PM: Removing the `sceneReady` event listeners `onKeyUp`, commit done. But how to remove the listener on switching to `2D` ? (**#201**)
- 9:00  PM: I am removing the sceneReady componentLoaded componentRemoved event listeners onKeyUp, but how to remove them when I switch to 2D. Additionally, I have checked using `jQ._data( document, "events");`. To check all the events that are attached to the document.<br>
On every switch from 2D to 3D increases the sceneReady listeners by 10, why is that ?
 
## **Tuesday: Februrary 6**
- 9:20  AM: Signed In.
- 10:00 AM: **Fixed:** `Show the UV sliders only after the texture is loaded.` (**#192**)
- 12:30 PM: Instead of using `on:load` on the `<img>`, we can fix the dimentions of the container in which the image will be loaded. This is a better fix.
- 1:30  PM: Find out a way of displaying the loader till the image loads.
- 2:30  PM: **Fixed:** Enhancing the UX by displaying a spinner till the image loads, also the positioning of UV sliders is no more causing glitches. Get awesome CSS loaders from `https://cssloaders.github.io/`.
- 3:45  PM: On `Walkin.init()` how do I initialize components ? And most probably this bug occurs from the stale state of previous 3D session.
- 4:45  PM: I think the problem is in `renderer.render()` only 🤔, because when the bug occurs, `the screen freezes before the axes are visible.` So maybe the axes are attached but the render() is having problems
- 5:20  PM: On every switch from `2D` to `3D`, `scene.children` are increasing by 6, why is this happening ?
- 7:00  PM: These 6 children are strange, I'm adding axes only if its not present in `scene.children`, even then `scene.add(axes)` is called. Why is that ?
- 8:00  PM: Figuring out who is adding these 6 meshes ? What are the geometries of these meshes ? I should search for these geometry creations in the codebase, maybe I can hit the correct function.
- 9:20  PM: `Tape` was adding 6 childrens on every swtich from `2D` to `3D`. But still, this doesn't fix the freeze issue ;(

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
