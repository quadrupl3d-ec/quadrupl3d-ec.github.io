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

#### Setting up render worker on host machine for development
1. 
