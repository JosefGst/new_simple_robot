# Simple Robot
**simple robot** is a differential drive robot devoeloped on ROS melodic.  
Current sensors used are:
- Wheel Encoders
- LIDAR
- IMU
## Resources
- [Turtlebot3](https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/)
## Launch Simulation World
starts the simulation in Gazebo  
`roslaunch simple_robot_simulation simple_world.launch`   
use  
`rosrun teleop_twist_keyboard teleop_twist_keyboard.py`  
to controll the robot manually with "ijkl,"  
or try  
`roslaunch simple_robot_gmapping simple_robot_slam.launch slam_methods:=explore`  
for autonomous exploration

![alt text](https://github.com/JosefGst/new_simple_robot/blob/2022/images/simple_world.png)

## SLAM 
to start gmapping  
`roslaunch simple_robot_gmapping simple_robot_slam.launch`  
if you still have teleop running you can now move around and generate a map.

![alt text](https://github.com/JosefGst/new_simple_robot/blob/2022/images/gmapping.png)
## save map
PS: don't close gazebo and rviz before you haven't saved the map  
cd into folder where you want to save the map  
`rosrun map_server map_saver -f <map_name>`

## Navigation
close the SLAM node.  
the map and the world need to match, you can change the map with ,map_file:=$HOME/maps/map.yaml. With the path to the yaml file.  
`roslaunch simple_robot_navigation simple_robot_navigation.launch map_file:=$HOME/maps/map.yaml` 

![alt text](https://github.com/JosefGst/new_simple_robot/blob/2022/images/navigation.png)
# Planar move
**planar move** should simulates a mecanum wheel robot but currently sliding on balls, however the working is the same. 
![alt text](https://github.com/JosefGst/new_simple_robot/blob/2022/images/gazebo.png)
## gmapping
you can change the world in the **gazebo.launch** file and run  
`roslaunch planar_move_gmapping gmapping.launch`   
click the terminal where the teleop key runs and move the robot around with "ijkl,"

![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/mapping.png)

## save map
PS: don't close gazebo and rviz before you haven't saved the map  
cd into folder to save the map  
`rosrun map_server map_saver -f battlefield`

![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/map.png)

## Navigation
the map and the world need to match, you can change the map in the **navigation.launch** file and run  
`roslaunch planar_move_navigation navigation.launch`

## move to navigation goal
move to a single goal which is hardcoded in the simple_navigation_goals.py file.   
`roscd simple_robot_move2goal/scripts/`  
`python simple_navigation_goals.py`  
  
move to several locations sequantually, specified in the launch file as "p_seq">[x,y,z,...]
`roslaunch simple_robot_move2goal movebase_seq.launch`

## Resources
- [Gazebo/Fusion to navigation Youtube tutorial](https://www.youtube.com/watch?v=o7w7yv-Nros&list=PLFnCFnTZNyU8-omA_VFztWfeFn2gCyY4_)
- [Another Gazebo/Fusion to mapping Youtube tutorial](https://www.youtube.com/watch?v=cQh0gNfb6ro&list=PLXM8kq-f3YucvPdqchLU22WfUfjKCIqlO_)
- [Gazebo plugins](http://gazebosim.org/tutorials?tut=ros_gzplugins_)
- [move to navigation goals](https://hotblackrobotics.github.io/en/blog/2018/01/29/seq-goals-py/_)