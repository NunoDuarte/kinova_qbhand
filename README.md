# kinova_qbhand

![kinova_qbhand] TODO - add image

- **kinova_qbhand_description** : a URDF for a Kinova gen3 robot with a qbhand attached and a rigid base.
- **kinova_qbhand_moveit** : a MoveIt! package to work with the robot description just defined.
- **kinova_qbhand_bringup**: a package to bringup LBR iiwa and qbhand.

## Dependencies

- [ros_kortex](https://github.com/Kinovarobotics/ros_kortex.git): ROS integration for the Kinova gen3 (6/7 dof).
- [qbhand](https://bitbucket.org/qbrobotics/qbhand-ros/src/production-melodic/):  A package contains the ROS nodes aimed to visualize and control the qbrobotics® qbhand device.

## Supported ROS Distribution

ROS Noetic

## Usage

After installing all the dependencies, you can:

- Visualize in RVIZ:

```xml
roslaunch kinova_qbhand_moveit demo.launch
```

- Real robot control:

TODO

