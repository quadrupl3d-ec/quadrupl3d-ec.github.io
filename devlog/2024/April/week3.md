---
layout: default
title: Week 16
---

# **April Week 3**
## **Wednesday: April 17**
- 9:10  AM: Signed In.
- 11:30 AM: **PR #690** Submitted to release. **Fixed:** Renders not working if woodwork furnishings are present in the scene.
- 12:30 PM: Not able to get night renders in production.
- 1:30  PM: WSL goes off. Not able to log into WSL.
- 3:00  PM: We enabled fast GI for version `3.2.2`. Therefore, in production, if we get night renders, then ao's effect will be added to the night lights, thereby over illuminating the render.
- 3:15  PM: **PR #693** Submitted to `release`.

## **Tuesday: April 16**
- 9:10  AM: Signed In.
- 11:30 AM: On `double click` on a mesh, changing the material of all the meshes who have the same slotname (for layout furnishings).
- 12:30 PM: Changing material of all the meshes that are a part of `layout furnishings`.
- 1:15  PM: If shift key is pressed and material is applied, then change the material of all the layout furnishings. Need to implement it for woodwork furnishings as well.
- 4:00  PM: Implemented shift + double click for layout and woodwork furnishings. **PR #685** Submitted.
- 5:15  PM: **PR #685** Updated. Tested in all cases. Filtering woodwork furnishing meshes and layout furnishing meshes using the mesh and the scene tree. Using `M` key for moving the furnishing instead of `Shift`.
- 8:00  PM: Error getting renders in the latest release if the woodwork has a furnishing.
