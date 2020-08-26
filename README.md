# ERA Path Planning

## Setup

Create a catkin workspace.

```bash
git clone [this repository] catkin_ws
```

Install requirements
* ros-kinetic-desktop-full
* ros-kinetic-gazebo-ros-control
* ros-kinetic-navigation
* ros-kinetic-gmapping
* ros-kinetic-robotnik-msgs
* ros-kinetic-robotnik-sensors
* ros-kinetic-teleop-twist-keyboard
* ros-kinetic-mavros
* ros-kinetic-twist-mux
* ros-kinetic-ros-controllers
* ros-kinetic-ros-localization
* ros-kinetic-teb-local-planner
* ros-kinetic-effort-controllers

```
sudo apt-get install ros-kinetic-desktop-full \
ros-kinetic-gazebo-ros-control \
ros-kinetic-navigation \
ros-kinetic-gmapping \
ros-kinetic-robotnik-msgs \
ros-kinetic-robotnik-sensors \
ros-kinetic-teleop-twist-keyboard \
ros-kinetic-mavros \
ros-kinetic-twist-mux \
ros-kinetic-ros-controllers \
ros-kinetic-ros-localization \
ros-kinetic-teb-local-planner \
ros-kinetic-effort-controllers \
python-rosdep python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential \
```

Rosdep initialize
```
sudo rosdep init
rosdep update
```

Build the catkin_workspace
```
cd catkin_ws
catkin_make
```

Source built packages
```
source devel/setup.bash
```

Launch Gazebo and RViz environments for localization
```
roslaunch roborts_sim_bringup roborts_complete.launch
```
