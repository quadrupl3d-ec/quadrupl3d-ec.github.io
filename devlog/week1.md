---
layout: default
title: Week 1
---

# **December Week 1**
## **Wednesday: December 20**

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

-----
<br>

## **Friday: December 22**

Kali Linux is not much compatible for development environment. I've tried to access the docs at `http://localhost:9999` but there were missing development dependencies therefore switched to Ubuntu upon Ab's directives.  

### 1. Dual boot Ubuntu LTS 22.04.3 (Bare Metal).  
### 2. Trying to deploy the web application to Docker containers.
- Now that we have the EmptyCup docs setup at `localhost:9999`, we have to install docker-desktop GUI application on ubuntu,
Docker-desktop installation for [ubuntu](https://docs.docker.com/desktop/install/ubuntu/)

For non-Gnome Desktop environments, **gnome-terminal must be installed**:

      sudo apt install gnome-terminal


  
Download latest [DEB package](https://desktop.docker.com/linux/main/amd64/docker-desktop-4.26.1-amd64.deb?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-linux-amd64&_gl=1*daj8tt*_ga*NDgzOTI5LjE3MDMyNTA3ODM.*_ga_XJWPQMJYHQ*MTcwMzMwOTgxOC40LjEuMTcwMzMxMDI4Mi42MC4wLjA.)

Install docker-desktop

      sudo apt-get install ./docker-desktop-<version>-<arch>.deb
            
- Install Docker Engine on Ubuntu on Ubuntu Jammy 22.04 (LTS)

Run the following command to **uninstall all conflicting packages**:

      for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.
      
1. **Set up Docker's apt repository**.

            # Add Docker's official GPG key:
            sudo apt-get update
            sudo apt-get install ca-certificates curl gnupg
            sudo install -m 0755 -d /etc/apt/keyrings
            curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
            sudo chmod a+r /etc/apt/keyrings/docker.gpg
            
            # Add the repository to Apt sources:
            echo \
              "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
              $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
              sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
            sudo apt-get update

            
2. **Install the Docker packages**.

         sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
  
3. **Verify that the Docker Engine installation is successful by running the hello-world image**.

          sudo docker run hello-world

You have now successfully installed and started Docker Engine !

Upon checking the docker context, you will find two docker engines: `default` and `desktop-linux` respectively.  

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/c9af6950-a8a2-4389-af99-c39449d608a3)


The GUI application contains the same two builders, `ecrebuild` and `ecstart` must be executed with the same engine used by the GUI application **otherwise your container will not be visible in the GUI application**.

In our case, we will using the newly-installed `desktop-linux` engine.

- Make sure to add the path `/var/www/emptycup/emptycup3d` under the `Settings -> Resouces -> File Sharing`

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/66c86441-a7c4-4650-9e6c-6a7222b8d619)

- Since the GUI application is launched with the normal user privileges, therefore **change the ownership of the emptycup3d folder to the currently logged-in user**:

       sudo chown -R username:username /var/www/emptycup/emptycup3d

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/53363778-9135-4f37-af25-381b60b26386)

- **Time to build the empire**.

       ecrebuild

- **Start the containers**
  
       ecstart

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/d287e1cc-eeb6-4888-a57e-8aa5ce599b5e)

### [+] Deployment succeeded.

- Check `localhost:3000/` to see the `emptycup3d_webapp` is working or not.
- Confirm the installation by checking the bind mounts.

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/be07b512-07eb-4b54-8469-d8d515190e69)

If you encounted logs like below, then manually create the `nonexistent` directory and restart the container.

![image](https://github.com/quadrupl3d-ec/quadrupl3d-ec.github.io/assets/154422664/a143c148-b135-4cf1-9816-e3c680bce5f4)
<br>
  
----

### If the `desktop-linux` engine does'nt works at first glance

- Completely remove the `docker-desktop` and the `cli` engine from your system

      # Stop all running containers. (in case if you have used the default docker engine)
      docker stop $(docker ps -q)

      # Remove all containers, including those that are stopped.
      docker rm $(docker ps -aq)

      # remove the images associated with the containers
      docker rmi $(docker images -q)

      sudo service docker stop
      sudo apt-get purge docker-ce docker-ce-cli containerd.io
      sudo rm -rf /var/lib/docker
      sudo apt-get autoremove
      sudo apt-get update

- Don't remove the docker's GPG key and anything from apt sources.list.d
- Now reinstall the [DEB package](https://desktop.docker.com/linux/main/amd64/docker-desktop-4.26.1-amd64.deb?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-linux-amd64&_gl=1*daj8tt*_ga*NDgzOTI5LjE3MDMyNTA3ODM.*_ga_XJWPQMJYHQ*MTcwMzMwOTgxOC40LjEuMTcwMzMxMDI4Mi42MC4wLjA.)
  
- Use the `desktop-linux` engine and execute `rebuild` and `ecstart`.
- It is guaranteed to work now.



