<h1 align="center">🤖🎨Autonomous Line-Painting Robot🎨🤖</h1>

Currently, in the subject Integrated Projects 2 at my university, my team is designing and developing from scratch an autonomous robot capable of painting lines on sports fields. <a href="https://github.com/Integrated-Project-2-2026-UVic-UCC/Line-Painting-Robot-T3/tree/main" target="_blank">Repository project link</a>

Although the main idea was to design it for outdoor grass fields, due to budget limitations, a scaled-down version for indoors has been made, ensuring the feasibility of the prototype. This change allows us to efficiently validate all the control, navigation, and painting system logic.

As the software leader of my group, I am responsible for programming both the robot's software and firmware. 

## 🚀System Architecture
The robot uses a dual processing architecture to separate real-time tasks from high-level tasks:

### 1. Control (Firmware - ESP32)
The ESP32 manages the critical hardware that requires low latency:
- DC Motors with Encoders: Speed and Position Control.
- IMU (Inertial Measurement Unit): Obtaining the orientation of the robot.
- Local Odometry: By processing the encoders and the IMU directly on the microcontroller, we obtain the relative position instantly, allowing much faster deviation corrections.

### 2. Navegation (Software - Raspberry Pi)
The Raspberry Pi acts as the central brain, taking care of:
- Lidar & Triangulation: Through the use of three beacons, the Lidar performs triangulation calculations to correct the cumulative drift of the odometry sensors.
- Obstacle Detection: Active safety during navigation.
- Scalability: In the original outdoor version, this localization system would be replaced by a high-precision sensor such as RTK GPS.

## 🎨Painting System
Currently in the design phase.
