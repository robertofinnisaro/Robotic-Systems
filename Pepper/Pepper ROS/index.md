---
title: "Setting up ROS with to Pepper"
date: 2024-01-17T09:00:00-00:00
draft: false
cover:
    image: img/Pepper-ros.jpg
    alt: "Pepper Robot"
    caption: "Pepper Robot"
    hidden: true
    hiddenInSingle: true
summary: "\"This is a short  guide to setting up Pepper with ROS.\""
tags: ["ROS", "Pepper", "Robotics"]
---

## Introduction to Pepper and ROS

This guide assumes that ROS has already been installed on your workstation PC.
To set started, you need to ensure that additional packages are installed.
Some of these packages may already be installed but it is worth the check.

## Dependencies

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

If you followed the [ROS installation guide](/ros-installation-guide.md) you should already have your catkin package sourced but double check by looking into the `~/.bashrc`:

```bash
cat ~/.bashrc | grep catkin
```

This line should be returned: 

```bash
source ~/catkin_ws/devel/setup.bash
```

If not then make sure that it is added to the `~/.bashrc`.

```bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

You can then connect to your robot by running:

```bash
roslaunch naoqi_driver naoqi_driver.launch nao_ip:=<yourRobotIP>  [network_interface:=<eth0|wlan0|vpn0>] [username:=<name>] [password:=<passwd>]
```

## Pepper and Python

Now that Pepper is fully integrated with ROS, it is time to look at launching a python version of Pepper. Python is one of the chosen languages to control robotic systems using ROS. For this to work, you will need to find the official NAOqi SDK.

After this you need to install the Pepper bring-up package but in order to execute the python bridge you will need to run the following command: 

```bash
roslaunch pepper_bringup pepper_full_py.launch nao_ip:=<RobotIP> roscore_ip:=<roscoreIP>
```

If you do not have `pepper_bringup` then this can be installed by running:

```bash
sudo apt-get install ros-$ROS_DISTRIB-pepper-.*
```

## Running RVIZ with Pepper

When using ROS, one of the best tools at your disposal is RVIZ. 
RVIZ is in installed with ROS and so to run RVIZ simply ensure that your `setup.bash` is sourced before running:

```bash
rosrun rviz rviz
```

This is the basic launch for RVIZ without any configuration file. 
To get a custom configuration file loaded to work with Pepper, it can be found in the catkin workspace.
The pre-defined RVIZ configuration shows the basic displays for Pepper such as the TF, RobotModel, Camera, LiDARs and Sonars. 
You can load it through the tool bar at the location below:

```bash
~/catkin_ws/src/pepper_robot/pepper_description/config/pepper.rviz
```