---
layout: default
title: Week 10
---

# **March Week 1**
## **Friday: March 8**
- 9:45  AM: Signed In.
- 11:00 AM: Tested razorpay integration in test mode. Need to test in live mode. (**#382**)
- 11:30 AM: Now `toJSON()` return laminates for all sections along with box's laminates. How laminates are composed in the backend ? For eg., if box has laminates, then backend takes the `box._laminates` array from `json` and composes laminates for each laminate present in the array. How to do the same thing for `sectionLaminates` ? (**#354**)
- 12:30 PM: No need to return `json.sectionLams`, append the laminates to `json.laminates`. (**#354**)
- 1:45  PM: Done with the code review call for **PR #371**
- 3:00  PM: **PR #462** Updated. Open section now have laminates. (**#354**)

## **Thursday: March 7**
- 9:15  AM: Signed In.
- 10:30 AM: Found multiple glitches in ModularUI. Worked out `Razorpay Integration` (**#**)
- 12:45 PM: Done with the code review call for 5 PR's. **Merged PR:** **#372 and #439 and #461**.
- 3:00  PM: Fixed a logic bug in **PR #461** (Custom drawer handles).
- 4:15  PM: **PR #371** Updated. Why `woodwork-options.json` is not returning `drawer` options ?
- 4:45  PM: Still trying to figure out how to compute laminates for open sections.
- 7:30  PM: Able to see laminates in 3D for open sections. Adding `getLaminates()` to `Section.js`.
- 8:30  PM: Calling `getLaminates()` for all sections in `toJSON()` but that too is called a number of times, resulting into repetition of laminates.
- 10:30 PM: Got an overview about how to integrate Razorpay for accepting payments. Currently, we can `createOrders()` and `verifyOrders()`. Need to set up routes in `APIClient.js` to capture and track the status of payments. (****)

## **Wednesday: March 6**
- 9:35  AM: Signed In.
- 11:00 AM: Figuring out a way to set laminates for open sections. (**#354**)
- 12:00 PM: Setting the laminates but they're getting set again and again for the same section. How to fix this ? (**#354**)
- 1:00  PM: Worked on `Customise door handles for external drawers`. (**#254**)
- 4:00  PM: How do I enable `Handle Type` as a `menuItem` when the section is set to `External Drawer` ? (**#254**)
- 5:30  PM: Able to set the `Handle Type` options for External Drawer but in 3D the position of the channel is not correct, what is causing this ? (**#254**)
- 7:00  PM: Woodwork options are fetched from the API while initializing modularUI adaptar. (**#254**)
- 8:00  PM: **PR #461** Submitted. How to set the handle position in `ExternalDrawer.js` for different handle types ? (**#254**)
- 9:30  PM: **Fixed:** Customise door handles for external drawers. **PR #461** Updated.
- 10:30 PM: **PR #462** Submitted. (**#354**)
- 11:30 PM: **PR #371** Updated. Implemented logging in `backup.py`. <br> **PR #439** Updated. Giving names to service containers in order to filter them correctly.

## **Tuesday: March 5**
- 9:20  AM: Signed in.
- 11:00 AM: Implement proper logging in `emptycup.core.cloud`, need to associate the cloud node with the job being executed by the node.
- 12:30 PM: **PR #372** Updated. Ready to merge in master.
- 2:00  PM: Now cloning all the branches and then making a ZIP file. (**#320**)
- 4:00  PM: Updated **PR #372**
- 5:00  PM: Done with the code review call regarding 3 PRs with Ab sir.
- 7:30  PM: Refactored all 3 PRs. (Re-requested code review). **PR #371, #372 and #439** Updated.

## **Monday: March 4**
- 9:30  AM: Signed In.
- 11:00 AM: Submitted **PR #439** from `jobs-container`. (**#103**)
- 12:00 PM: Mistakenly deleted the `version/xxxx.py` migration file of db, but the version is saved in MySQL workbench. How to fix ?
- 1:45  PM: **PR #364** Updated from branch `time-to-render`. (**#90**)
- 3:00  PM: **PR #439** Updated. Filtering based on a name contained within the image name. (**#103**)
- 4:30  PM: Getting a wierd error in logging requests to mixpanel. (**#**)
- 5:00  PM: No need to send `sjid` or `pjid` to mixpanel.
- 7:00  PM: How to get the `vm-name` from `Cloud.py` which is currrently executing the job ?
- 9:30  PM: Done with the weekly review call with CTO and Manager.
