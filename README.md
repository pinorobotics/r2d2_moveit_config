**r2d2** (ros2dorna2) - set of ROS2 packages which provide support for [Dorna2 robotic arm](https://dorna.ai/).

**r2d2_moveit_config** package contains MoveIt2 configuration files for Dorna2 robotic arm

NOTE: This is unofficial Dorna ROS2 package. For official Dorna software follow https://dorna.ai/

To use this package with MoveItConfigsBuilder its name should be in form "<PACKAGE_NAME>_moveit_config"

# Generating MoveIt configuration files

Run MoveIt Setup Assistant:
``` bash
ros2 launch moveit_setup_assistant setup_assistant.launch.py
```

Build:
```
cd <ROS WORKSPACE>
colcon build
source install/setup.zsh
```

Test generated files:
```
ros2 launch r2d2_moveit_config demo.launch.py
```

Set "Goal state" to "valid random" and press "Plan". MoveIt should generate the trajectory.

# Contacts

aeon_flux <aeon_flux@eclipso.ch>
