# install-and-Simulate-the-TurtleBot3

## Table of Contents:
- install TurtleBot3 packages
- Install Turtlebot 3 Simulator
- Simulate TurtleBot3
- SLAM

## install TurtleBot3 packages
Before installing  TurtleBot3 packages , make sure to make the following tow commands:

`sudo apt update`

` sudo apt upgrade`

Then , do the following :

`cd ~/catkin_ws/src/`

`sudo apt-get install ros-melodic-dynamixel-sdk`

` sudo apt-get install ros-melodic-turtlebot3-msgs`

` sudo apt-get install ros-melodic-turtlebot3`

`sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers `
  
  `cd ~/catkin_ws && catkin_make`
  
  TurtleBot3 has three models, Burger, Waffle, and Waffle Pi, so you have to set which model you want to use before you launch TurtleBot3. Type this command to open the bashrc file to add this setting:
  
  `gedit ~/.bashrc`
  
  Add this line at the bottom of the file:

export TURTLEBOT3_MODEL=burger

Save the file and close it.

Now reload .bashrc so that you do not have to log out and log back in.

`source ~/.bashrc`


## Install Turtlebot 3 Simulator

After the correct compilation of the catkin_ws , can download and instalation the simlation packages 

`cd ~/catkin_ws/src/`

`git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git`

`cd ~/catkin_ws && catkin_make`

## Simulate TurtleBot3

Now that we have the TurtleBot3 simulator installed, let’s launch the virtual robot with different environments . 

for Empty World :

`roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch`

for TurtleBot3 World:

`roslaunch turtlebot3_gazebo turtlebot3_world.launch`

for TurtleBot3 House :

`roslaunch turtlebot3_gazebo turtlebot3_house.launch`

for Operate TurtleBot3 :

launch the teleoperation node with below command in a new terminal window

`roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`

## SLAM


The SLAM (Simultaneous Localization and Mapping) is a technique to draw a map by estimating current location in an arbitrary space. 
When SLAM in Gazebo simulator, you can select or create various environments and robot models in virtual world. Other than preparing simulation environment instead of bringing up the robot, SLAM Simulation is pretty similar to that of SLAM with the actual TurtleBot3.
  
  ### Launch Simulation World
  
  `roslaunch turtlebot3_gazebo turtlebot3_world.launch`
  
  ### Run SLAM Node
  
  Open a new terminal from Remote PC with Ctrl + Alt + T and run the teleoperation node from the Remote PC
  
  ` roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`
  
  ### Run Teleoperation Node
  
  Open a new terminal from Remote PC with Ctrl + Alt + T and run the teleoperation node from the Remote PC.
  
  `roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`
  
  ### Save Map
  
  When the map is created successfully, open a new terminal from Remote PC with Ctrl + Alt + T and save the map
  
  `rosrun map_server map_saver -f ~/map`
  
