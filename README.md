# Base Robot
This repositry contains ROS package for base mobile robot it includes: 

`base_discreption` URDF configuration

`base_navigation` move_base launch and configuration files

`base_robot` 

`third_party_sensors`


# Preliminaries
If you haven't already installed ROS on your PC, you need to add the ROS apt repository. This step is necessary for either binary or source install.

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
sudo apt-get update -qq
```

### Source install

For a source install, run the commands below:

#### Create a catkin workspace
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src/
```
#### Clone base-robot into the catkin workspace
```
git clone -b https://github.com/Sunspeed-Robotics/Base-Robot.git
```
#### Build all packages in the catkin workspace
```
source /opt/ros/kinetic/setup.bash
catkin_init_workspace
cd ~/catkin_ws
catkin_make -DCMAKE_BUILD_TYPE=RelWithDebugInfo
```
You should add the following line to the end of your `~/.bashrc`, and then close and reopen all terminals:
```
source ~/catkin_ws/devel/setup.bash
```

![Screenshot from 2019-12-31 16-59-54|512x397](https://user-images.githubusercontent.com/36022350/72243048-cb41d300-3625-11ea-9b49-0f24d772e46d.png)

# ros2 control 
## Using ros1_bridge

In first shell you need to source ros1 
```
source /opt/ros/melodic/setup.bash
```

In second shell source ros2
```
source /opt/ros/dashing/setup.bash
```

Run ros1_bridge in third shell 
```
ros2 launch ros1_bridge dynamic_bridge
```
![Screenshot from 2019-12-31 16-55-gfd30](https://user-images.githubusercontent.com/36022350/72399948-a151f300-3782-11ea-8585-d5a8409b623e.png)

Run state_publisher.py
```
ros2 launch ir100_discreption ir100_state_publish.py
```

![Screenshot from 2019-12-31 16-58-401](https://user-images.githubusercontent.com/36022350/72243210-4905de80-3626-11ea-8a12-524b862c6b86.png)


