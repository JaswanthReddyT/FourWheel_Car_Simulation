# 🚗FourWheel_Car_Simulation
![Project Type](https://img.shields.io/badge/Type-Simulation%20Project-critical?logo=arduino&logoColor=white)
![Drone Type](https://img.shields.io/badge/chassis-FourWheel-success?logo=rocket&logoColor=white)
![Linux](https://img.shields.io/badge/OS-Ubuntu%2022.04-green)
![Framework: ROS2](https://img.shields.io/badge/Framework-ROS2-0A66C2?logo=ros&logoColor=white)
![Gazebo Classic](https://img.shields.io/badge/Simulator-Gazebo--Classic-yellow?logo=opengl&logoColor=white)
![Navigation: Waypoints](https://img.shields.io/badge/Controller-Teleop-blueviolet?logo=map&logoColor=white)
[![License: BSD 3-Clause](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

---
## 🧑‍💻 Author
***T.Jaswanth Reddy***   
  <a href="https://www.linkedin.com/in/thugu-jaswanth-reddy-12a72828b/" target="_blank">
    <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn" width="20" height="20" style="margin-left: 20px;">
  </a>
[LinkedIn](https://www.linkedin.com/in/thugu-jaswanth-reddy-12a72828b/) 
  <a href="https://github.com/JaswanthReddyT" target="_blank">
    <img src="https://cdn-icons-png.flaticon.com/512/25/25231.png" alt="GitHub" width="20" height="20">
  </a>
[GitHub](https://github.com/JaswanthReddyT)

---
## 🛰️ Overview
A complete simulation of a **four-wheel robot** built using **URDF/Xacro**, **ros2_control**, and **Gazebo Classic**, controlled using **keyboard teleoperation**.

---
## 🧠 Project Objective
- A custom **4-wheel robot model** (URDF/Xacro)
- Integration with **gazebo_ros2_control**
- A working **diff_drive_controller**
- **Keyboard teleoperation** using `teleop_twist_keyboard`
- A fully automated **launch file** to spawn the robot in Gazebo

---

## 🔧 Requirements

Tested on:
- **Ubuntu 22.04**
- **ROS 2 Humble**
- **Gazebo Classic**
- `ros2_control`, `ros2_controllers`, `gazebo_ros2_control`
- `teleop_twist_keyboard`

Install required packages:

```bash
sudo apt update
sudo apt install -y ros-humble-gazebo-ros-pkgs \
                    ros-humble-ros2-control ros-humble-ros2-controllers \
                    ros-humble-gazebo-ros2-control \
                    ros-humble-teleop-twist-keyboard
```

---
## 📁 Project Structure

```arduino
four_wheel_sim/
├── config/
│   └── diff_controllers.yaml
├── launch/
│   └── spawn_launch.py
├── urdf/
│   └── four_wheel_car.xacro
├── package.xml
├── setup.py
└── README.md
```

---
## 🛠️ Build Instructions
Create a workspace and build:

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
git clone <your-repo-url>
cd ..
colcon build
source install/setup.bash
```

---
## ▶️ Run the Simulation
Launch Gazebo and spawn the robot:

```bash
ros2 launch four_wheel_sim spawn_launch.py
```
This launch file:
  - Starts Gazebo Classic
  
  - Spawns the four-wheel robot
  
  - Loads diff_drive_controller

---
## 🎮 Keyboard Teleoperation
Open a new terminal and run:

```bash
source ~/ros2_ws/install/setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```
Controls:

```ini
w = move forward
s = move backward
a = turn left
d = turn right
```

---
## 🧠 How It Works
### 🔹 Robot Model (URDF/Xacro)
Includes:

  - Base link
  
  - 4 wheels with continuous joints
  
  - Transmissions for ros2_control
  
  - Gazebo plugin: `libgazebo_ros2_control.so`

### 🔹 Differential Drive Controller
`diff_drive_controller` controls left and right wheel groups:

 - Left wheels:
    `front_left_wheel_joint`, `rear_left_wheel_joint`

 - Right wheels:
   `front_right_wheel_joint`, `rear_right_wheel_joint`

It converts `/cmd_vel` → wheel velocities.

### 🔹 Gazebo Integration
- `spawn_entity.py` places robot into simulation

- `controller_manager` loads the controller automatically

---
## 📝 Features
- Custom URDF/Xacro-based robot

- ros2_control + Gazebo integration

- Differential-drive motion

- Keyboard control out of the box

- Clean and reusable package

- Perfect for beginners and simulation demos

---
## 🧩 Future Improvements
  - Add LIDAR, camera, and IMU sensors
  
  - Add Ackermann steering
  
  - Implement autonomous navigation (Nav2)
  
  - Add SLAM or mapping

---
## 📸 Screenshots


```scss
![Robot in Gazebo](images/sim1.png)
![Keyboard Teleop](images/teleop.png)
```

---
## 📜 License

This project and its related documentation are distributed under the **BSD 3-Clause License**.    
You are free to use, modify, and distribute this software, provided that proper credit is given to the original author and
the copyright notice is retained in all copies or substantial portions of the software.


---
