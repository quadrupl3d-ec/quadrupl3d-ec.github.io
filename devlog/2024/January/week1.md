---
layout: default
title: Week 1
---
# **January Week 1**


## **Friday: January 5**

#### **Adding the Axeshelper to a furnishing object**
1. Starting with the `axesHelper()` class of three.js, I faced the same issue I was facing with the `Box3Helper()`. It is conflicting with the version of theee.js used in our stack. The version we are using supports the old method `axisHelper()`.
2. Now I am able to add the axes of any length to the furnishing object. And this is done by copying this axisHelper to the centre of the furnishing object using the BoundingBox vector.
3. But on adding this axis helper, it is just rendered after the mouse is moved. This means that the frames are not rendered continuously, therefore I have to render the frame by triggering the sceneChanged.
4. Now, another issue that I'm facing is each time on mouse over on the furnishing object, a new axesHelper constructor is created as I was creating this constructor inside the `addAxesHelper(object)` function, which was called on every mouseover event. Simply moving this constructor out of the function solves the issue.

#### **Hovering on any furnishing object**
I have created an array that will contain the `uuid` of any hovered furnishing object on `shift key press` and this array will be initialized to an empty array [] as soon as the key is released, followed by detaching the mousemove event listener.

#### **Adding the axesHelper to any number of furnishing objects, one at a time**
Now that I have an array that contains the object with a unique `uuid` of any hovered object. I can add the axesHelper to the center of this object upon hovering onto it. And that empty array makes sure that the axes helper is not added again and again to the same furnishing object.

#### **Detaching the axesHelper upon keyup or hover onto another furnishing object**
We are not disposing the axesHelper upon keyrelease, we're `detaching` it from the scene. Meaning that the constructor still lives and will attach itself to any hovered furnishing object. And on hovering onto any other furnishing object present within the scene, the axesHelper attaches to the newly hovered furnishing object. The idea is simple, "we can't have two objects in the `hoveredFurnishingObject()` array.

## **Thursday: January 4**

#### **Creating a JavaScript class**
Upon analysing how the `scenejs` works, I get to know that walkin.js calls the JavaScript classes from `Components.js`. In addition to this, there are many helper functions inside `walkin.js`. Now the goal is to interact with any furnishing object upon holding the shift key.

#### **Creating the ShiftPointer**
1. Naming the class as `3DPointerControls` will be too generic and therefore is not a good practice for naming conventions. Since this class should trigger on pressing and holding the shift key and then it vests in some power to the pointer to translate the objects using pointer, `ShiftPointer` should be the class name.

2. I need to have two state variables, one for tracking if the class is enabled or disabled and one for tracking the press of shift key. To get started, let's always keep this class enabled.

3. In order to replace the pointer with an `arrows-move` icon, it's good to create eventlisteners for `keydown` and `keyup` events.
On Keypress,`handleKeyPress` will be called which will add an event listener `handleMouseMove` that listens for `mousemove` event only when the shift key is pressed.

#### **Getting all the Furnishing Objects from the scene**
1. There is a helper function in `walkin.js` that lets get all the mesh objects associated with the current scene.
2. `getMeshes()` will set up a ray caster and casts a ray in the direction specified by the 2D coordinates of a `mouse` vector. Therefore, all I have to do is pass these coordinates to the getMeshes function and it returns all the meshes intersected by mouseover.
3. Now that I have all the meshes intersected by the 2D mouse vector, I have to figure out how to calculate the furnishing object using this.
4. Creating a `getFurnishingObjectFromMeshes(object)` function that will check if the parent of a mesh is an object 3D instance of three.js and has a `userData.isFurnishingObject` set to `true`. This function will simply push this object into the array of furnishing objects.

#### **Adding a boundingBox**
Now my next Target will be adding the bounding box to the hovered furnishing object. 

1. Creating a bounding box using the `Box3()` three.js class. What this does is, it can calculate the center of the object using the `setFromObject(object)` method. This constructor will return the bounding planes encompassing the object in form of two vectors:
`min {}` and `max {}` 

2. I can get the co-ordinates of the bounding box by `boundingBox / 2`, Since the position of the object is already `{ x:0, y:0, z:0 }`

3. I don't know why, but I am not able to create a visualization of this BoundingBox Using the `Box3helper()` method. But after spending hours on it, my guess is that we're having three.js version conflict with class names.

 

   
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

