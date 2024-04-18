---
layout: default
title: Week 16
---

# **April Week 3**
## **Thursday: April 18**
- 9:20  AM: Signed In.
- 10:00 AM: **Fixed:** Only prompt for changing handleType for all sections if the sections `hasHandles()`
- 10:15 AM: **PR #685** Updated. Refactored allMeshes, meshOnly to `scope`.
- 11:30 AM: What is the ideal way to apply material only to the ledge?
- 2:30  PM: **PR #699** Submitted. **Fixed:** Apply material to entire ledge.
- 3:30  PM: Started testing the product at `beta.emptycup3d.com`.
- 5:15  PM: Improvised the refactor. **PR #685** Updated.

## **Wednesday: April 17**
- 9:10  AM: Signed In.
- 11:30 AM: **PR #690** Submitted to release. **Fixed:** Renders not working if woodwork furnishings are present in the scene.
- 12:30 PM: Not able to get night renders in production.
- 1:30  PM: WSL goes off. Not able to log into WSL.
- 3:00  PM: We enabled fast GI for version `3.2.2`. Therefore, in production, if we get night renders, then ao's effect will be added to the night lights, thereby over illuminating the render.
- 3:15  PM: **PR #693** Submitted to `release`.
- 4:00  PM: **PR #694** Submitted to `release`. **Fixed:** Tooltip not shown on glass and light materials.
- 4:30  PM: Updated **PR #635**. To create a rectangle, we need 4 points, not 8.
- 5:30  PM: **PR #685** Updated. `Shift + Click` instead of `Shift + Double Click`.
- 6:30  PM: Discussed refactor of `Shift + Click` with Ab sir. Signed out.

## **Tuesday: April 16**
- 9:10  AM: Signed In.
- 11:30 AM: On `double click` on a mesh, changing the material of all the meshes who have the same slotname (for layout furnishings).
- 12:30 PM: Changing material of all the meshes that are a part of `layout furnishings`.
- 1:15  PM: If shift key is pressed and material is applied, then change the material of all the layout furnishings. Need to implement it for woodwork furnishings as well.
- 4:00  PM: Implemented shift + double click for layout and woodwork furnishings. **PR #685** Submitted.
- 5:15  PM: **PR #685** Updated. Tested in all cases. Filtering woodwork furnishing meshes and layout furnishing meshes using the mesh and the scene tree. Using `M` key for moving the furnishing instead of `Shift`.
- 8:00  PM: Error getting renders in the latest release if the woodwork has a furnishing.
