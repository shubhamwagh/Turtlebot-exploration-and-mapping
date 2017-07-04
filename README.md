# Turtlebot-exploration-and-mapping
Autnomous Robotics module UdG Final Project

# Installation

Save this package into catkin_ws/src/.

Turtlebot-exploration-and-mapping contains two packages :
1) control_turtlebot
2) final_project

1) control_turtlebot package : /src/controller_turtlebot.py -> make this executable file
2) final_project package : /scripts/mapping.py and /scripts/control.py -> make these files executable.


AS we need to save the start position of the robot, we do this by saving into text file
1) final_project package : check control.py -> line 467 -> for text file writing path to avoid errors.
2) control_turtlebot package : check offline_planner_R2.cpp -> line 395 -> for text file reading path to avoid errors.

Once all the above steps are taken care of 
catkin_make can be done
Commands to execute the code successfully

1) roslaunch control_turtlebot start_turtlebot_modules.launch
2) roslaunch control_turtlebot start_turtlebot_mapping_planning_control.launch explore_time:=(time in seconds given by user)


Once exploration is completed until given user time

3) rosservice call /controller_turtlebot/start_finding_path "start: true"  ---> finds the path back to initial position
4) rosservice call /controller_turtlebot/ready_to_go "start: true"    ----> for thr robot to move towards initial position



Video link - https://www.youtube.com/watch?v=CU55TZUhDv4&t=4s

