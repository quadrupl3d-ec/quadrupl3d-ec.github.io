---
layout: default
title: Week 8
---

# **February Week 3**
## **Wednesday: Februrary 21**
- 9:30  AM: Signed in.
- 10:30 AM: Able to acces the beta deployment lcoally on port 4000. Now having some issues connecting to the MySqL server.
- 12:00 PM: Read about `Github actions`. Read about `rq` in python. Did the documentation for the beta deployment. (**#312**)
- 1:00  PM: Done with the call with Ab sir, finding a way to enable the connections from the api container to the cloud db.
- 2:00  PM: Signing up for Azure account, having issues with debit card and credit cards.
- 4:00  PM: Deployed a MySQL Azure flexible server and connected to it using SSL. Currently configured with public access. Now need to export oue DB and import it in the newly created DB. (**#312**)
- 5:00  PM: Updated the `beta.Dockerfile` to use the new db connection string and connect to the newly created Azure DB. Build and deployed the beta containers again. Now the beta deployment is working good. So, in all, the folks need to add their IP to this Azure server's firewall rules and they're good to go with the beta deployment.

## **Tuesday: Februrary 20**
- 9:30  AM: Signed In.
- 11:00 AM: Done with the call with Ab sir, highlighted some points about the new task.
- 12:00 PM: do I have to set this up locally so I should use the same `beta.Dockerfile` and containerize only the webapp on a different port. As the beta will use the same api, redis and db ?
- 1:00  PM: I created a `docker-compose-beta.yml` that only contains the `webapp` service and uses `beta.Dockerfile`. And the 3 containers remain same. But this is wrong.
- 2:00  PM: The beta version will have two containers only and it will use the cloud redis and clous db. Therefore, creating `docker-compose-beta.yml` to deploy a multi container application.
- 3:00  PM: Forgot to update the `supervisord.conf` file for beta environment inside the docker compose file. Fixing `redis: 6379` not found issue inside the container logs.
- 3:30  PM: Able to deploy the `beta.emptycup3d.com` locally but why the frontend is not accessible ?
- 5:00  PM: I'm mapping the host port to container's port and exposing the port in `beta.Dockerfile`, still the frontend is not accessible. Why is that happening ?
- 8:00  PM: Done with the call with entire team about streamlining planning and execution. Deciding the new way of maintaing spent hours on unshaped tasks.

## **Monday: Februrary 19**
- 9:20  AM: Signed in.
- 11:00 AM: Visualizing the casted ray to check the authenticity of `_computeTranslation(x, y);`
- 12:00 PM: If `a1a2` vector is perpendicular to any axis, then we get incorrect results about the `min. distance from ray calculation.` Why is that happening ?
- 1:30  PM: Done with the call with Ab sir. Got some valuable insights about the implementation of `ShiftPointer.`
- 3:00  PM: How to select the point of intersection so that A1A2 vector will lie in the plane containing the axis ?
- 4:00  PM: Submitted **PR #230** (**#225**)
- 5:15  PM: Submitted **PR #273**. Snap the furnishing to walls. (**#222**)
- 6:30  PM: How to differentiate the meshes that correspond to the interior face of a wall which are intersected by the raycaster ?
- 7:00  PM: Maybe the face vertices can help the raycaster in identifying the meshes that correspond to interior walls ?
- 8:00  PM: Is there any way to uniquely identify the interior faces of walls ? Currently I'm using faceIndex = 0. But sometimes interior walls have faceIndex = 1 as well. Like I need a unique identification for the meshes that correspond to the interior face of wall.
- 9:00  PM: Done with the weekly review call with the manager and CTO.
