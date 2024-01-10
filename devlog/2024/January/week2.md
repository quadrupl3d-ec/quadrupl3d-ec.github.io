---
layout: default
title: Week 2
---
# **January Week 2**
## **Wednesday: January 10**
- How can I ensure that my scene tree contains all the furnshings/objects/groups because then only I'll be able to do more robust filtering of the axesgroup object and not just picking the last child of the scene ?
- I don't need to filter axesgroup at all, I already have that in a global variable `axes`. xoxo
- I should check if the intersection works even if the planes are invisible.
- Seems like if I intersect only one plane then the axis perpendicular to that plane becomes z axis by default, otherwise, if I intersect 2 or 3 planes then:

      right: +x axis,
      up: +y axis,
      out of screen: +z axis
- If I cast a ray, it will cut minimum 1 plane and maximum 3 planes. I have to calculate the minimum distance between the casted ray and 
each of the x, y and z axis.
- Now I have two mathematical approaches to calculate the min./perpendicular distance between the casted ray and any axis:
   1. Drawing a plane perpendicular to the casted ray which contains the axis from which min. distance is to be calculated.
   2. Find the equation of casted ray and find distance between the axis and the casted ray.
 
- Adding the relative coordinates into an array `relCo`. Because if I have relative coordinates of the intersection points, then it will be much easier to find the perpendicular distance since my origin is now (0,0,0) which is the object's center
                            OR
Can I directly compute the distance ?



## **Tuesday: January 9**
- Reaching to a conclusion that I don't need to add the axes to scene on every call for `attachAxes()`.
- The axes should be only added to the scene once and hovering should just toggle the position and visibility.
- Trying to add the `click` event listener on the hovered furnishing. Therfore, this event listener can't be added normally, it has to be added conditionally.
- How do I translate my object ? What should be the optimal strategy ?
- Since I want to translate the object between two consecutive clicks on any axis, I should add and remove classes to canvas.
- If I click on any point on any axis, I want the co-ordinates of that point so that I can do `object.positon.set(x, y, z)` to update the position of object to that point.
- I need to get the shortest distance between the mouse's 3D coordinates and the axes. Translation should be done along an axis which is closest to the mouse. Shortest distance is the perpendicular distance.
- I am struggling in creating a raycaster through pointer as the `setFromCamera(mouse3D, camera)` doesn't work in the three.js version we are using.
- I have decided to use the existing `_getMeshAt(x,y)` function to intersect the planes.
- I am adding the XY, YZ, ZX planes to my `axes` object, so that I can intersect them using the `getMeshAt(x,y)` function and then I will calculate the projections.
- Now able to intersect the plane and get the point at which the ray intersects it.

## **Monday: January 8**
#### Code refactoring with sir
1. Now that I have a code that works, but the code quality needs to be enhanced. Performance and efficiency should also be thoroughly analysed.

2. I missed fundamental software development practices for example, I was carrying the business logic inside the `handleKeyPress()`, but this should only handle the keypress.

3. I was creating the constructor in a function which was called on every hover, so I was creating the three.js object as many times as I hover onto an object.

#### Debugging an issue
1. I have Listeners that listen for `scene ready`, `component loaded` and `component changed`, but there is no definite order in which these load.

2. In console, we found that the array containing FOs is empty, so tried to debugged that function, but it was working perfectly fine.

3. During the process, I've came across various smart techniques to debug the code instead of only relying on `console.log()`.
For example, in browser's dev tools, I can add breakpoints to specific lines of code and control the execution before and after that.
So we analysed that the furnishings were not loaded completely when the function is called.

4. Therefore, it's most likely that the issue persists in the listener.
Therefore, if `data.scene` doesn't contain the furnishings, and only contain the room and lightings then my functions won't be able to extract the furnishings from the scene.




