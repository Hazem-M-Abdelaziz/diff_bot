# 🚗 Differential-Drive Robot with ROS2 Foxy, Gazebo, and RViz 🚗

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
<img src="https://github.com/user-attachments/assets/9b831404-0650-4ba3-88fb-475ef95437e7">

  - **`empty_world.world`**: In case you need to test your robot in an empty world. 

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

## 🚀 How to Use

1. Clone the repository inside <ROS2_WS/SRC>:  
   ```bash
   git clone https://github.com/Hazem-M-Abdelaziz/diff_bot.git
   cd <ROS2_WS>
2. Build the package:
   ```bash
    colcon build --symlink-install
    source install/setup.bash
3. Launch the simulation and visualization:
   ```bash
    ros2 launch diff_bot sim.launch.py world:=./<pathFromCurrentToCustomWorldFileWithExtension>

This will:
- 📜 Load the robot model into the parameter server.
- 🌍 Start Gazebo with the specified world.
- 🤖 Spawn the robot in the simulation environment.
- 📷 Publish camera sensor snaps into /camera topics.

## ⌨️ Moving using teleop node
- for this, you'll need to install teleop_twist_keyboard package to use teleop_twist_keyboard node as follows:
   ```bash
    ros2 run teleop_twist_keyboard teleop_twist_keyboard

## ⌨️ Visualizing in RViz2
- For sensory data and tf visualization:
   ```bash
    rviz2 -d ros2_ws/src/diff_bot/config/view_bot.rviz 

<img src="https://github.com/user-attachments/assets/8231d88a-77ee-46bb-91a2-a138e525bc33">


## Credits 🙌
Special thanks to [Articulated Robotics Youtube channel](https://www.youtube.com/@ArticulatedRobotics) for their valuable published tutorials.
