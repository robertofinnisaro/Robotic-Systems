---
title: "ROS Installation"
date: 2023-02-05T00:49:36Z
draft: false
---

This is a guide on how to install ROS-Noetic
It is recommended to use Ubuntu 16.04, 18.04 or 20.04 as the base operating system for ROS to be installed on.
In this guide it will run through how to download and install ROS assuming that Ubuntu 20.04 is used.

# Overview
Depending on the Ubuntu version that is used will depend on the installation of ROS that can be installed on the operating system.
For the likes of Ubuntu 20.04, the ROS version used is ROS-Noetic-Niniemys, this version of ROS will be supported until 2025.
Once booted into your operating system open up a terminal 
```bash
Ctrl + Alt + T
```

# ROS Installation
## 1.0 System Update
When the terminal has loaded make sure that the system is up-to-date but running:
```bash 
sudo apt update && sudo apt upgrade
```

Once the system has upgraded follow up by removing any unnecessary packages from your system:
```bash
sudo apt autoremove
```

## 1.1 Setting up ROS
Now that your system is setup, it is time to install the necessary packages for ROS.
To make sure that your system can accept packages from packages.ros.org the system needs to allow software from this location,
to do so run:
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

Next, it is time to set up the correct keys for ROS:
```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

## 1.2 ROS installation
Now that the system is set-up and configured for ROS, the installation process can now be undertaken.
To install ROS the following command is used:
```bash
sudo apt install ros-noetic-desktop-full
```

This will install everything for ROS including **RQT**, **RVIZ**, **2D/3D simulators**

## 1.3 ROS Environment
To use ROS, this script must be used to tell the terminal where to look for the ROS installation and so that any installed packages can be used.
This script must be run in every new terminal session.
```bash
source /opt/ros/noetic/setup.bash
```

It is possible to source the terminal with the ROS installation on each new terminal session but updating the `~/.bashrc`.
This can be done automatically but running the following once:
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

To check that this has been appended into the `~/.bashrc` correctly run the following:
```bash
cat ~/.bashrc
```

Where at the end of the `~/.bashrc` will output:
```bash
source /opt/ros/noetic/setup.bash
```

## 1.4 Building Dependencies for Packages
To make ROS compatible with some terminal applications and programs, some dependencies need to be installed: 
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

### 1.4.1 Initialsing rosdep
Before ROS tools can be used, rosdep needs to be initalised which allows you to install system dependencies for source.
To initalise rosdep as follows:
```bash
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
```

# Environment Setup
## 2.0 Setting up an Environment
Now that ROS has been installed and configured on your system it is now time to set up an environment where you will be able to do development.
To make packages for ROS they need to be initialised inside of a workspace which can be created by:
```bash
mkdir -p ~/catkin_ws/src
```

## 2.1 Building the Environment
Once the directory has been created move to the directory and then build the folder. This will be used anytime you make dependency changes to your packages located in this workspace or when you create new packages.
```bash
cd catkin_ws && catkin_make
```

## 2.2 Sourcing the Environment
Now that the workspace has been built, in order for the terminal and ROS to see the packages that will be created inside of this workspace; the workspace needs to be sourced back to the current terminal session. To do this manually for each session:
```bash
source ~/catkin_ws/devel/setup.bash
```

This will need to be run for **every** new terminal session.
This process can be made automatic but appending this into your `~/.bashrc` so that the workspace will be initalised for every new terminal session automatically.
```bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```

This command only needs to be run.
To check that this has been appended into the `~/.bashrc` correctly run the following:
```bash
cat ~/.bashrc
```

Where at the end of the `~/.bashrc` will output:
```bash
source ~/catkin_ws/devel/setup.bash
```