---
layout: default
title: Week 11
---

# **March Week 2**
## **Monday: March 11**
- 9:30  AM: Signed In.
- 10:45 AM: Updated **PR #488**. Review requested. (**#483**)
- 11:30 AM: Now using libcloud's Azure ARM driver to manager Azure resources instead of using Azure SDK for python. No need to create a separate resource client to manager azure resources, we can use the driver created by libcloud. **PR #488** Updated. (**#483**)
- 12:00 PM: `subprocess.check_output` will return a bytes like object therefore using `utf-8` decoding to convert it to a string so that it can be applied as a tag on the worker VM. (**#483**)
- 12:30 PM: `Adding a woodwork in modular won't update the Floorplan`. Worked on - `Not able to add decor in modular`.
- 2:00  PM: Figured out why decor items are not loaded in `Modular UI`.
- 2:30  PM: Able to load the decor items in `Modular UI`.
- 4:00  PM: Figured out why we're not able to save the woodwork if a decor item is added to it. This is happening because `decor.json` is empty i.e blob storage is not returning the brick if the component type is `decor`. (**#448**)
