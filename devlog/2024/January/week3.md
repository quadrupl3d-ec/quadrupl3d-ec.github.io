---
layout: default
title: Week 3
---
# **January Week 3**
## **Friday: January 19**
- Updated the `toggleEditor` to hide the settings and split icon upon clicking edit. Commit done.
- Found 2 new glitches in modular-ui.
- Identified 3 more bugs in modular-ui.
- Why on changing the section from cupboard to any other section, the `split` icon persists ?

## **Thursday: January 18**
- How the `onMousemove()` of `SectionRenderer()` is affected upon scaling ?
- **Fixed**: Settings and split icon becomes invisible upon scaling any woodwork.
- How scaling affects the section type ?
- How scaling works ?
- When scaling is complete, event `onStop` is completed. Then the section type of is automatically set to `cupboard`. This means, `onStop` is the dead end, but how does `setSize()` calls `_box.reset()` ? 
- **Fixed**: Upon scaling any woodwork, the `section type` is automatically set to `cupboard`.
- Incorporating a `properly channelized way of addressing issues and following the protocol in which OOP works`. Updated the `setSize()` method and no more accessing the private variables. Updated the pr. 

## **Wednesday: January 17**
- Exploring the woorworks UI to look for potential glitches.
- Getting familiar with the woodoworks module in the codebase.
- While wandering in `woodworkjs/woodwork.js`, some classes are using `static methods`, therefore I practiced some examples on `static methods in JS classes`.
- How `lib/woodworksjs` works ?
- Found a glitch in the woodworks customisation page, the door icon is not hided with other icons. Created a new branch and started debugging.
- When the woodwork loads, `modular-container` is created using the `modulasjs` and when a user tries to scale a woodwork, `hideDoor()` was not called on that event trigger, instead `hideDelete()` was being called twice. So, calling `hideDoor()` fixes the issue.
- I want to figure out how the blue line moves onMousemove as it shows glitches in making partitions in the modular-ui.
- What happens when I click the pencil ? How the 3 icons show up on mousehover ?
- Why all the sections except cupboard extend the SectionRenderer class. Why is that ?
- How to make partitioning possible for open sections ? (I'll get back on this later)
- If any woodwork is scaled, the `settings` and `split` icons become invisible, also, upon hovering on ww after scaling it, `settings` and `split` are not visible.
- There is something that is not setting their visibilty to `inline` if the `scale.set == 'ready'`, or I am missing something.

## **Tuesday: January 16**
- Final polishes in the `shift-pointer` plugin.
- Reducing the code length by using the `Array.prototype.filter` method on array, using ternary operator to convert an if-else block in a one liner.
- Rebasing and merging the pr in the master branch.
- Syncing the fork and pulling the latest master.
- Can't request renders through the UI. It says `Cannot read properties of undefined (reading 'unshift')`. Why is that happening ?
Is this same code works in other system ?
- There is an authentication error while requesting assets from Azure Blob storage. These two endpoints are not working because of this issue.<br>
`/projects/<pid>/renders` <br>
`/projects/<pid>/layouts/<lid>`<br>
This is happening because of the expired `CLIENT_KEY`.
- On syncing the fork, pulling the latest master, why this issue persists ?
- Learning about OOPs concepts in JavaScript
- How the woodworks module works in overall ?
- Identifying the glitches in the woorworks 3D page.

## **Monday: January 15**
- Code refactoring. Keeping in mind the fundamental software development practices and the notion of `python zen`.
- Learning about good code and how to organise my code better.
- Refactoring the `_computeTranslation()` in order to reduce the exposure of a bug.
- Learned about advanced code refactoring.
- Learned the basics of `Linux kernel coding style`
- Refacotring the `shiftpointer` class based on the principles of `linux kernel coding style`


