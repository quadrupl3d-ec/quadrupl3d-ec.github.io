---
layout: default
title: Week 12
---

# **March Week 3**
## **Friday: March 22**
- 9:35  AM: Signed IN.
- 

## **Thursday: March 21**
- 9:35  AM: Signed IN.
- 11:00 AM: **PR #572** Submitted. Contains minor fixes for renders.
- 12:00 PM: Installed all the graphics drivers for AMD RADEON RX 5600M. Now I can't boot into ubuntu. Ubuntu is not compatible with amd graphics drivers. Switching to Windows Subsystem for linux.
- 2:15  PM: Deployed the web application on docker through WSL Ubuntu-22.04.03. Need some sql dumps to set up local database.
- 4:30  PM: Finished setting up everything on WSL. Blender2.79 GUI is running super smooth in windows.
- 5:30  PM: Trying to use the dedicated GPU for any GUI applications running on WSL through X server on windows.
- 7:00  PM: Using dedicated GPU to get a 1080p render in windows. Dedicated GPU takes ~12min. to get a 1080p render.
- 9:30  PM: Using integrated GPU to get renders.

## **Wednesday: March 20**
- 9:30  AM: Signed IN.
- 10:45 AM: **Fixed** missing slot keys corresponding to windows, walls etc. And the jobs container is still not resilient to errors.
- 12:00 PM: Not able to get renders sometimes. And night renders don't have sufficient illumination.
- 1:00  PM: Why `model.json` contains - `Blob not found` sometimes. This wasted a lot of time as this will result into `JSON decode error.`
- 3:00  PM: Got night renders for all type of presets - `Low`, `High`, `Spot`, `Panel`, `Medium`.
- 3:30  PM: **Fixed:** Render thumbnail doesn't have options when status is 'Started'. (**#129**).
- 4:00  PM: Why we're not able to set the section to `internal-drawer` ? Why the shelf section is still rendered in external sections ?
- 7:15  PM: When I try to set the section to internal-drawer, the `render()` method is called, it calls `_renderTextureFill()` from its parent class.
This renderTextureFill expects an image source so that it can use that image's texture and scale it to the size of section. But the image src is undefined,
causing error. Why all the functions inside render() are erroring out ?
- 8:00  PM: What is the difference between `new fabric.Rect({})` and `CanvasObject.create({})` ?

## **Tuesday: March 19**
- 9:40  AM: Signed IN.
- 10:00 AM: `ec renders monitor` working now.
- 11:00 AM: Setting the internal section to `Internal Drawer` errors out, maybe because we're trying to add a fabric object to canvas ? The error says - `c.getObject()` is not a function.
- 12:00 PM: **PR #559** Submitted. Merged in **release**.
- 1:45  PM: Got renders done in dev environment's HOST and in `Jobs` container as well. The lighting seems dull in daytime renders. Need to import the `.blend` file in blender and do some tweaks to improve daylight rendering.
- 4:00  PM: Why the material that corresponds to a woodwork is not visible/applied in the render scene ? <br>   Done with a debugging call with Ab sir. 
- 4:45  PM: Able to log the render request and see the theme dictionary and components in the jobs container.
- 7:00  PM: Getting the mesh area through `sum(p.area for p in o.data.polygons)`, but the model used for rendering in blender and the model used in 3D are not same. This patch will work for woodwork meshes but not for furnishing meshes. What's the fix to this problem ?
- 9:45  PM: **PR #567** Submitted.

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
