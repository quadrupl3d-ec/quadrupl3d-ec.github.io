---
layout: default
title: Week 1
---

# **December Week 1**
## **Wednesday: December 20**
Setting up ecdocs and SSH access on my github account.

-----
<br>

## **Friday: December 22**

Kali Linux is not much compatible for development environment. I've tried to access the docs at `http://localhost:9999` but there were missing development dependencies therefore switched to Ubuntu upon Ab's directives.  
Deployed the web application on docker.

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
