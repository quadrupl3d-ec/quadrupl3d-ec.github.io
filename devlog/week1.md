---
layout: default
title: Week 1
---
# **December Week 1**
## **Friday: December 30**  

### **System Freeze fixed**  
Upon setting the kernel parameter to `amdgpu.runpm=0` will keep the GPU on at all times and it won't go to sleep abruptly but this drains the battery life. Till date this is the only patch this issue has. So, I will implement a stable fix in future.  

System works very smooth now. No hangs, no freezes and no modifications in the kernel version.

### **Deciphering the render functionality**
1. #### **`Try Preview` stuck at queued**
Upon going through the docs/docs/renders.md, I get to know that core.py module is responsible for preparing RenderJob and posts it on the manager queue.  
`src/emptycup` is the pure python based core library for backend, so I should examine the `core.py` to see how it creates and sends the Render requests in the manager queue.
These queues are maintained in the redis service defined at `docker-compose-dev.yml` (sicne I'm working on development environment). The core.py says that when `manager` is initialized with the `JobManager`, it reads reads two variables:

- queue_prefix
- cloud_prefix 

The cloud_prefix dictionary has no values for the `standard` and `preemptible` keys, as no cloud workers are specified in `docker-compose-dev.yml`.  
Therefore the `Jobmanager` is unable to spin up the cloud compute instance render worker to process the queue. This results into stucking at the `queued` stage. So,should I use the cloud workers used in production environement ?

2. #### **How does the render works ?**

`renders/` library of the core emptycup module
I am currently analysing this library in detail, I have now reached to a basic understanding:

- `blender_utils` uses the Blender python API that allows us to script and automate various tasks within Blender such as create and manipulate 3D objects, set up scenes, apply materials, control animations, and perform various other operations.
-  `blender` imports and uses `blender_utils`. For example, using blender_utils to call clear_scene() function before rendering the file present at request path (`requestp`). `blender` utilizes the command line arguments and requires the JSON file containing rendering parameters. These operations are executed in render workers which are Azure VMs.

-----
<br>

## **Friday: December 29**

### **System Freeze not fixed yet**
I have dual boot ubuntu running on my Dell G5 SE,  
Hardware configuration
- CPU: Ryzen 7 4800H with AMD Radeon Graphics
- GPU: Radeon RX 5600M 6 GiB
- System Memory: 16 GiB
- Display(s): laptop integrated screen
- Type of Diplay Connection: eDP

Few links supporting the system freeze.
- [Dell G5 SE freezing on any linux](https://www.reddit.com/r/DellG5SE/comments/qm0w52/every_linux_freezes_in_dell_g5_se/)
- [Intermittent freezes (flip_done timed out) since 5.10.21 on 4800H/RX 5600M (Dell G5 SE)](https://gitlab.freedesktop.org/drm/amd/-/issues/1707)

My machine freezes atleast 5 times a day due the the AMD RADEON RX 5600M GPU.  
The issue with this is the micro freeze caused by 5600m after waking up. It's clearly a kernal issue I'm facing, the kernal is buggy with AMD RX 5600M.
This has no solution on the internet till date, only ubuntu with kernel version 5.10.20 can run on the bare metal of DELL G5 SE. I'll fix this once I go home.

### **Code Investigation**
I'm on the top of a cliff, looking at the code blocks from top. I got a basic understanding about the code structure.  
- I want to render my 3D preview, but it's stuck on `queued`.
- I want to get renders but I don't have credits.

I've started examining the requests in Network tab. Preview is available in only 144px by default and it's a png image fetched from AzureCDN.  
If I try to render my project in any resolution without credits, then no request is sent to backend due to client side checks. Secondly, If I want to get free credits and render the image, I have to bypass the razorpay gateway and check how orders are created, maybe I can forge a request to create an order without passing through the payment gateway, so checking upon the `orders.py` may help.  
Reading the `renders.md`, I think if I have access to s3 bucket then can I add a render request in the render manager so that I'll be able to see the render in GUI ?

-----
<br>

## **Friday: December 22**

Kali Linux is not much compatible for development environment. I've tried to access the docs at `http://localhost:9999` but there were missing development dependencies therefore switched to Ubuntu upon Ab's directives.  
Deployed the web application on docker.

-----
<br>

## **Wednesday: December 20**
Setting up ecdocs and SSH access on my github account.



