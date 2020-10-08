### 1. installation and build the file

install dependent packages
```
sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan ros-melodic-rosserial-arduino ros-melodic-rosserial-python ros-melodic-rosserial-server ros-melodic-rosserial-client ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro ros-melodic-compressed-image-transport ros-melodic-rqt-image-view ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers

```

install gazebo_ros_control
```
sudo apt-get install ros-melodic-gazebo-ros-pkgs ros-melodic-gazebo-ros-control
```
down load source file
```
git clone https://github.com/kaistcapstone/capstone2_ROS_gazebo
```
build the code
```
cd ~/capstone1_ROS_gazebo
catkin_make
```


### 2. running the code

map open
```
roslaunch map_generate import_world.launch
```
swapn the robot
```
roslaunch turtlebot3_description spawn_turtlebot3.launch
```
launch the controller_manager
```
roslaunch junny_control junny_control.launch
```
steer the robot
```
rosrun turtlebot3_teleop turtlebot3_teleop_key
```

```
->              q     w     e
                a     s     d
                      x
```
```
w: linear velocity increase
a: angular velocity increase to clockwise
s: stop
d: angular velocity increase to counter-clockwise
x: linear velocity decrease
```
detect and publish ball position from camera image
```
rosrun ball_detection ball_detect_node
```
draw the lidar data and ball position
```
rosrun data_integrate data_show_node
```

# Change object detection test image

- In terminal
'''
roscd map_generate or move to src/map_generate directory
cd worlds
gedit map_final_ball.world
'''

- In map_final_ball.world

change line124
<name>test1</name> 
to
<name>test3</name>

10 test image is provided. You can change test1 to test10.

Image source:
T.-Y. Lin, M. Maire, S. Belongie, J. Hays, P. Perona, D. Ra-manan, P. Doll ́ar, and C. L. Zitnick. Microsoft COCO: Com-mon objects in context. InECCV, 2014.




