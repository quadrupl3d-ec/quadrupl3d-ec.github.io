---
layout: default
title: Week 12
---

# **March Week 3**
## **Monday: March 18**
- 9:40  AM: Signed In.
- 11:00 AM: Testing renders on `beta.emptycup3d.com`.
- 12:00 PM:  have found a patch but it's not a good fix. Why `r.thumbnail_ref` exists even if the render is not finished ?<br>
This is returned by to_json() method of the Render class in renders/core.py. The r.thumbnail_ref is returned by _thumbnail_store.get_asset_ref()<br>
Right now, the patch could be - If `r.status` is `finished`, then only set the image source to `r.thumbnail`
- 1:15  PM: **Fixed:** Render thumbnails not showing up in the UI. **PR #552** Submitted to release.
- 3:30  PM: **Fixed:** Woodwork deleted if delete key is pressed on a selected partition after mousemove. **PR #554** Submitted.
