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
[reference](https://wiki.ros.org/noetic/Installation/Ubuntu)
#### Step 1 – Once Ubuntu is running:
```bash
sudo apt update && sudo apt upgrade -y
```
```bash
sudo apt install build-essential curl git
```
#### Step 2 – Install ROS Noetic Desktop Full
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
```bash
sudo apt install curl -y
```
```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
```bash
sudo apt update
```
```bash
sudo apt install ros-noetic-desktop-full -y
```
#### Step 3 – Setup environment
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
```
```bash
source ~/.bashrc
```
#### Step 4 – Install ROS build tools
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
```bash
sudo apt install python3-rosdep
```
```bash
sudo rosdep init
```
```bash
rosdep update
```

# Installing and Configuring Your ROS Environment
[reference](https://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment)
#### Let's create and build a catkin workspace:
```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```
```bash
source devel/setup.bash
```
#### To make sure your workspace is properly overlayed by the setup script, make sure ROS_PACKAGE_PATH environment variable includes the directory you're in.
```bash
$ echo $ROS_PACKAGE_PATH
/home/youruser/catkin_ws/src:/opt/ros/noetic/share
```
