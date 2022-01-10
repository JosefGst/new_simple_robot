# gmapping
you can change the world in the **gazebo.launch** file  
run  
`roslaunch simple_robot_description gmapping.launch`  
click the terminal where the teleop key runs and move the robot around with "ijkl,"

# save map
cd into folder to save the map  
`rosrun map_server map_saver -f turtle_home_map`

# SLAM navigation
the map and the world need to match, you can change the map in the **navigation.launch** file
`roslaunch simple_robot_description navigation.launch`