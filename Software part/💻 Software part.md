This section documents the software used for planning, control, firmware and real-robot integration.

## Index

- [[Firmware]]
- [[Flow_of_program]]
- [[Attitude_Control]]
- [[Winch_Homing_and_Position_Control]]
- [[Body_Pose_Reconstruction]]
- [[Jump_Execution_Pipeline]]
- [[#Single jump trajectory]]
- [[#Multi jump trajectory optimizer]]
- [[🌐 Web_App_GUI]]
- [[#Cost map and point cloud handler]]

---

## Real-robot control layer

The current physical architecture separates fast local feedback from high-level coordination:

- body attitude loop: **100 Hz** on the ESP32-S3;
- rope-position control: **50 Hz**;
- winch encoder feedback: **200 Hz**;
- ESC PWM frame: **50 Hz**;
- jump sequencing and planner interface: high-level software.

The main rule is that **each actuator has one command owner at a time**. During a jump, the attitude controller remains active while the high-level sequence coordinates pneumatic actuation and the two winch force profiles.

See [[Flow_of_program]].

---

## Single Jump trajectory

- [[Single Jump]]
- [[Climb_robot2_Light]]

## Multi jump trajectory optimizer

- [[Multi Jump]]

## Mixed Distribution Cross Entropy Method

- [[Mixed Distribution Cross Entropy Method]]

## Cost map and point cloud handler

- [[💵Cost_map]]

## Web App

## ROS1/ROS2 Bridge
