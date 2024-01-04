---
layout: default
title: Week 1
---
# **January Week 1**


## **Wednesday: January 3**

#### **Getting started with three.js**
1. Installing the latest versions of vite, node, npm.
2. Initialising a `Basic scene` project and importing three.js using main.js
3. Creating a scene, adding a cube geometry to the scene, adding material to the geometry. Then creating a mesh using geometry and material.
4. Rendering the scene inside a canvas using `webGL`.
5. Setting up a camera to view to cube, transforming the camera to view the geometry accordingly.
6. Next, I've set up a raycaster and casted a ray using `raycaster.set(rayOrigin, rayDirection)` and if it intersects the cube object then the color of cube is changed to blue.
7. Using `setFromCamera()` method to cast a ray from the near plane of camera to any point that is in the xy plane, z=0. This is done by setting up a 2D mouse vector which is basically a unit vector. Now added an eventlistener that fires on mousemove and mousemove will create the variable `2D mouse vector`. Therefore, on hovering onto the cube object, the color changes.

#### **Analysing `walkin.js`**
At this point, I'm dealing with frontend component `3D page` of the web application. In the webapp docker container, my focus is on `lib/scenejs/walkin.js` and `Components.js`. I'm going to create a plugin called `ShiftPointer` that will be used to select and translate any furniture object in the 3D page within the canvas while the shift key is holded. This is a bit complex.
So, the first step is to change the cursor to a `Arrows move image` while holding the shift key. This is done by downloading the png image from bootstrap icons, using it in a css class and manipulating the appropriate DOM element using JQ.



## **Tuesday: January 2**  

### **Making Renders work on development environment**  
In production, render workers are cloud VMs but we can't use them in development as it will make the development environment complex and also it won't be feasible. So, first of all I have to understand the request flow.

#### **Analysing the Request flow:**

1. The request is made from the client side API to server side API, which is directly Targeting the `core.py`.
2. core.py calls the `JobManager` from `jobs.py`, this called as `render-manager`, this manages the queues inside the redis in-memory database.
3. Redis contains 3 queues `mq, sq, pq`. Any job associated with any queue must have a corresponding job id `mjid`. If there is no `mjid` for a job, then it will simply throw "no such jobs".
4. `JobManager` posts the jobs to the queue in redis, this post methods does some checks and `enqueues` the job and commits to the db.
5. Optimization lets the fresh job enter in the `pq` instead of the `sq`.
6. A job in any queue ( `sq` or `pq` ) is fetched/picked by the corresponding render worker.
7. Since, jobs in the queue can be added through the UI, theredore I need to setup render worker on my host machine.

#### **Drawing the flow chart**
I have drawn the request flow diagram ( a mini system design) that demonstrates how renders work in cloud environment and how we can leverage the development environment access to make renders work on host machine.

#### **Connecting to Redis**
Since I already have my docker container running and have the redis port opened, I can connect to the redis in-memory databse through the `redis-cli` utility and list all the `KEYS` ( these are jobs added to the render manager )

#### **Setting up render worker on host machine for development**
1. Installed blender version specified in the `Inspect` section of the docker container `api`.
2. Created a symbolic link to the to `/usr/bin/blender`, since rqworker directly uses the `blender` command to run it.
3. activated aliases using `conf`
4. `run_preemptible_render_worker` invokes the appropriate `rqworker` bash command which connects to `redis` to fetch the current job to be executed by the render worker.
5. To download the preview render from UI, I have to click on `refresh` to download the rendered image.

#### **Using the render worker to get HD renders**
- I added credits through the db and then requested the render in 1080p, so now what happens is, the render-request for a HD render is added to the redis queue.
- This will commit to db that an HD render is requested by a particular user.
- Now manually using the alias to invoke rqworker which fetches this render request from the redis-db.

<br>

