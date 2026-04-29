# wro-future-engineers-the-good-boys
Engineering documentation and source code for The Good Boys WRO Future Engineers self-driving robot using Matrix Mini R4, Arduino C++, servo steering, rear-wheel drive, laser sensor, AI camera, and color line detection.
# WRO Future Engineers Documentation  
## Team: The Good Boys

This repository contains the engineering documentation and source code for **The Good Boys**, a team participating in the **WRO Future Engineers self-driving car challenge**.

Our vehicle is designed to complete both the open challenge and the obstacle challenge using a Matrix Mini R4 controller, Arduino C++ programming, rear-wheel drive, servo steering, line detection, distance sensing, and camera-based object recognition.

The goal of this repository is to document the full engineering process behind the robot, including the mechanical design, electrical system, sensor layout, software logic, testing process, and final challenge strategies.

---

# 1. Team Information

**Team Name:** The Good Boys  
**Competition Category:** WRO Future Engineers  
**Robot Type:** Autonomous self-driving vehicle  
**Controller:** Matrix Mini R4  
**Programming Language:** Arduino C++  

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/daa82aaf-4b5f-44bb-97ae-74dda7e2682d" />

---

# 2. Robot Overview

Our robot uses a rear-wheel drive system and a front steering system. The rear axle is powered by one motor, which drives the robot forward. The rear axle is supported with bearings to reduce friction and keep the wheels aligned while moving.

For steering, the robot uses a servo motor connected to a front axle. The front axle holds two wheels, and both wheels are attached with separate bearings. This allows the servo to rotate the steering axle smoothly and control the direction of the robot during autonomous movement.

The robot uses multiple sensors to understand the field:

- A color sensor placed at the bottom of the robot to detect colored lines on the field.
- A laser distance sensor to measure distance from objects or walls.
- An AI camera to help identify objects and assist with navigation during the obstacle challenge.

The robot is programmed using Arduino C++ through the Matrix Mini R4 system.

[ADD FULL ROBOT PHOTO HERE]

---

# 3. Mechanical Design

The mechanical design is based on a simple and stable four-wheel vehicle structure. The robot has two main movement systems:

## 3.1 Rear-Wheel Drive System

The robot uses one motor connected to the rear axle. The motor transfers motion to the rear axle, allowing the rear wheels to push the robot forward. This design was chosen because it keeps the driving system simple and direct.

The rear axle is supported with bearings. The purpose of the bearings is to reduce friction, improve smooth rotation, and keep the axle stable during movement.

[ADD PHOTO OF REAR AXLE AND MOTOR HERE]

## 3.2 Front Steering System

The steering system uses a servo motor connected to a front axle. The front axle holds two wheels. Each wheel is attached with its own bearing, which helps the wheels rotate smoothly while the servo changes the steering angle.

The servo motor controls the turning direction of the robot by rotating the front axle. This makes the steering more similar to a real car instead of using differential steering.

This design was chosen because the WRO Future Engineers challenge requires controlled movement around the track, and a servo-based steering system gives the robot more precise turning control.

[ADD PHOTO OF SERVO STEERING SYSTEM HERE]

## 3.3 Chassis and Structure

The robot is built using the Matrix kit structure. The chassis holds the controller, motor, servo, sensors, and wiring in fixed positions. The structure is designed to keep the robot stable while still allowing access to the main components for testing and repair.

[ADD TOP VIEW PHOTO OF ROBOT HERE]  
[ADD BOTTOM VIEW PHOTO OF ROBOT HERE]  
[ADD LEFT SIDE PHOTO HERE]  
[ADD RIGHT SIDE PHOTO HERE]  
[ADD FRONT PHOTO HERE]  
[ADD BACK PHOTO HERE]

---

# 4. Electrical System

The robot uses the Matrix Mini R4 controller with Arduino C++ code. The controller receives input from the sensors and sends output commands to the motor and servo.

The main electrical components are:

