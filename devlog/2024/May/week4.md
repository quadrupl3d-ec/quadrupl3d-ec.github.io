---
layout: default
title: Week 18
---

# **May Week 4**
## **Thursday: May 23**
- 8:30  AM: Signed In.
- 8:00  PM: Signed out

## **Wednesday: May 22**
- 8:00  AM: Signed In.
- 1:00  PM: **Implemented:** Shift click to apply material to all the walls of the room. (**PR #1023**)
- 3:00  PM: If a Material is applied to the screen of a TV or laptop then its preset should be `glow` by default?
- 4:30  PM: 2 issued unblocked.

## **Tuesday: May 21**
- 8:00  AM: Signed In.
- 10:00 AM: Collaborating with Raj to debug glitches in single axis pointer.
- 12:00 PM: I have a new and much simpler approach for all cases. I have implemented it for the X and Z axis, it is very smooth.
- 2:00  PM: Implemented single axis pointer in Z direction using new concept. No more using dx, dy, dz, crossx etc. Simplified `_computeTranslation()`.
- 3:00  PM: Implemented single axis pointer in all directions, refactored the code. Ready for review. (**PR #1000**)
- 5:45  PM: Done with planning call for v0.6 and demo call.
- 8:00  PM: Done with the scrum call for today.

## **Monday: May 20**
- 8:00  AM: Signed In.
- 9:00  AM: **Fixed:** Cupboard section not visible if internal section of a box is set to hanger. (**PR #989**)
- 11:00 AM: Changed the controls for first person and orbit view. `pg up + q` replaces `x`, `pg dn + a` replaces `z`.
- 11:30 AM: Removed `W S A D` for controlling first person camera. `page up OR q` replaces `x`. `page down OR a` replaces `z`. 
- 3:00  PM: Implemented single axis pointer for X axis.  (Very smooth).
- 5:00  PM: Implemented single axis pointer for all axes but seems too glitchy in Y and Z axes. Why is that happening?
- 5:30  PM: Along the z and y axis, it is glitchy. But for the x axis it is very smooth, why this may be happening!
For x axis I have chosen xy plane, for y axis I have chosen yz plane, for z axis I have chosen zx plane. It was coming to be very glitchy along the z axis. Then I chose all 3 planes for z axis and it was not that glitchy but this isn't the solution. I should dig in a bit deeper.
- 6:30  PM: Not able to figure out!.
- 8:30  PM: Re-checked all the vector equations, nothing seems wrong in terms of calculating Q.
