# Task of smart method training
## task Ai 
### Step 1
***open terminal:***
## Install Dependent ROS Packages
$ $ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
$sudo apt install ros-noetic-hls-lfcd-lds-driver
$ sudo apt install ros-noetic-dynamixel-sdk
$ sudo apt install ros-noetic-turtlebot3-msgs
$ mkdir -p ~/catkin_ws/src
$cd catkin_ws/src
$git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.get
$git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations
$cd ~/catkin_ws &&catkin_make
## Operate Gazebo & Teleop Turtlebot 3
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
$export TURTLEBOT3_MODEL=burger
$roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
## SLAM & Save the map
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch
$ export TURTLEBOT3_MODEL=burger
$roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
$ rosrun map_server map_saver -f ~/map

![slam](https://user-images.githubusercontent.com/79949101/183309956-677d6711-a628-4fc3-b477-52548498b574.jpg)
## Launch Navigation
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
***Click the 2D Pose Estimate button in the RViz menu.***
![Screenshot 2022-08-07 233605](https://user-images.githubusercontent.com/79949101/183310085-03c75ba7-2ce5-4052-b116-7bf443e960db.jpg)
