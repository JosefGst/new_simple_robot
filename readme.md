# Simple Robot
**simple robot** is a differential drive robot  
## Resources
- [Turtlebot3](https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/)
## Launch Simulation World
`roslaunch simple_robot_simulation simple_world.launch` starts the simulation in Gazebo  
use `rosrun teleop_twist_keyboard teleop_twist_keyboard.py` to controll the robot manually with "ijkl,"
![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/simple_world.png)

## SLAM 
`roslaunch simple_robot_gmapping simple_robot_slam.launch` to start gmapping  
if you still have teleop running you can now move around and generate a map.
![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/gmapping.png)
## save map
PS: don't close gazebo and rviz before you haven't saved the map  
cd into folder where you want to save the map  
`rosrun map_server map_saver -f <map_name>`

## Navigation
close the SLAM node.  
the map and the world need to match, you can change the map with ,map_file:=$HOME/maps/map.yaml. With the path to the yaml file.
`roslaunch simple_robot_navigation simple_robot_navigation.launch map_file:=$HOME/maps/map.yaml`  
![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/navigation.png)
# Planar move
**planar move** simulates a mecanum wheel robot but currently rolling on balls  
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


## Resources
- [Gazebo/Fusion to navigation Youtube tutorial](https://www.youtube.com/watch?v=o7w7yv-Nros&list=PLFnCFnTZNyU8-omA_VFztWfeFn2gCyY4_)
- [Another Gazebo/Fusion to mapping Youtube tutorial](https://www.youtube.com/watch?v=cQh0gNfb6ro&list=PLXM8kq-f3YucvPdqchLU22WfUfjKCIqlO_)
- [Gazebo plugins](http://gazebosim.org/tutorials?tut=ros_gzplugins_)