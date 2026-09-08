🔥 Firefighter Robot
Technical Project Documentation
	
Team	Robo-X Team
Program	EAII Summer Camp
Year	2026
Team Size	11 members
Project Type	Educational Robotics
Controller	Arduino Uno
📖 Table of Contents
1. Project Overview
2. Objectives
3. System Architecture
4. Hardware
5. Software
6. Development Stages
7. Final System
8. Testing
9. Challenges
10. Team & Contributions
11. Skills Developed
12. Limitations
13. Future Improvements
14. Resources
15. License
16. Conclusion
1. Project Overview

The Firefighter Robot is a multi-stage robotic system developed by the Robo-X Team during EAII Summer Camp 2026.

The project was designed to demonstrate how robotics can be used to detect and respond to a simulated fire.

The robot combines:

🚗 Mobile movement
🔥 Flame detection
💨 Smoke detection
🧭 Obstacle detection
💧 Water-based extinguishing
🤖 Autonomous control

Rather than developing the complete robot at once, we built it through five progressive stages.

Stage 1
Basic Movement
      ↓
Stage 2
Fire Detection
      ↓
Stage 3
Fire Extinguishing
      ↓
Stage 4
Smoke Detection
      ↓
Stage 5
Autonomous Navigation


This approach allowed us to build, test, debug, and improve each subsystem before moving to the next stage.

2. Objectives

The project had several main objectives:

Build a functional four-wheel robotic platform.
Control DC motors using an Arduino.
Detect a simulated flame.
Determine the approximate direction of the flame.
Navigate toward the detected fire.
Detect smoke/gas using an MQ-2 sensor.
Detect obstacles using an ultrasonic sensor.
Activate a water pump to extinguish the simulated fire.
Integrate multiple sensors and actuators.
Gain practical experience in robotics and engineering.
Develop teamwork and problem-solving skills.
3. System Architecture

The Arduino Uno acts as the central controller.

It receives input from the sensors, processes the information using programmed logic, and controls the robot's motors and extinguishing system.

                         ┌──────────────────┐
                         │    ARDUINO UNO   │
                         │  Main Controller │
                         └────────┬─────────┘
                                  │
            ┌─────────────────────┼─────────────────────┐
            │                     │                     │
            ▼                     ▼                     ▼
     ┌─────────────┐       ┌─────────────┐       ┌─────────────┐
     │    Flame    │       │    MQ-2     │       │   HC-SR04   │
     │   Sensors   │       │    Smoke    │       │  Ultrasonic │
     └─────────────┘       └─────────────┘       └─────────────┘
            │                     │                     │
            └─────────────────────┼─────────────────────┘
                                  │
                                  ▼
                         ┌──────────────────┐
                         │   CONTROL LOGIC  │
                         └────────┬─────────┘
                                  │
                    ┌─────────────┴─────────────┐
                    │                           │
                    ▼                           ▼
             ┌─────────────┐             ┌─────────────┐
             │     L298N   │             │ Extinguishing│
             │ Motor Driver│             │    System    │
             └──────┬──────┘             └──────┬──────┘
                    │                           │
                    ▼                           ▼
               4 DC Motors                 Pump + Servo

4. Hardware
4.1 Component Overview
Component	Purpose
Arduino Uno	Main controller
L298N	Motor control
4 × DC Motors	Robot movement
Flame Sensors	Fire detection
MQ-2 Sensor	Smoke/gas detection
HC-SR04	Obstacle detection
Servo Motor	Extinguishing mechanism positioning
Water Pump	Moves water to the nozzle
Water Tank	Stores water
LED	Status indication
Battery	Power source
Breadboard	Circuit connections
Jumper Wires	Electrical connections
4.2 Arduino Uno

The Arduino Uno is responsible for coordinating the robot.

Its main tasks include:

Reading sensor values
Processing sensor information
Controlling motor movement
Controlling the servo
Activating the water pump
Executing the programmed control logic
4.3 L298N Motor Driver

