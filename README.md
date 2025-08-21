# ZA-3201 – Stretch2

**Team T4 and Team T5 – Stretch2 Serving Waiter**

---

## Version

This documentation is written for the following system configuration:

| Descriptor | Version      |
| ---------- | ------------ |
| Model      | Stretch 2    |
| OS         | Ubuntu 20.04 |
| ROS        | Noetic       |
| Python     | Python3      |

Links:
[Start Guide](https://docs.hello-robot.com/0.2/stretch-tutorials/getting_started/quick_start_guide_re2/) || 
[Follow Joint Trajectory Commands](https://docs.hello-robot.com/0.2/stretch-tutorials/ros1/follow_joint_trajectory/) || 
[Stretch Demos](https://github.com/hello-robot/stretch_ros/tree/master/stretch_demos)

---

## Ubuntu Install of ROS Noetic

[Reference: ROS Noetic Installation Guide](https://wiki.ros.org/noetic/Installation/Ubuntu)

### Step 1 – Update Ubuntu

```bash
sudo apt update && sudo apt upgrade -y
```

```bash
sudo apt install build-essential curl git
```

### Step 2 – Install ROS Noetic Desktop Full

```bash
sudo sh -c 'echo "deb https://ftp.osuosl.org/pub/ros-ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
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

### Step 3 – Setup ROS environment

```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
```

```bash
source ~/.bashrc
```

### Step 4 – Install ROS build tools

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

---

## Installing and Configuring Your ROS Workspace

[Reference: Installing and Configuring ROS Environment](https://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment)

### Create and build a catkin workspace

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```

```bash
source devel/setup.bash
```

Append this line to your `~/.bashrc`:

```bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```

Then reload bashrc:

```bash
source ~/.bashrc
```

### Verify workspace overlay

```bash
echo $ROS_PACKAGE_PATH
# Expected output: /home/youruser/catkin_ws/src:/opt/ros/noetic/share
```

---

## Clone Stretch2 ROS Packages

```bash
cd ~/catkin_ws/src
```

```bash
git clone https://github.com/hello-robot/stretch_ros -b melodic
```

```bash
git clone https://github.com/pal-robotics/realsense_gazebo_plugin -b melodic-devel
```

```bash
cd ~/catkin_ws
catkin_make
```

```bash
source devel/setup.bash
```

---

## Install Required ROS Packages

### 1. Update system and package lists

```bash
sudo apt-get update
```

### 2. Install core ROS packages

```bash
sudo apt install ros-noetic-ros-control ros-noetic-ros-controllers
```

```bash
sudo apt install ros-noetic-teleop-twist-keyboard
```

```bash
sudo apt install ros-noetic-navigation
```

### 3. Install Gazebo and ROS integration

```bash
sudo apt install gazebo11 ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control
```

```bash
sudo apt install ros-noetic-gazebo-ros
```

### 4. Install MoveIt for motion planning

```bash
sudo apt install ros-noetic-moveit
```

### 5. Install Realsense support

```bash
sudo apt-get install ros-noetic-realsense2-description
```

```bash
sudo apt-get install ros-noetic-librealsense2
```

### Rebuild workspace after installing packages

```bash
cd ~/catkin_ws
catkin_make
```

```bash
source devel/setup.bash
```

---

## Modify `publish_ground_truth_odom.py` for Python 3

1. Navigate to the script folder

```bash
cd ~/catkin_ws/src/stretch_ros/stretch_gazebo/scripts
```

2. Open the script in a text editor

```bash
nano publish_ground_truth_odom.py
```

3. Change the first line from (`python` → `python3`):

```python
#!/usr/bin/env python
```

to:

```python
#!/usr/bin/env python3
```

4. Save and exit (`Ctrl+S` → `Ctrl+X`)

---

## Launching the Robot Simulation

[Reference: Running Gazebo with MoveIt! and Stretch](https://docs.hello-robot.com/0.2/stretch-tutorials/ros1/moveit_basics/)

### 1. Launch Gazebo simulation

```bash
roslaunch stretch_gazebo gazebo.launch
```

### 2. Launch MoveIt demo in Gazebo

```bash
roslaunch stretch_moveit_config demo_gazebo.launch
```

---
