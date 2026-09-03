~={red}**Welcome to the Climb Robot / ALPINE Robot Project Documentation**=~

This documentation covers the development of the ALPINE climbing robot from concept and simulation to the current integrated physical prototype.

The repository includes:
- electrical components and power architecture;
- mechanical components and subsystem design;
- physics-based calculations and actuator selection;
- single- and multi-jump planning;
- embedded firmware and real-robot control;
- six-EDF pitch/yaw attitude regulation;
- winch homing and rope-position control;
- body-pose reconstruction and telemetry;
- pneumatic actuation;
- experimental validation on the physical platform.

for readme: [[README]]

---

## Schema of all structure

The legacy workspace schema is stored in:
![[Climb_robot/schema.canvas]]

Communication and software-flow material is also available in:
![[Alpine_workflow.excalidraw]]

For the current physical control architecture see [[Flow_of_program]] and [[Jump_Execution_Pipeline]].

---

## 🗃️ Index

- [[🧾 State of art climb robot]]
- [[🧾 Introduction climb robot]]
- [[🤝 Team of the Climbing Robot]]
- [[🧾 BOM climbing robots]]
- [[2026 attitude-control additions]]

### [[⚙️ Hardware (mechanical) part]]

- [[🧮 Old_calculations]]
- [[📊 Winch_calculations]]
- [[📊 Piston_calculations]]
- [[📊 Stabilizers calculations]]
- [[EDF attitude-control system]]

### [[💡 Hardware (electric) part]]

- [[Body propulsion electronics]]

### [[💻 Software part]]

- [[Firmware]]
- [[Flow_of_program]]
- [[Attitude_Control]]
- [[Winch_Homing_and_Position_Control]]
- [[Body_Pose_Reconstruction]]
- [[Jump_Execution_Pipeline]]
- [[Single Jump]]
- [[Multi Jump]]
- [[🌐 Web_App_GUI]]
- [[💵Cost_map]]

### 🧪 Experimental validation

- [[Experimental validation]]
- [[EDF and attitude tests]]
- [[Pneumatic actuator tests]]
- [[Winch and odometry tests]]
- [[Integrated jump test]]

### 📝 Thesis

- Mechatronics Design of the Alpine Climbing Robot — Luca Hardonk, 2025.
- Multi-jump Trajectory Optimizer and Software Design of the Alpine Climbing Robot — 2026.
- **Orientation Control and Experimental Integration of the ALPINE Climbing Robot — Andrea Dalla Villa, 2026.**
- See [[Thesis - Andrea Dalla Villa 2026]].

### Notes

- [[🧾 Climb Robot general theory]]

---

## 🔗 Link to schema and collaboration GIT

- Git collaboration: [click here](https://github.com/MalaHard-RoboTech)
- ALPINE GitHub organisation: [alpine-robot](https://github.com/alpine-robot)

---

### 📊 Matlab Results

>[!Note] **NOTE:** legacy Matlab simulation results are available in the following resources:

- [Matlab_Scripts](https://github.com/MalaHard-RoboTech/Matlab_Scirpts)
- [Matlab_result](Misure_Matlab.xlsx)

---

## 🔗 Useful links and software

- ODrive:
  - [ODrive](https://odriverobotics.com/)
  - [ODrive GUI](https://gui.odriverobotics.com/)
  - [Torque-speed simulation](https://www.desmos.com/calculator/1bw85mchnu)
- Tutorials:
  - [Motor driver](https://www.youtube.com/watch?v=9UxTPxgvOAA)
  - [Git submodule](https://youtu.be/wTGIDDg0tK8?si=bb5k6O9tb5w0m2Zo)
- Software and environments:
  - [ROS 1](https://docs.ros.org/)
  - [ROS 2](https://docs.ros.org/en/jazzy/index.html)
  - [MATLAB](https://it.mathworks.com/)
  - [Fusion 360](https://www.autodesk.com/it/products/fusion-360/overview)

---

## 🧾 Useful Git commands after cloning

```bash
git config --global user.name "name"
git config --global user.email "name.surname@gmail.com"

ssh-keygen
cat ~/.ssh/id_rsa.pub

eval "$(ssh-agent -s)"
ssh -T git@github.com
```
