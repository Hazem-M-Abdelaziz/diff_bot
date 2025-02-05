# 🚗 Differential-Drive Robot with ROS2 Foxy, Gazebo, and RViz

This repository contains a **ROS2 Foxy** package for simulating and visualizing a differential-drive mobile robot in **Gazebo** and **RViz**. The robot's configuration and design are defined using **URDF (Unified Robot Description Format)**.


## 📂 Repository Structure

- **`config/`**  
  Contains configuration file to add adjust visulaization in rviz2:  
  - **`view_bot.rviz`**

- **`description/`**  
  Contains the URDF files used to describe the robot:
  - **`camera.xacro`**: Represents the camera link, joint, and plugin.
  - **`gazebo_control.xacro`**: Represents the differential drive plugin.
  - **`inertial_macros.xacro`**: Specify some standard inertial calculations as macros.
  - **`inertial_macros.xacro`**: Specify some standard inertial calculations as macros.
  - **`robot.urdf.xacro`**: Acts as linker to the rest of xacro files.
  - **`robot_core.xacro`**: Has all differential robots links and joints (the definition of the robot).

- **`launch/`**  
  Includes launch files:
  - **`display.launch.py`**: Launchs file used in the early stages of design period to visualize robot and use robot_state_publisher.  
  - **`sim.launch.py`**: Launchs the robot in a gazebo world by using spawn entity from gazebo_ros package.

- **`worlds/`**  
  Contains the world file:
  - **`custom_world.world`**: Defines a custom environment where a robot should spawns in.

- **`CMakeLists.txt`** & **`package.xml`**  
  Standard files for defining the ROS2 package dependencies and build process. 🛠️

## ✨ Features

1. **🌌 Simulation in Gazebo**:  
   The robot is spawned in a custom world and can interact with the simulation environment.
   
2. **🔍 Visualization in RViz**:  
   Displays the robot model and sensor data for debugging and monitoring.

3. **🛠️ URDF Robot Model**:  
   A detailed URDF representation of a differential-drive mobile robot with camera sensor.

## 📋 Prerequisites

- **ROS2 Foxy** installed on your system.  
- **Gazebo** is required for simulation.  
