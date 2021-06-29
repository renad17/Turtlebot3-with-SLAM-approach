# Turtlebot3-with-SLAM-approach

Install Dependent ROS 1 Packages:

$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
  
 Install TurtleBot3 Packages:
  
$ sudo apt-get install ros-melodic-dynamixel-sdk

$ sudo apt-get install ros-melodic-turtlebot3-msgs

$ sudo apt-get install ros-melodic-turtlebot3

Set TurtleBot3 Model Name:

$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc

create and build a catkin workspace:

$ mkdir -p ~/catkin_ws/src

$ cd ~/catkin_ws/

$ catkin_make

Install Simulation Package:

$ cd ~/catkin_ws/src/

$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

$ cd ~/catkin_ws && catkin_make

TurtleBot3 World:

$ export TURTLEBOT3_MODEL=waffle

$ source devel/setup.bash

$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

Run SLAM Node:

$ source devel/setup.bash

$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

Run Teleoperation Node:

$ source devel/setup.bash

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

save map:

$ rosrun map_server map_saver -f ~/map
