<p align="center">
  <img src="https://assets.skyfilabs.com/images/blog/tips-to-increase-the-chances-of-winning-wro.webp" width="700" alt="World Robot Olympiad logo">
</p>

<h1 align="center">WRO Future Engineers Documentation</h1>

<p align="center">
  <b>The Good Boys</b> | Autonomous Self-Driving Robot | Matrix Mini R4 + Arduino C++
</p>

<p align="center">
  <img src="https://img.shields.io/badge/WRO-Future%20Engineers-blue" alt="WRO Future Engineers">
  <img src="https://img.shields.io/badge/Team-The%20Good%20Boys-red" alt="Team The Good Boys">
  <img src="https://img.shields.io/badge/Controller-Matrix%20Mini%20R4-green" alt="Matrix Mini R4">
  <img src="https://img.shields.io/badge/Code-Arduino%20C++-orange" alt="Arduino C++">
  <img src="https://img.shields.io/badge/Robot-Autonomous%20Vehicle-purple" alt="Autonomous Vehicle">
</p>

---

<p align="center">
  Engineering documentation and source code for <b>The Good Boys</b> WRO Future Engineers self-driving robot using Matrix Mini R4, Arduino C++, servo steering, rear-wheel drive, laser sensing, AI camera recognition, and color line detection.
</p>

---

## Table of Contents

