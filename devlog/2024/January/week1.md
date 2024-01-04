---
layout: default
title: Week 1
---
# **January Week 1**
## **Tuesday: January 2**  

### **Making Renders work on development environment**  
In production, render workers are cloud VMs but we can't use them in development as it will make the development environment complex and also it won't be feasible. So, first of all I have to understand the request flow.

#### Analysing the Request flow:

1. The request is made from the client side API to server side API, which is directly Targeting the `core.py`.
2. core.py calls the `JobManager` from `jobs.py`, this called as `render-manager`, this manages the queues inside the redis in-memory database.
3. Redis contains 3 queues `mq, sq, pq`. Any job associated with any queue must have a corresponding job id `mjid`. If there is no `mjid` for a job, then it will simply throw "no such jobs".
4. `JobManager` posts the jobs to the queue in redis, this post methods does some checks and `enqueues` the job and commits to the db.
5. Optimization lets the fresh job enter in the `pq` instead of the `sq`.
6. A job in any queue ( `sq` or `pq` ) is fetched/picked by the corresponding render worker.
7. Since, jobs in the queue can be added through the UI, theredore I need to setup render worker on my host machine.

#### Drawing the flow chart
I have drawn the request flow diagram ( a mini system design) that demonstrates how renders work in cloud environment and how we can leverage the development environment access to make renders work on host machine.

#### Connecting to Redis
Since I already have my docker container running and have the redis port opened, I can connect to the redis in-memory databse through the `redis-cli` utility and list all the `KEYS` ( these are jobs added to the render manager )

#### Setting up render worker on host machine for development
1. Installed blender version specified in the `Inspect` section of the docker container `api`.
2. Created a symbolic link to the to `/usr/bin/blender`, since rqworker directly uses the `blender` command to run it.
3. activated aliases using `conf`
4. `run_preemptible_render_worker` invokes the appropriate `rqworker` bash command which connects to `redis` to fetch the current job to be executed by the render worker.
5. To download the preview render from UI, I have to click on `refresh` to download the rendered image.

#### Using the render worker to get HD renders
- I added credits through the db and then requested the render in 1080p, so now what happens is, the render-request for a HD render is added to the redis queue.
- This will commit to db that an HD render is requested by a particular user.
- Now manually using the alias to invoke rqworker which fetches this render request from the redis-db.


## **Tuesday: January 2**  

#### Getting started with three.js

#### Analysing `walkin.js` 
