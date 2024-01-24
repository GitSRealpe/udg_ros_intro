# UdG_ROS_intro

ROS package for the UdG robotics master students, that aims to cover the basics of URDF with examples for the following scenarios:
- Simple serial manipulator using URDF defined geometries.
- Serial manipulator with attached gripper defined by its own URDF and in a different ROS package [unal_gripper_pkg](https://github.com/GitSRealpe/unal_gripper).
- Dual arm robot URDF, robot manipulators that share a common base link.
- Multi robot definition, robots who are independent from each other between themselves, a "*swarm*" robot example like.

## Simple serial manipulator

Executed running the following in the linux terminal:
- <code>roslaunch udg_ros_intro tutobot_viz.launch</code>
<p float="left" align="middle">
  <img src="/media/tutobot.png" width="300" height="250"/>
  <img src="/media/tutobot_gripper.png" width="300" height="250"/> 
</p>

The following is the tf tree showing how the robot links are related.
<p align="middle">
    <img src="/media/frames.png" width="200"/>    
</p>

## Dual arm robot

This example showcases how a Xacro macro defined robot can be included seamlessly in a general URDF, allowing for example, a dual arm robot.
Executed running the following in the linux terminal:
- <code>roslaunch udg_ros_intro dual_tutobot_viz.launch</code>
<p float="left" align="middle">
  <img src="/media/dualbot.png" width="500"/>
</p>

Here, the tf tree shows how both manipulators have their own link chain, but share a common base_link.
<p align="middle">
    <img src="/media/frames_dual.png" width="300"/>    
</p>

## Multiple robots
In this case we load two `robot_descriptions` in the ROS parameter server, meaning that each robot is kinematically independent from the other.
This example showcases the use of the `namespace` and the `tf_prefix` variables in the launch file.

Executed running the following in the linux terminal:
- <code>roslaunch udg_ros_intro multi_tutobot_viz.launch</code>

<p float="left" align="middle">
  <img src="/media/multibot.png" width="400"/> 
</p>

Following is the tf tree, any robot in ROS should have a parent link from where it gets its position, here the common parent for the robots is the `world` frame, besides that, the robots are independent from each other.

<p align="middle">
    <img src="/media/frames_multi.png" width="400"/>    
</p>

