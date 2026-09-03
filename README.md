# 🤖 ALPINE Climbing Robot Documentation

This repository collects the documentation of **ALPINE (A cLimbing robot for oPerations In mouNtain Environments)**, a rope-supported climbing robot developed for inspection and maintenance on steep and irregular mountain surfaces.

The current experimental platform combines:
- two motorised winches for rope-supported motion;
- a pneumatic jumping leg;
- a six-EDF attitude-control subsystem for pitch and yaw regulation;
- onboard inertial sensing and embedded control;
- homing-relative rope sensing and body-pose reconstruction;
- high-level jump planning and coordinated real-robot execution.

The documentation is organised as an Obsidian vault, but the Markdown files can also be read directly on GitHub.

## Main documentation

Open [[🧠_Alpine_Documentation]] for the complete index.

### Current integrated platform

The 2026 experimental integration adds the control layer required to operate the physical prototype as a coordinated system. The main additions are documented in:

- [[EDF attitude-control system]]
- [[Body propulsion electronics]]
- [[Attitude_Control]]
- [[Winch_Homing_and_Position_Control]]
- [[Body_Pose_Reconstruction]]
- [[Jump_Execution_Pipeline]]
- [[Experimental validation]]

## Repository structure

- `Hardware (mechanical) part/` - mechanical design and subsystem calculations.
- `Hardware (electric) part/` - electrical architecture, power and electronics.
- `Software part/` - firmware, control architecture, planners and runtime flow.
- `Experimental_Results/` - real-robot validation and actuator characterisation.
- `Bill_Of_material/` - component lists.
- `0_Images/` - figures and documentation assets.
- `Thesis/` - thesis references and final-dissertation information.

> The current integrated platform was validated functionally on the indoor wall. Quantitative trajectory accuracy, direct rope-tension measurement, automatic touchdown detection and planner-driven consecutive physical jumps remain future work.
