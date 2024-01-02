---
layout: default
title: Week 1
---
# **January Week 1**
## **Tuesday: January 2**  

### **System Freeze fixed**  
Upon setting the kernel parameter to `amdgpu.runpm=0` will keep the GPU on at all times and it won't go to sleep abruptly but this drains the battery life. Till date this is the only patch this issue has. So, I will implement a stable fix in future.  

System works very smooth now. No hangs, no freezes and no modifications in the kernel version.

### **Deciphering the render functionality**
1. #### **`Try Preview` stuck at queued**
Upon going through the docs/docs/renders.md, I get to know that core.py module is responsible for preparing RenderJob and posts it on the manager queue.  

