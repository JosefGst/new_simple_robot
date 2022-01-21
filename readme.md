**simple robot** is a differential drive robot  
**planar move** simulates a mecanum wheel robot but currently rolling on balls  

![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/gazebo.png)

# gmapping
you can change the world in the **gazebo.launch** file and run  
`roslaunch simple_robot_description gmapping.launch`   
or  
`roslaunch planar_move_gmapping gmapping.launch`   
click the terminal where the teleop key runs and move the robot around with "ijkl,"

![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/mapping.png)

## save map
PS: don't close gazebo and rviz before you haven't saved the map  
cd into folder to save the map  
`rosrun map_server map_saver -f battlefield`

![alt text](https://github.com/JosefGst/new_simple_robot/blob/master/images/map.png)

# SLAM navigation
the map and the world need to match, you can change the map in the **navigation.launch** file and run  
`roslaunch simple_robot_description navigation.launch`   
or   
`roslaunch planar_move_navigation navigation.launch`


# Sources
- [Gazebo/Fusion to navigation Youtube tutorial](https://www.youtube.com/watch?v=o7w7yv-Nros&list=PLFnCFnTZNyU8-omA_VFztWfeFn2gCyY4_)
- [Another Gazebo/Fusion to mapping Youtube tutorial](https://www.youtube.com/watch?v=cQh0gNfb6ro&list=PLXM8kq-f3YucvPdqchLU22WfUfjKCIqlO_)
- [Gazebo plugins](http://gazebosim.org/tutorials?tut=ros_gzplugins_)