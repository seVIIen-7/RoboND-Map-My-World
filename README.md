# Map My World
In this project, a 2D occupancy grid and 3D octomap from a simulated environment using your own robot with the [RTAB-Map package](http://wiki.ros.org/rtabmap_ros). There are 3 nodes.
1. Mapping Node
2. RTABMAP Visulization Node
3. [Teleop Node](https://github.com/ros-teleop/teleop_twist_keyboard)

## Testing 
First, launch the Gazebo world and RViz, spawn the robot in the environment:
```
$ cd catkin_ws
$ catkin_make
$ source devel/setup.bash
$ roslaunch my_robot world.launch
```
Then, launch the teleop node:
```
$ cd catkin_ws
$ source devel/setup.bash
$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
Finally, launch the mapping node:
```
$ cd catkin_ws
$ source devel/setup.bash
$ roslaunch my_robot mapping.launch
```
Navigate the robot in the simulation to create map for the environment! When all are set, terminal the node and the map db file can be found in the place specified in the launch file. If you did not modify the argument, it will be located in the /root/.ros/ folder.

Then, open a new terminal and analyse the databse by:
```
$ rtabmap-databaseViewer ~/.ros/rtabmap.db
```
Once open, add some windows to get a better view of the relevant information, so:
- Say yes to using the database parameters
- View -> Constraint View
- View -> Graph View