The L298N provides the connection between the Arduino and the DC motors.

It allows the robot to control the direction and movement of the motors.

The Arduino provides the control signals while the motor driver handles the motor control.

4.4 Flame Sensors

Flame sensors are used to detect a simulated fire.

Multiple sensors allow the robot to compare readings from different directions and determine where the flame is located.

4.5 MQ-2 Smoke Sensor

The MQ-2 sensor was introduced during Stage 4.

It provides smoke/gas detection and gives the robot additional environmental information.

4.6 HC-SR04 Ultrasonic Sensor

The HC-SR04 is used for obstacle detection.

It measures the distance between the robot and nearby objects, allowing the robot to react when an obstacle is detected.

4.7 Water Extinguishing System

The extinguishing system consists of:

Water tank
Water pump
Servo motor
Tubing
Nozzle

The pump moves water from the tank through the tubing while the servo controls the position of the mechanism.

5. Software

The robot was programmed using Arduino/C++.

The software was developed progressively, with a separate program for each stage.

code/
├── stage1.ino
├── stage2.ino
├── stage3.ino
├── stage4.ino
└── stage5.ino


Each file represents a milestone in the robot's development.

6. Development Stages
🟢 Stage 1 — Basic Movement
Goal

Create a reliable mobile platform.

Components
Arduino Uno
L298N motor driver
Four DC motors
Battery
Functions

The robot was programmed to:

Move forward
Move backward
Turn left
Turn right
Stop
Result

The team established the basic movement system that became the foundation for later stages.

🔴 Stage 2 — Fire Detection
Goal

Enable the robot to detect and approach a simulated fire.

Components Added
Flame sensors
Process
Read Sensors
     ↓
Flame Detected?
     ↓
Determine Direction
     ↓
Turn Toward Flame
     ↓
Move Forward

Result

The robot could react to the detected direction of a simulated flame.

🔵 Stage 3 — Fire Extinguishing
Goal

Add the ability to respond to the detected fire.

Components Added
Water tank
Water pump
Servo
Tubing
Nozzle
Process
Detect Fire
     ↓
Approach Fire
     ↓
Stop
     ↓
Position Nozzle
     ↓
Activate Pump
     ↓
Spray Water

Result

The robot gained a water-based fire-extinguishing capability.

🟡 Stage 4 — Smoke Detection
Goal

Add another method of detecting fire-related environmental conditions.

Component Added
MQ-2 smoke/gas sensor
Process
Read MQ-2
     ↓
Evaluate Reading
     ↓
Combine With Other Sensor Data
     ↓
Continue Fire Response

Result

The robot gained an additional environmental sensing capability.

🟣 Stage 5 — Autonomous Navigation
Goal

Improve the robot's ability to navigate its environment.

Component Added
HC-SR04 ultrasonic sensor
Process
Move Forward
     ↓
Check Distance
     ↓
Obstacle?
   /     \
 No       Yes
 ↓         ↓
Move     Stop
          ↓
    Change Direction
          ↓
      Continue

Result

The robot gained obstacle detection and navigation capabilities.

7. Final System

The final system combines the capabilities developed throughout all five stages.

Final Mission
┌─────────────┐
│    START    │
└──────┬──────┘
       ↓
┌─────────────┐
│  Navigate   │
└──────┬──────┘
       ↓
┌─────────────┐
│Check for    │
│  Obstacles  │
└──────┬──────┘
       ↓
┌─────────────┐
│Detect Smoke │
└──────┬──────┘
       ↓
┌─────────────┐
│Detect Flame │
└──────┬──────┘
       ↓
┌─────────────┐
│   Approach  │
│     Fire    │
└──────┬──────┘
       ↓
┌─────────────┐
│    STOP     │
└──────┬──────┘
       ↓
┌─────────────┐
│Activate Pump│
└──────┬──────┘
       ↓