- Matrix Mini R4 controller
- Rear drive motor
- Servo motor for steering
- Bottom color sensor
- Laser distance sensor
- AI camera
- Battery or power source

The controller is responsible for reading sensor values, processing the robot’s position, deciding the next movement, and controlling the motor and servo.

[ADD WIRING PHOTO HERE]  
[ADD WIRING DIAGRAM HERE]

---

# 5. Sensor System

The robot uses three main sensors: the color sensor, the laser sensor, and the AI camera.

## 5.1 Color Sensor

The color sensor is placed on the bottom of the robot. Its main job is to detect colored lines on the field.

In the open challenge, the robot uses the color sensor to detect orange and blue lines. Every time the robot passes a line, the program updates a variable that counts the number of detected lines. This allows the robot to know how many sections of the track it has passed and when it should stop.

This is important because the robot cannot simply drive for a fixed amount of time. A timer would become inaccurate if the battery level changes, if the robot slips, or if the robot turns differently. Counting lines gives the robot a better way to track its progress around the field.

[ADD PHOTO OF BOTTOM COLOR SENSOR HERE]

## 5.2 Laser Distance Sensor

The laser distance sensor is used to measure distance from objects or walls. This helps the robot understand how close it is to obstacles or boundaries.

The sensor can be used to help the robot avoid collisions, correct its path, or decide when to turn.

[ADD PHOTO OF LASER SENSOR HERE]

## 5.3 AI Camera

The AI camera is used for object recognition and obstacle detection. It helps the robot identify objects during the obstacle challenge and adjust its movement based on what it sees.

The AI camera adds another layer of sensing beyond simple line and distance detection. This is useful because the obstacle challenge requires the robot to react to objects in the field rather than only following a fixed route.

[ADD PHOTO OF AI CAMERA HERE]

---

# 6. Software Overview

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

1. Open Challenge Code  
2. Obstacle Challenge Code  

[ADD SCREENSHOT OF CODE FILE STRUCTURE HERE]

---

# 7. Open Challenge Strategy

In the open challenge, the robot must drive autonomously around the field without obstacles.

Our open challenge strategy is based on detecting the orange and blue lines on the field. The bottom color sensor reads the floor and checks when the robot passes over a colored line.

Each time the robot detects an orange or blue line, the code updates a variable. This variable stores how many lines the robot has passed. The robot uses this count to estimate its progress around the field and decide when it should stop.

The basic open challenge logic is:

1. Start the robot.
2. Drive forward using the rear motor.
3. Use the servo to steer and stay on the correct path.
4. Use the bottom color sensor to detect orange and blue lines.
5. Increase the line count whenever a valid line is detected.
6. Continue driving until the target number of lines is reached.
7. Stop the robot.

This method is stronger than only using time because line counting is based on the actual field position. If the robot moves slightly faster or slower, the line count still gives it a way to know where it is.

[ADD OPEN CHALLENGE VIDEO LINK HERE]  
[ADD OPEN CHALLENGE CODE LINK HERE]

---

# 8. Obstacle Challenge Strategy

In the obstacle challenge, the robot must move around the field while reacting to obstacles.

The obstacle challenge uses the same basic driving system as the open challenge, but it also relies more on the laser distance sensor and AI camera.

The laser sensor helps the robot measure distance from objects or walls. The AI camera helps the robot identify obstacles and make decisions based on what appears in front of it.

The basic obstacle challenge logic is:

1. Start the robot.
2. Drive forward using the rear motor.
3. Use the servo motor to steer.
4. Use the color sensor to track colored lines when needed.
5. Use the laser sensor to detect nearby objects or walls.
6. Use the AI camera to identify obstacles.
7. Adjust steering and movement based on sensor readings.
8. Avoid obstacles and continue around the field.
9. Stop after completing the required task.

[ADD OBSTACLE CHALLENGE VIDEO LINK HERE]  
[ADD OBSTACLE CHALLENGE CODE LINK HERE]

---

