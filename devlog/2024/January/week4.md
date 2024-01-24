---
layout: default
title: Week 4
---
# **January Week 4**
## **Wednesday: January 24**
- **0**    Continuing the thread `Enable Esc to reset view #66`
- **+1**   **Fixed: #66**. Commit done. Pushed. Now changing the way in which the key is listening. (#66)
- **+1**   I have exposed `this.resetCamera = function(config) {}` in `scenejs/Walkin.js` <br>and in `js/Walkin.js`, `_setupScene(layout, container)` returns an object created using Scene class. So the method `resetCamera()` can be called on this object. But how to add the eventListener ?
- The pr for implementing shortcuts is still pending so moving onto the next issue.
- **0.5**   Worked on issue number **57**.
- 12:30 PM: Starting to understand the issue `Implement individual mesh material application.` (#56)
- 1:30  PM: Understood the issue clearly and how the implementation differs from the default application. (#56)
- 3:00  PM: Cleared some confisions about `how two meshes can have the same texture on clicking it.`
- 4:00  PM: Able to set event listeners and change the texture of the first mesh from the list of brush's intersection array.
- 5:00  PM: Still thinking about how to filter the mesh that is double clicked.
- 6:00  PM: **Fixed #56**. Commit done. Pushed. Submitted PR for (#56)
- 7:00  PM: Displaying the UV scale of each material in the material reel. (#57)

## **Tuesday: January 23**
**Total Hours worked = 9.67**
- **0**   Going through the suggestions on different open threads (issues).
- **+1**  Working on **#61** Invalid state on setting mirror and then setting full glass for door.
- **+1**  Still thinking about the logic to fix the invalid state.
- Fixed issue number **#61**. Commit done. Updated the pr.
- **+1**  Spent some time on fixing 60 but then got instruction to mark it as **triage** and **51** is blocked till we receive a confirmation from the designers team.
- started working on **#66** Enable Esc to reset view.
- **+1.5**  Created a Javascript class `EscapeReset()` that is enabled it in `walkin.js` as a plugin component. I got the camera position using the camera object, but should I get it using the `scene tree` ?
- **+1**  I am able to set the camera position to the initial position but I have to figure out how to incorporate the rotations about the `Pitch` and `Yaw` axes.
- **+1** For orbit camera, the globle variable `initialPos` is updated to the current position of the camera but it works fine for firstPerson camera. I need to rethink the logic.
- **0.5**  Made the right strategy to reset the camera and not just change the position of it.
- **+1**   I am now able to reset the camera when the `mode == 'firstperson'`. Thinking how the same reset camera functionality can be implemented for `mode == orbit`.
- **40 minutes** Still stuck on "Why the value of variable `initialO` is being overridden with the current position of camera in orbit view ?
What is the other way of resetting the camera if not using `camera.position.set()` ?"
- **0.5**  Trying to fix issue number **#75**: Error while changing the Door Type to 'Pooja'
- **0.5**  Learning about `Textures`, `UV scaling`, `UV unwrapping` as these issues will help me when I'll implement the `UV scaling feature`.

## **Monday: January 22**
- Learned how to think and how debugging works, how to use the browser's debugger. How to narrow down the scope of bug to hunt it in minimum possible time.
- **Fixed**: Handles are not visible in External drawer section.
- Developing a broad picture about how to fix these issues in upcoming days.
   - Enable Esc to reset view.
   - Remove horizontal strip option in DoorPattern.
   - Clear doorPattern strip on changing to glass doors ()
   - Invalid state on setting mirror and then setting full glass for door.
   - Give option for UV scaling.
 
- How UV scaling works and how this new feature will be implemented ? 