┌─────────────┐
│  Spray Water│
└──────┬──────┘
       ↓
     END


Note: The robot was designed and tested as an educational prototype using a simulated fire environment.

8. Testing

Testing was performed throughout the development process.

Each new feature was tested before moving to the next stage.

Stage	Main Test
1	Movement and motor control
2	Flame detection and direction
3	Pump, servo, and water flow
4	MQ-2 sensor response
5	Obstacle detection and navigation
Testing Method

The general testing cycle was:

Build
  ↓
Test
  ↓
Observe
  ↓
Identify Problem
  ↓
Debug
  ↓
Improve
  ↓
Retest

9. Challenges

During development, the team worked through challenges involving:

Motor control
Sensor readings
Wiring
Power management
Programming logic
Hardware positioning
Sensor integration
Combining multiple subsystems

Breaking the project into five stages made it easier to isolate problems and solve them individually.

10. Team & Contributions

The project was developed collaboratively by an 11-member team.

Team members contributed to areas such as:

Programming
Electronics
Robot construction
Sensor integration
Motor control
Testing
Troubleshooting
Documentation
Team Members
#	Name
1	Abubeker Amru
2	Amar Bahredin
3	Amen Yordanos
4	Biniyam Sisay
5	Delina Gebresilassie
6	Eyosiyas Abiyot
7	Fayo Ibrahim
8	Irfan Jibril
9	Nathan Samuel
10	Natnael Solomon
11	Samuel Abeselom

Contribution details can be added once the individual responsibilities of each team member are documented.

11. Skills Developed
💻 Programming
Arduino
C/C++
Conditional logic
Sensor processing
Motor control
🤖 Robotics
Mobile robotics
Sensor integration
Autonomous navigation
Actuator control
⚡ Electronics
Motor drivers
Sensors
Wiring
Power systems
Hardware troubleshooting
🛠️ Engineering
Prototyping
Iterative development
Testing
Debugging
System integration
👥 Collaboration
Team-based development
Task division
Communication
Coordinating multiple subsystems
12. Limitations

This project is an educational prototype and was designed for a simulated fire environment.

It is not professional firefighting equipment.

Current limitations include:

Limited sensor range
Limited water capacity
Battery limitations
Simplified fire-detection logic
Limited navigation capabilities
Environmental effects on sensor readings
13. Future Improvements

Possible future improvements include:

📷 Camera-based fire detection
🧭 More advanced autonomous navigation
🔥 Improved flame localization
🚧 Better obstacle avoidance
📡 Wireless monitoring
📊 Real-time telemetry
💧 More accurate water targeting
🔋 Improved power management
🗺️ Mapping and navigation
🏠 Automatic return-to-base functionality
14. Project Resources
💻 GitHub

Source code and project files:

https://github.com/Robo-X-team/Fire-fighter

🌐 Project Website

Interactive project documentation:

https://fire-fighter-rho.vercel.app/

📁 Source Code

The five Arduino programs are located in:

code/
├── stage1.ino
├── stage2.ino
├── stage3.ino
├── stage4.ino
└── stage5.ino

15. License

This project is licensed under the MIT License.

See the LICENSE file for the complete license terms.

16. Conclusion

The Firefighter Robot project demonstrates how a complex robotic system can be developed through incremental engineering stages.

Beginning with basic movement, the team progressively added:

Movement → Fire Detection → Extinguishing → Smoke Detection → Autonomous Navigation

The project provided practical experience in programming, electronics, robotics, testing, debugging, system integration, and teamwork.

Most importantly, the project demonstrated an iterative engineering approach:

Design → Build → Test → Debug → Improve

The final result was an educational robotic platform integrating multiple sensors, motors, and actuators into a single system.

🏕️ Project Information

Robo-X Team
EAII Summer Camp — 2026

Design. Build. Test. Improve. 🔥🤖
