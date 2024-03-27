---
layout: default
title: Week 13
---

# **March Week 4**
## **Wednesday: March 27**
- 10:30  AM: Signed IN.
- 12:00  PM: **Fixed:** Esc for exiting edit mode in modular.
- 3:00   PM: Not able to figure out why `scale` and `move` are not working after `Undo` in Modular UI!. `onDrop()` calls `moveTo(left, bottom)` from `woodworkjs/Component/Component.js` and is setting `this._left` and `this._bottom` but still the woodwork is not shown up at the new position. Is there something wrong related to rendering or is it Undo doing something wrong or incomplete?
- 4:00   PM: `snap-pointer` branch is now broken. Rebased on top of `release`, but snapping is not at all smooth.
