[**r2d2** (ros2dorna2)](https://github.com/pinorobotics/r2d2) - set of ROS2 packages which provide support for [Dorna2 robotic arm](https://dorna.ai/).

**r2d2_moveit_config** package contains MoveIt2 configuration files for Dorna2 robotic arm

NOTE: This is unofficial Dorna ROS2 package. For official Dorna software follow https://dorna.ai/

NOTE: This package can be used with [MoveItConfigsBuilder](https://github.com/moveit/moveit2/blob/main/moveit_configs_utils/moveit_configs_utils/moveit_configs_builder.py), as it satisfies MoveItConfigsBuilder package naming requirement "<PACKAGE_NAME>_moveit_config"

# Generating MoveIt configuration files

Run MoveIt Setup Assistant:
``` bash
ros2 launch moveit_setup_assistant setup_assistant.launch.py
```

- Before pressing "Generate" make sure to uncheck "initial_positions.yaml". MoveIt Setup Assistant uses default joint values from URDF, when it generatess this file, which results in all values to be equal "0". Since we want the robot to start from its home position (and not simply "0"), we set initial values manually inside "initial_positions.yaml" (which is Dorna2 "home" position).

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

Inside MotionPlanning panel, set "Goal state" to "valid random" and press "Plan". MoveIt should generate the trajectory.

# Documentation

- [r2d2](https://github.com/pinorobotics/r2d2)

# Contacts

aeon_flux <aeon_flux@eclipso.ch>
