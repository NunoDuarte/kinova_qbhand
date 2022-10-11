# kinova_qbhand

![kinova_qbhand] TODO - add image

- **kinova_qbhand_description** : a URDF for a Kinova gen3 robot with a qbhand attached and a rigid base.
- **kinova_qbhand_moveit** : a MoveIt! package to work with the robot description just defined.
- **kinova_qbhand_bringup**: a package to bringup LBR iiwa and qbhand.

## Dependencies

- [ros_kortex](https://github.com/Kinovarobotics/ros_kortex.git): ROS integration for the Kinova gen3 (6/7 dof).
- [qbhand-ros](https://bitbucket.org/qbrobotics/qbhand-ros):  A package contains the ROS nodes aimed to visualize and control the qbrobotics® qbhand device.

## Supported ROS Distribution

ROS Melodic and Noetic 
roslaunch is different and in Ubuntu 20.04 is much trickier to install than in Ubuntu 18.04

## Test qbhand
run qbhand-ros launch file
```
roslaunch qb_hand_control control_qbhand.launch standalone:=true activate_on_initialization:=true device_id:=1
```
to close and open manually
```
rostopic pub /qbhand1/control/qbhand1_synergy_trajectory_controller/command trajectory_msgs/JointTrajectory "header:
  seq: 0
  stamp:
    secs: 0
    nsecs: 0
  frame_id: ''
joint_names:
- 'qbhand1_synergy_joint'
points:
- positions: [1]
  velocities: [0]
  accelerations: [0]
  effort: [0]
  time_from_start: {secs: 2, nsecs: 0}"
```
set position 1 to close completly and position 0 to open fully. Don't forget to add time in secs.

## Usage

After installing all the dependencies, you can:

- Visualize in RVIZ:

```xml
roslaunch kinova_qbhand_moveit demo.launch
```

- Real robot control:

TODO

