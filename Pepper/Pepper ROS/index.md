---
title: "Setting up ROS with to Pepper"
date: 2024-01-17T09:00:00-00:00
draft: false
cover:
    image: img/pepper-ros.jpg
    alt: "Pepper Robot"
    caption: "Pepper Robot"
    hidden: true
    hiddenInSingle: true
summary: "\"This is a short  guide to setting up Pepper with ROS.\""
tags: ["ROS", "Pepper", "Robotics"]
---

This guide assumes that ROS has already been installed on your workstation PC.
To set started, you need to ensure that additional packages are installed.
Some of these packages may already be installed but it is worth the check.

The packages required are: `naoqi_libqi`, `naoqi_libqicore` and `naoqi_bridge_msgs` and these can be installed by the following:

```bash
sudo apt-get install naoqi_libqi naoqi_libqicore naoqi_bridge_msgs
```
These packages can be built from source but `apt-get` is recommenced. 
If you want to build from source, you can do the following.

Change directory into your ROS workspace.

```bash
cd ~/caktin_ws/src
```

Afterwards you will need to clone the repository:

```bash
git clone https://github.com/ros-naoqi/naoqi_driver.git
```

Make sure that you have all of the dependicies installed with the package:

```bash
rosdep install -i -y --from-paths ./naoqi_driver
```

To build the package you can then run these commands:

```bash
source /opt/ros/$ROS_DISTRIB/setup.sh
cd ~/catkin_ws && catkin_make
```

If you followed the [ROS installation guide]()