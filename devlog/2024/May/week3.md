---
layout: default
title: Week 17
---

# **May Week 3**
## **Wednesday: May 15**
- 11:00 AM: Signed In.
- 12:00 PM: Re-installed windows 11, deleted all the partitions. Now I have 3 partitions of 500 Gib each. One is reserved for docker and WSL distros.
- 1:00  PM: Updated the BIOS to latest version, clean install of all graphic drivers, updated windows to latest version. Installed Blender 3.2.2 GUI in windows. Installed MySQL workbench. Machine is development ready.
- 2:00  PM: Installed docker-desktop for windows through PowerShell Invoke-WebRequest method to make it install in a non-system drive.
- 4:00  PM: Trying to deploy the web application in **Ubuntu-24.04** LTS but seems like it has python 3.12 installed by default which doesn't support the package distutils.
- 6:00  PM: Deployed the web application on **Ubuntu-22.04@WSL2**. (Python-3.10 supports distutils module).
            Exported the distro (Ubuntu-22.04) as a tarball so as to use as a snapshot for clean install in emergency.
