---
layout: default
title: Week 11
---

# **March Week 2**
## **Saturday: March 16**
- 9:30  AM: Signed In.
- 11:00 AM: Done with debugging call with sir.
- 2:00  PM: **Fixed:** Able to save a woodwork which has a decor item in it. (**#448**)
- 4:00  PM: Able to see the woodwork furnishings in 3D but a lot of necessary arguments are missing in `comp` which are needed by `_loadFurnishing(scene, component, woodwork)` through `component`. (**#393**)
- 5:40  PM: **Fixed:** Woodwork furnishings not visible in 3D. (**#393**)
- 6:30  PM: **PR #529** Updated from `save-woodwork` to `release`.

## **Friday: March 15**
- 10:00 AM: Signed In.
- 1:00  PM: Limiting the `refkey` column to 32 characters. Preventing woodwork delete on partition deletion. (**#340**)
- 2:00  PM: **PR #514** and **PR #517** Merged in `beta`.
- 4:00  PM: Confused about storages!
- 7:30  PM: Submitted **PR #522** to branch `release`. (**#340**)

## **Monday: March 11**
- 9:30  AM: Signed In.
- 10:45 AM: Updated **PR #488**. Review requested. (**#483**)
- 11:30 AM: Now using libcloud's Azure ARM driver to manager Azure resources instead of using Azure SDK for python. No need to create a separate resource client to manager azure resources, we can use the driver created by libcloud. **PR #488** Updated. (**#483**)
- 12:00 PM: `subprocess.check_output` will return a bytes like object therefore using `utf-8` decoding to convert it to a string so that it can be applied as a tag on the worker VM. (**#483**)
- 12:30 PM: `Adding a woodwork in modular won't update the Floorplan`. Worked on - `Not able to add decor in modular`.
- 2:00  PM: Figured out why decor items are not loaded in `Modular UI`.
- 2:30  PM: Able to load the decor items in `Modular UI`.
- 4:00  PM: Figured out why we're not able to save the woodwork if a decor item is added to it. This is happening because `decor.json` is empty i.e blob storage is not returning the brick if the component type is `decor`. (**#448**)
- 5:00  PM: Figuring out a way to verify if the brick's blob store contains appropriate bricks for component that are of type `decor`. Additionally, Blocked on unshaped, unconfirmed, not-outlined issues.
- 7:00  PM: Updated `log-vmname` **PR** and Posted the error stack trace to AB sir. (**#448**)
- 9:15  PM: Done with the manager and CTO with the weekly review call.
