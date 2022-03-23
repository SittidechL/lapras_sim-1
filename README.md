# lapras_sim-1
```
terminal#1 **run gazebo**
mkdir nav2robot_ws && cd nav2robot_ws/
mkdir src && cd src/
git clone https://github.com/phuwanat-vg/lapras_sim.git
source /opt/ros/galactic/setup.bash
cd ..
colcon build
source install/local_setup.bash
export GAZEBO_MODEL_PATH=/usr/share/gazebo-11/models:${GAZEBO_MODEL_PATH}:~/nav2robot_ws/src/lapras_sim/lapras_sim
ros2 launch lapras_sim lapras_world.launch.py
```
```
terminal#2 **run ydlidar**
cd nav2robot_ws
source /opt/ros/galactic/setup.bash
ros2 topic list
colcon build
source install/local_setup.bash
ros2 launch lapras_sim ydlidar.launch.py
```
```
terminal#3 **lapras_module**
cd nav2robot_ws
source /opt/ros/galactic/setup.bash
colcon build
source install/local_setup.bash
ros2 run lapras_sim_support lapras_module 
```
```
terminal#4 **rviz2**
cd nav2robot_ws
source /opt/ros/galactic/setup.bash
source install/local_setup.bash
rviz2
```
```
new terminal **run cartographer**
cd navrobot_ws
source /opt/ros/galactic/setup.bash
colcon build
source install/local_setup.bash
ros2 launch navrobot cartographer.launch.py
```
```
new terminal **Key board**
cd nav2robot_ws
source /opt/ros/galactic/setup.bash
source install/local_setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```
```
terminal#5 **map_server**
cd nav2robot_ws
source /opt/ros/galactic/setup.bash
sudo apt install ros-galactic-nav2-map-server
ros2 run nav2_map_server map_saver_cli -f gazebo_map
```

# run robot actual to scan at 33:20
```
terminal#1
cd navrobot_ws
source /opt/ros/galactic/setup.bash
colcon build
source install/local_setup.bash
ros2 launch navrobot robot_bringup.launch.py
rviz2

terminal#2
source /opt/ros/galactic/setup.bash
ros2 launch navrobot cartographer.launch.py

terminal#3 for scan map
source /opt/ros/galactic/setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard

terminal#4 save map
source /opt/ros/galactic/setup.bash
ros2 run nav2_map_server map_saver_cli -f gazebo_map
```
## run map
```
navrobot_ws/
map --> insert file .pgm/.yaml
setup.py --> write add .pgm/.yaml

open terminal
source /opt/ros/galactic/setup.bash
colcon build --packages-select navrobot


```









