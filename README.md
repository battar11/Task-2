# Task-2
First we need to install ROS1 on PC remote Open the terminal and enter below commands 

$ sudo apt update 

$ sudo apt upgrade

$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh 

$ chmod 755 ./install_ros_melodic.sh $ bash ./install_ros_melodic.sh

after that install dependent ROS one packages by these commoand:

$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy/
ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc/
ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan/
ros-melodic-rosserial-arduino ros-melodic-rosserial-python/
ros-melodic-rosserial-server ros-melodic-rosserial-client/
ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server/
ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro/
ros-melodic-compressed-image-transport ros-melodic-rqt*/
ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers

now we need to install TruleBot3 using debian Packages

 $ sudo apt-get install ros-melodic-dynamixel-sdk 
 
 $ sudo apt-get install ros-melodic-turtlebot3-msgs 
 
 $ sudo apt-get install ros-melodic-turtlebot3 
 
 $ cd ~/catkin_ws/src/ 
 
 $ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git 
 
 $ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git 
 
 $ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git 
 
 $ cd ~/catkin_ws && catkin_make 
 
 $ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
 
then Set TurtleBot3 Model Name $ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc

$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc

after that we need to install gazebo and SLAM Simulation pakeages so first we will do gazebo Simulation Install Simulation Package 
$ cd ~/catkin_ws/src/ 

$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git 

$ cd ~/catkin_ws && catkin_make then $ export TURTLEBOT3_MODEL=waffle

$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

now we will install SLAM Simulation
$ export TURTLEBOT3_MODEL=burger 

$ roslaunch turtlebot3_gazebo turtlebot3_world.launch then 

$ export TURTLEBOT3_MODEL=burger 

$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

$ export TURTLEBOT3_MODEL=burger 

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

it will open gazebo and RViz and you can work in the map Also, by last command you can control robots by (w-s-x-a-d) to make move on around the map.

to save the map use this command >> $ rosrun map_server map_saver -f ~/map
