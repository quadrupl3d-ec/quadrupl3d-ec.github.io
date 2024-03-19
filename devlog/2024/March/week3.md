---
layout: default
title: Week 12
---

# **March Week 3**
## **Monday: March 19**
- 9:40  AM: Signed IN.
- 10:00 AM: `ec renders monitor` working now.
- 11:00 AM: Setting the internal section to `Internal Drawer` errors out, maybe because we're trying to add a fabric object to canvas ? The error says - `c.getObject()` is not a function.
- 12:00 PM: **PR #559** Submitted. Merged in **release**.
- 1:45  PM: Got renders done in dev environment's HOST. Now need to get renders in Jobs container. The lighting seems dull in daytime renders. Need to import the `.blend` file in blender and do some tweaks to improve daylight rendering.

## **Monday: March 18**
- 9:40  AM: Signed In.
- 11:00 AM: Testing renders on `beta.emptycup3d.com`.
- 12:00 PM:  have found a patch but it's not a good fix. Why `r.thumbnail_ref` exists even if the render is not finished ?<br>
This is returned by to_json() method of the Render class in renders/core.py. The r.thumbnail_ref is returned by _thumbnail_store.get_asset_ref()<br>
Right now, the patch could be - If `r.status` is `finished`, then only set the image source to `r.thumbnail`
- 1:15  PM: **Fixed:** Render thumbnails not showing up in the UI. **PR #552** Submitted to release.
- 3:30  PM: **Fixed:** Woodwork deleted if delete key is pressed on a selected partition after mousemove. **PR #554** Submitted.
- 5:00  PM: **Fixed:** When moving a furnishing on the axis, it was interfering with other furnishing objects in the way, resulting in glitches.
- 5:30  PM: Worked out new glitches in modular UI.
- 7:00  PM: Done with a debugging call with Ab sir.
- 9:00  PM: Done setting up render worker again. I've mistakenly reset the beta render worker.