- [Team Information](#team-information)
- [Robot Overview](#robot-overview)
- [Mechanical Design](#mechanical-design)
  - [Rear-Wheel Drive System](#rear-wheel-drive-system)
  - [Front Steering System](#front-steering-system)
  - [Chassis and Structure](#chassis-and-structure)
- [Electrical System](#electrical-system)
- [Sensor System](#sensor-system)
  - [Color Sensor](#color-sensor)
  - [Laser Distance Sensor](#laser-distance-sensor)
  - [AI Camera](#ai-camera)
- [Software Overview](#software-overview)
- [Code Files](#code-files)
- [Open Challenge Strategy](#open-challenge-strategy)
- [Obstacle Challenge Strategy](#obstacle-challenge-strategy)
- [Robot Gallery](#robot-gallery)

---

## Team Information

| Item | Details |
|---|---|
| Team Name | The Good Boys |
| Competition Category | WRO Future Engineers |
| Robot Type | Autonomous self-driving vehicle |
| Controller | Matrix Mini R4 |
| Programming Language | Arduino C++ |

<p align="center">
  <img width="700" alt="Team image" src="https://github.com/user-attachments/assets/daa82aaf-4b5f-44bb-97ae-74dda7e2682d">
</p>

<p align="center">
  <i>The Good Boys team documentation for the WRO Future Engineers challenge.</i>
</p>

---

## Robot Overview

Our robot uses a rear-wheel drive system and a front steering system. The rear axle is powered by one motor, which drives the robot forward. The rear axle is supported with bearings to reduce friction and keep the wheels aligned while moving.

For steering, the robot uses a servo motor connected to a front axle. The front axle holds two wheels, and both wheels are attached with a single connector and axle. This allows the servo to rotate the steering axle smoothly and control the direction of the robot during autonomous movement.

The robot uses multiple sensors to understand the field:

- A color sensor placed at the bottom of the robot to detect colored lines on the field.
- A laser distance sensor to measure distance from objects or walls.
- An AI camera to help identify objects and assist with navigation during the obstacle challenge.

The robot is programmed using Arduino C++ through the Matrix Mini R4 system.

<p align="center">
  <img width="700" alt="Robot overview" src="https://github.com/user-attachments/assets/bbf78ad0-5eea-48f8-979c-6dfe739cef8e">
</p>

<p align="center">
  <i>Overall robot structure showing the main vehicle layout.</i>
</p>

---

## Mechanical Design

The mechanical design is based on a simple and stable four-wheel vehicle structure. The robot has two main movement systems:

- Rear-wheel drive system
- Front servo steering system

---

### Rear-Wheel Drive System

The robot uses one motor connected to the rear axle. The motor transfers motion to the rear axle, allowing the rear wheels to push the robot forward. This design was chosen because it keeps the driving system simple and direct.

The rear axle is supported with a single axle and one connector. The purpose of the connector is to reduce friction, improve smooth rotation, and keep the axle stable during movement.

<p align="center">
  <img width="700" alt="Rear wheel drive system" src="https://github.com/user-attachments/assets/546b2a87-f985-4b3c-9d84-46c32da37d73">
</p>

<p align="center">
  <i>Rear-wheel drive system powered by one motor connected to the rear axle.</i>
</p>

---

### Front Steering System

The steering system uses a servo motor connected to a front axle. The front axle holds two wheels. Each wheel is attached with its own bearing, which helps the wheels rotate smoothly while the servo changes the steering angle.

The servo motor controls the turning direction of the robot by rotating the front axle. This makes the steering more similar to a real car instead of using differential steering.

This design was chosen because the WRO Future Engineers challenge requires controlled movement around the track, and a servo-based steering system gives the robot more precise turning control.

<p align="center">
  <img width="700" alt="Front steering system" src="https://github.com/user-attachments/assets/a85ea278-1a16-4228-a25c-5eeb42d99e47">
</p>

<p align="center">
  <i>Servo-based front steering system for controlled turning.</i>
</p>

---

### Chassis and Structure

The robot is built using the Matrix kit structure. The chassis holds the controller, motor, servo, sensors, and wiring in fixed positions. The structure is designed to keep the robot stable while still allowing access to the main components for testing and repair.

<table>
  <tr>
    <td align="center">
      <img width="350" alt="Chassis view 1" src="https://github.com/user-attachments/assets/64adda7d-c5f5-48fe-b17e-8e7950c5d3d0"><br>
      <sub>Chassis structure view</sub>
    </td>
    <td align="center">
      <img width="350" alt="Chassis view 2" src="https://github.com/user-attachments/assets/b2b25e62-6910-4756-a674-4987ddfc27f3"><br>
      <sub>Component placement view</sub>
    </td>
  </tr>
</table>

---

## Electrical System

The robot uses the Matrix Mini R4 controller with Arduino C++ code. The controller receives input from the sensors and sends output commands to the motor and servo.

### Main Electrical Components

| Component | Function |
|---|---|
| Matrix Mini R4 Controller | Reads sensor values and controls outputs |
| Rear Drive Motor | Moves the robot forward |
| Servo Motor | Controls the steering direction |
| Bottom Color Sensor | Detects colored lines on the field |
| Laser Distance Sensor | Measures distance from objects or walls |
| AI Camera | Detects and recognizes obstacles |
| Battery / Power Source | Supplies power to the system |

The controller is responsible for reading sensor values, processing the robot’s position, deciding the next movement, and controlling the motor and servo.

<p align="center">
  <img width="600" alt="Electrical system" src="https://github.com/user-attachments/assets/d298f63c-c7eb-4c20-8f56-bc7d9d0c66f9">
</p>

<p align="center">
  <i>Electrical layout showing the controller and connected components.</i>
</p>

---

## Sensor System

The robot uses three main sensors: the color sensor, the laser sensor, and the AI camera.

---

### Color Sensor

The color sensor is placed on the bottom of the robot. Its main job is to detect colored lines on the field.

In the open challenge, the robot uses the color sensor to detect orange and blue lines. Every time the robot passes a line, the program updates a variable that counts the number of detected lines. This allows the robot to know how many sections of the track it has passed and when it should stop.

This is important because the robot cannot simply drive for a fixed amount of time. A timer would become inaccurate if the battery level changes, if the robot slips, or if the robot turns differently. Counting lines gives the robot a better way to track its progress around the field.

---

### Laser Distance Sensor

The laser distance sensor is used to measure distance from objects or walls. This helps the robot understand how close it is to obstacles or boundaries.

The sensor can be used to help the robot avoid collisions, correct its path, or decide when to turn.

---

### AI Camera

The AI camera is used for object recognition and obstacle detection. It helps the robot identify objects during the obstacle challenge and adjust its movement based on what it sees.

The AI camera adds another layer of sensing beyond simple line and distance detection. This is useful because the obstacle challenge requires the robot to react to objects in the field rather than only following a fixed route.

---

## Software Overview

The robot is programmed in Arduino C++ using the Matrix Mini R4 system.

The software controls:

- Motor movement
- Servo steering
- Line detection
- Line counting
- Distance sensing
- Camera-based obstacle detection
- Stopping logic
- Challenge-specific movement strategies

The program is divided into two main challenge modes:

| Challenge Mode | Purpose |
|---|---|
| Open Challenge Code | Drives around the field using line detection and line counting |
| Obstacle Challenge Code | Uses sensors and camera input to react to obstacles |

---

## Code Files

The robot code is organized by challenge type. Each section contains the Arduino C++ code used for that specific WRO Future Engineers challenge.

| Code Section | Purpose | Link |
|---|---|---|
| Open Challenge Code | Controls autonomous driving using line detection and line counting | [View Open Challenge Code](./Open%20Challenge%20Code) |
| Obstacle Challenge Code | Controls obstacle navigation using distance sensing and camera input | [View Obstacle Challenge Code](./Obstacle%20Challenge%20Code) |

---

## Open Challenge Strategy

In the open challenge, the robot must drive autonomously around the field without obstacles.

Our open challenge strategy is based on detecting the orange and blue lines on the field. The bottom color sensor reads the floor and checks when the robot passes over a colored line.

Each time the robot detects an orange or blue line, the code updates a variable. This variable stores how many lines the robot has passed. The robot uses this count to estimate its progress around the field and decide when it should stop.

### Open Challenge Logic

```text
1. Start the robot.
2. Drive forward using the rear motor.
3. Use the servo to steer and stay on the correct path.
4. Use the bottom color sensor to detect orange and blue lines.
5. Increase the line count whenever a valid line is detected.
6. Continue driving until the target number of lines is reached.
7. Stop the robot.
```

This method is stronger than only using time because line counting is based on the actual field position. If the robot moves slightly faster or slower, the line count still gives it a way to know where it is.

---

## Obstacle Challenge Strategy

In the obstacle challenge, the robot must drive autonomously while reacting to blocks and nearby walls. This challenge uses the same basic driving system as the open challenge, but it adds camera-based block detection and stronger distance sensing.

The robot uses the bottom color sensor to detect orange and blue lines, just like in the open challenge. These lines help the robot decide its driving direction and count its progress around the field.

The obstacle challenge also uses the AI camera to detect red and green blocks. When the camera detects a red block, the robot steers to the right. When the camera detects a green block, the robot steers to the left. This allows the robot to react to the obstacle color instead of following only a fixed route.

The front laser sensor is used to detect close objects or walls in front of the robot. If the robot gets too close to a wall while it is not tracking a block, it stops, reverses, and turns away. This helps prevent the robot from crashing into the field boundary.

The left laser sensor is used for soft wall stabilization. If the robot is too close to the left wall, it slightly steers right. If it is too far from the left wall, it slightly steers left. This helps the robot stay more stable while driving around the field.

### Obstacle Challenge Logic

```text
1. Start the robot.
2. Read the front laser sensor, left laser sensor, bottom color sensor, and AI camera.
3. Use the bottom color sensor to detect orange and blue lines.
4. Decide the driving direction based on the first valid colored line.
5. Count valid colored lines to track the robot’s progress.
6. Use the AI camera to detect red and green blocks.
7. If a red block is detected, steer right.
8. If a green block is detected, steer left.
9. If a front wall is detected and no block is being tracked, stop, reverse, and turn away.
10. Use the left laser sensor to make small steering corrections near the wall.
11. Continue driving until the target number of lines is reached.
12. Stop the robot after completing the required route.
```

This strategy is stronger than using only line detection because the robot can react to obstacles in real time. The camera allows the robot to respond to block color, while the laser sensors help it avoid walls and keep a stable path.

---

## Robot Gallery

<table>
  <tr>
    <td align="center">
      <img width="250" alt="Robot gallery 1" src="https://github.com/user-attachments/assets/bbf78ad0-5eea-48f8-979c-6dfe739cef8e"><br>
      <sub>Robot overview</sub>
    </td>
    <td align="center">
      <img width="250" alt="Robot gallery 2" src="https://github.com/user-attachments/assets/546b2a87-f985-4b3c-9d84-46c32da37d73"><br>
      <sub>Rear drive system</sub>
    </td>
    <td align="center">
      <img width="250" alt="Robot gallery 3" src="https://github.com/user-attachments/assets/a85ea278-1a16-4228-a25c-5eeb42d99e47"><br>
      <sub>Front steering system</sub>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img width="250" alt="Robot gallery 4" src="https://github.com/user-attachments/assets/64adda7d-c5f5-48fe-b17e-8e7950c5d3d0"><br>
      <sub>Chassis structure</sub>
    </td>
    <td align="center">
      <img width="250" alt="Robot gallery 5" src="https://github.com/user-attachments/assets/b2b25e62-6910-4756-a674-4987ddfc27f3"><br>
      <sub>Component placement</sub>
    </td>
    <td align="center">
      <img width="250" alt="Robot gallery 6" src="https://github.com/user-attachments/assets/d298f63c-c7eb-4c20-8f56-bc7d9d0c66f9"><br>
      <sub>Electrical system</sub>
    </td>
  </tr>
</table>

---

<p align="center">
  <b>End of Documentation</b>
</p>
