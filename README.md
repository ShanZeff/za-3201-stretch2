# ZA-3201-Stretch2
Team T4 and Team T5 Stretch2 Serving Waiter

# Version
This is a Stretch2 User Documentation. It is written with the following system configuration in mind:
| Descriptor                             | Version                                           |
| -------------------------------------- | ------------------------------------------------- |
Model | Stretch 2
OS | Ubuntu 20.04
ROS | ROS Noetic
Python | Python3

# Ubuntu install of ROS Noetic
The primary testing framework being used within *stretch_ros* is pytest. Pytest is an open source testing framework that scales well and takes a functional approach resulting in minimal boiler plate code. First we should ensure that pytest is installed and up to date:

```bash
>>$ pip3 install -U pytest
>>$ pytest --version
pytest 6.2.4
```

```bash

```

DIVIDER
Step 1 – Update system
Once Ubuntu is running:
```bash
sudo apt update && sudo apt upgrade -y
```
```bash
sudo apt install build-essential curl git
```
Step 2 – Install ROS Noetic Desktop Full
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
```bash
sudo apt install curl -y
```
```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

# Installing and Configuring Your ROS Environment
