# kinova_qbhand

- Needs to be included the rgb-d camera

![kinova_qbhand] TODO - add image

- **kinova_qbhand_description** : a URDF for a Kinova gen3 robot with a qbhand attached and a rigid base.
- **kinova_qbhand_moveit** : a MoveIt! package to work with the robot description just defined.
- **kinova_qbhand_bringup**: a package to bringup LBR iiwa and qbhand.

## Dependencies

- [ros_kortex](https://github.com/Kinovarobotics/ros_kortex.git): ROS integration for the Kinova gen3 (6/7 dof).
- [qbhand-ros](https://bitbucket.org/qbrobotics/qbhand-ros):  A package contains the ROS nodes aimed to visualize and control the qbrobotics® qbhand device.

## Supported ROS Distribution

ROS Melodic (Ubuntu 18.04) and Noetic (Ubuntu 20.04). Note that in Ubuntu 20.04 it is harder to install qbhand-ros. 

## Test qbhand
run qbhand-ros launch file
```
roslaunch qb_hand_control control_qbhand.launch standalone:=true activate_on_initialization:=true device_id:=1
```
to close and open manually open new terminal
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

## Configuration
Inside **kinova_qbhand_moveit** the file sensor_3d.yaml has parameters on the point cloud data to set before any experiment:
- point_cloud_topic: change to the correct depth topic
- max_range: points further than this will not be used. 
- padding_offset: points closer than this will not be used. 

padding_offset is important to change to prevent moveit to detect the qbhand has an obstacle. 

## Usage

After installing all the dependencies, you can:

- Visualize in RVIZ:

```xml
roslaunch kinova_qbhand_moveit demo.launch
```

- Real robot control:

Working - needs documentation

