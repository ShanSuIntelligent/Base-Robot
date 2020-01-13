# Preliminaries
If you haven't already installed ROS on your PC, you need to add the ROS apt repository. This step is necessary for either binary or source install.

> sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
sudo apt-get update -qq

## Source install
For a source install, run the commands below:

## Create a catkin workspace
> mkdir -p ~/catkin_ws/src
> cd ~/catkin_ws/src/

## Clone base-robot into the catkin workspace
> git clone -b https://github.com/Sunspeed-Robotics/Base-Robot.git

## Build all packages in the catkin workspace
> source /opt/ros/kinetic/setup.bash
> catkin_init_workspace
> cd ~/catkin_ws
> catkin_make -DCMAKE_BUILD_TYPE=RelWithDebugInfo

You should add the following line to the end of your ~/.bashrc, and then close and reopen all terminals:

> source ~/catkin_ws/devel/setup.bash
