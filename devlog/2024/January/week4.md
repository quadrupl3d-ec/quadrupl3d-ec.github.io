---
layout: default
title: Week 4
---
# **January Week 4**
## **Tuesday: January 23**
- **0**   Going through the suggestions on different open threads (issues).
- **+1**  Working on **#61** Invalid state on setting mirror and then setting full glass for door.
- **+1**  Still thinking about the logic to fix the invalid state.
- Fixed **#61**. Commit done. Updated the pr.
- **+1**  Spent some time on fixing 60 but then got instruction to mark it as **triage** and **51** is blocked till we receive a confirmation from the designers team.
- started working on **#66** Enable Esc to reset view.
- **+1.5** Created a Javascript class `EscapeReset()` that is enabled it in `walkin.js` as a plugin component. I got the camera position using the camera object, but should I get it using the `scene tree` ?
- **+1** I am able to set the camera position to the initial position but I have to figure out how to incorporate the rotations about the `Pitch` and `Yaw` axes.
- **+1** For orbit camera, the globle variable `initialPos` is updated to the current position of the camera but it works fine for firstPerson camera. I need to rethink the logic.

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
