# VAUV-simulator
This simulator is based on hte Plankton and used to test Vortex Robotics' AUV

## Install Dependinces
```
git clone https://github.com/VorteX-co/VAUV-simulator.git
cd VAUV-simulator
git clone -b dashing-devel https://github.com/ros/xacro.git
git clone -b eloquent https://github.com/ros2/launch.git
sudo apt install ros-dashing-launch*
sudo apt install ros-eloquent-launch-xml    
sudo apt install ros-eloquent-launch-yaml
```

## Sourceing
```
source /opt/ros/eloquent/setup.bash
source install/setup.bash
```
Add  " source /usr/share/gazebo/setup.sh" to your .bashrc file.
```
gedit ~/.bashrc
```


## Build Simulator
```
colcon build --packages-up-to plankton
```

## How to Run
Run each one in seperate terminals.
```
ros2 launch uuv_gazebo_worlds ocean_waves.launch
ros2 launch ptions uplv>LAUNCh mode;y;=0 z;=0 namespace;=rexrov
ros2 launch uuv_control_cascaded_pid joy_velocity.launch uuv_name:=rexrov model_name:=rexrov joy_id:=0
ros2 launch uuv_trajectory_control  rov_pid_controller.launch uuv_name:=rexrov
ros2 launch uuv_control_utils send_waypoints_file.launch uuv_name:=rexrov
```

