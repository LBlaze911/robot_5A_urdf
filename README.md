# robot_5A_urdf

# ROS2

## Sourcing

Source the setup files in your workspace:

. install/setup.bash

source /opt/ros/humble/setup.bash

source install/setup.bash


## Build

Always build in the top level of your workshop (ros2_ws):

colcon build –symlink-install


## Rosdep

Check missing dependencies:

rosdep install -i --from-path src --rosdistro humble -y


## YAML File

Path: 

‘Workspace’/install/’package’/share/’package’/config

## Rviz

Launch the moveo_urdf:

1st terminal: 	ros2 launch moveo_urdf rsp.launch.py

2nd terminal: 	ros2 run joint_state_publisher_gui joint_state_publisher_gui

3rd terminal: 	rviz2

<br/>

Launch the robot_5a_urdf:

1st terminal: 	ros2 launch robot_5a_urdf rsp.launch.py

2nd terminal: 	rviz2 -d src/robot_5a_urdf/view_robot.rviz

3rd terminal: 	ros2 run joint_state_publisher_gui joint_state_publisher_gui

4th terminal: 	ros2 launch gazebo_ros gazebo.launch.py

5th terminal:	ros2 run gazebo_ros spawn_entity.py -topic robot_description -entity robot_5a_urdf


## Gazebo

Launch empty world:

ros2 launch gazebo_ros gazebo.launch.py

<br />

Launch seesaw world:

gazebo /usr/share/gazebo-11/worlds/seesaw.world

## Git

Send to Github

git add --all *

git commit -a -m “”

git push


Sent to the computer:

git pull


## Ressource used

Ressources being used by the computer:

htop



## Launch urdf_example

ros2 launch urdf_example rsp.launch.py

rviz2 -d src/urdf_example/view_robot.rviz

ros2 run joint_state_publisher_gui joint_state_publisher_gui

ros2 launch gazebo_ros gazebo.launch.py

ros2 run gazebo_ros spawn_entity.py -topic robot_description -entity my_bot

ros2 launch urdf_example rsp_sim.launch.py

## fixer une position:

ros2 topic pub -l /set_joint_trajectory trajectory_msgs/msg/JointTrajectory ‘{header: {frame_id: world}, joint_names: [slider_joint, arm_joint], points: [  {positions: {0.8,0.6}} ]}’
 
## Camera

1st terminal: 	ros2 launch urdf_example rsp_sim.launch.py world:=~/test_world.world

2nd terminal: 	rviz2 -d src/urdf_example/view_robot.rviz

## Message type

Show the topics:

ros2 topic list

<br />

Find the type of the topics:

ros2 topic type {name of the topic}

<br />

Show the content of a message:

ros2 interface show {type of the topic}