---
layout: default
title: Week 1
---

# December Week 1
## Wednesday: December 20

Connected with sir @Ab and received the credentials of the newly created gmail account.  
Gmail - `quadrupl3d@gmail.com` 

### 1. Dual boot Kali Linux 2023.4 (Bare Metal).  
Steps to perform a dual boot to install the bare metal:
- Download the ISO file from the official website and use Rufus to create an installation media
- Create 150 GB of unallocated / free space using windows disk manager.
- Restart the laptop
- Press F12 to enter boot menu (DELL G5 SE 5505)
- Disable secure boot.
- Select the “Generic Flash Disk”
- Use graphical install to proceed further.
- Guided partitioning - use the largest continuous free space
- Uncheck “xfce”, “KDE Plasma”, “Desktop environment” in the section “Softwares to install”.
- Time to boot into the newly created OS.

### 2. Login to gmail using quadrupl3d@github.in

### 3. Create a Github account.
### 4. Setup SSH access to github account.
- Creating SSH keys for the newly installed Kali Linux

      ssh-keygen -t rsa -b 4096 -C "quadrupl3d@emptycup.in"

- Make sure that the permissions of id_rsa are correct, otherwise it won't work with full permissions.

      chmod -R 600 id_rsa

- Now add the SSH key to github account and test the connection.

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/687e260d-d166-450c-a1ff-765bb7c9b821)


### 5. Setup Worklog.
- Create a new repository called "quadrupl3d-ec.github.io" (Github Pages)
- Clone Ab's starter branch
  
       git clone --branch starter git@github.com:ab-emptycup/ab-emptycup.github.io.git


- In the local repository (ab-emptycup.github.io), update the remote URL to point to newly created repository:

      git remote set-url origin git@github.com:quadrupl3d-ec/quadrupl3d-ec.github.io.git

- Switch to main branch
  
       git checkout main
- Push the modified version of forked repo.
  
      git push origin main
  <br>
-----

