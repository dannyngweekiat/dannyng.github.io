---
title: ROS Project
layout: default
parent: Robot Operating System (ROS)
nav_order: 3
---

## ROS Project

This section will cover the development of a ROS project. It will explain the steps involved in creating the projects. We will begin by creating a ROS workspace.

## Setup Tools

To ensure compatibility with ROS2 Python packages and eliminate warnings, it is recommended to use setup tools version 58.2.0, the last version known to work seamlessly. If your current version of setup tools is higher than 58.2.0, you will need to downgrade it. Execute the following command to perform the downgrade:

```bash
pip install setuptools==58.2.0
```

For more information about this solution, you can refer to [this link](https://answers.ros.org/question/396439/setuptoolsdeprecationwarning-setuppy-install-is-deprecated-use-build-and-pip-and-other-standards-based-tools/#400052){: target="_blank"}.

## ROS Workspace

If you have created the workspace, you can skip the steps below. Otherwise, follow the steps below to create a ROS workspace.

```bash
# Create a workspace directory
mkdir -p ~/ros2_ws/src
# Change directory to the workspace
cd ~/ros2_ws
```

Build the workspace.

```bash
# Build the workspace
colcon build --symlink-install
```

After building the workspace, you will be able to see the folders shown in the image below.

![Workspace Directory](/assets/images/ros/project/files.png)

Once succesfully build, there will be 4 workspace directories:

- build
- install
- log
- src

The "src" directory, which we created earlier, is where you will create your ROS packages. The "build" directory is where the build files will be stored. The "install" directory is where the installed files will be stored. Lastly, the "log" directory is where the log files will be stored.

## ROS Package

Let's create a ROS package called "turtle_controller". Make sure that you are in the source folder when running the command below. To create the package, run the following command:

```bash
ros2 pkg create --build-type ament_python --node-name turtle_driver turtle_controller
```

The command above will create package name **"turtle_controller"** with a node named **"turtle_driver"**.

---
[Previous]({{ site.baseurl }}{% link robot-operating-system/ros-basics.md %}) | [Next]({{ site.baseurl }}{% link robot-operating-system/publisher.md %})
