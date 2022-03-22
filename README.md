# lapras_sim-1
```
mkdir nav2robot_ws && cd nav2robot_ws/
mkdir src && cd src/
git clone https://github.com/phuwanat-vg/lapras_sim.git
source /opt/ros/galactic/setup.bash
cd ..
colcon build
source install/local_setup.bash
export GAZEBO_MODEL_PATH=/usr/share/gazebo-11/models:${GAZEBO_MODEL_PATH}:~/ros2robot_ws/src/lapras_sim/lapras_sim
ros2 launch lapras_sim lapras_world.launch.py
```

















```
mkdir nav2sim_ws && cd nav2sim_ws
git clone https://github.com/phuwanat-vg/lapras_sim.git
mkdir src
mv lapras_sim src/
colcon build
cd ..
source /opt/ros/galactic/setup.bash
cd nav2sim_ws
colcon build
source install/local_setup.bash
sudo apt install ros-galactic-gazebo-ros   # install "gazebo"
sudo apt install ros-galactic-gazebo-plungins   # E: Unable to locate package ros-galactic-gazebo-plungins
export GAZEBO_MODEL_PATH=/usr/share/gazebo-11/models:${GAZEBO_MODEL_PATH}:~/nav2sim_ws/src/lapras_sim
ros2 launch lapras_sim lapras_world.launch.py
 ```
