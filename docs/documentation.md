Firefighter Robot — Technical Documentation

Team: Robo-X Team
Program: EAII Summer Camp
Year: 2026
Team Members: 11

1. Project Overview

The Firefighter Robot is a robotics project developed by the Robo-X Team at EAII Summer Camp 2026.

The goal of the project was to design and build a robot that could detect a simulated fire, move toward it, and activate a water-based extinguishing system.

The robot was developed through five stages. Each stage introduced a new feature and allowed the team to test the system before moving to the next stage.

Development progression
Stage 1 → Basic Movement
     ↓
Stage 2 → Fire Detection
     ↓
Stage 3 → Water Extinguishing
     ↓
Stage 4 → Smoke Detection
     ↓
Stage 5 → Autonomous Navigation

2. Objectives

The main objectives of the project were:

Build a functional mobile robot.
Control four DC motors.
Detect a simulated flame.
Determine the approximate direction of the flame.
Navigate toward the fire.
Detect smoke/gas using an MQ-2 sensor.
Detect obstacles using an ultrasonic sensor.
Activate a water pump to extinguish the simulated fire.
Integrate multiple sensors and actuators into one system.
Develop practical robotics, programming, electronics, and teamwork skills.
3. System Architecture

The Arduino Uno acts as the main controller.

It receives information from the sensors and sends commands to the motors and other actuators.

                    ┌───────────────────┐
                    │    Arduino Uno    │
                    │  Main Controller  │
                    └─────────┬─────────┘
                              │
          ┌───────────────────┼───────────────────┐
          │                   │                   │
          ▼                   ▼                   ▼
   Flame Sensors         MQ-2 Sensor        HC-SR04 Sensor
   Fire Detection       Smoke Detection     Obstacle Detection
          │                   │                   │
          └───────────────────┼───────────────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │   Control Logic   │
                    └─────────┬─────────┘
                              │
                  ┌───────────┴───────────┐
                  │                       │
                  ▼                       ▼
           ┌─────────────┐       ┌─────────────┐
           │ L298N Motor │       │ Extinguishing│
           │ Driver      │       │ System       │
           └──────┬──────┘       └──────┬──────┘
                  │                     │
                  ▼                     ▼
             4 DC Motors          Pump + Servo

4. Hardware Components
4.1 Arduino Uno

The Arduino Uno is the main microcontroller.

It processes sensor readings and controls the robot's movement and other components.

4.2 L298N Motor Driver

The L298N provides motor control between the Arduino and the four DC motors.

It allows the robot to control motor direction and movement.

4.3 DC Motors

Four DC motors provide movement for the robot.

The motors allow the robot to move:

Forward
Backward
Left
Right
Stop
4.4 Flame Sensors

Flame sensors detect the presence and approximate direction of a simulated flame.

Multiple sensors allow the robot to compare readings from different directions.

4.5 MQ-2 Sensor

The MQ-2 smoke/gas sensor was introduced during Stage 4.

It provides additional environmental information that can be used alongside the flame sensors.

4.6 HC-SR04 Ultrasonic Sensor

The HC-SR04 is used for obstacle detection.

It measures the distance between the robot and nearby objects.

4.7 Servo Motor

The servo is part of the water-extinguishing mechanism and is used to control the position of the mechanism/nozzle.

4.8 Water Pump

The water pump moves water from the tank through the tubing and nozzle.

It is activated when the robot performs the extinguishing sequence.

5. Software

The robot was programmed using Arduino/C++.

The software was developed incrementally rather than creating the complete program at once.

Each stage has its own .ino file:

code/
├── stage1.ino
├── stage2.ino
├── stage3.ino
├── stage4.ino
└── stage5.ino


This makes it possible to see how the robot's software developed over time.

6. Stage 1 — Basic Movement

The first stage focused on controlling the robot's movement.

Components
Arduino Uno
L298N motor driver
Four DC motors
Battery
Functions

The program controls the motors to perform:

Forward
Backward
Left
Right
Stop

Development Goal

The main goal was to create a reliable movement system that could be used as the foundation for the later stages.

7. Stage 2 — Fire Detection

Stage 2 introduced flame sensors.

The robot could detect a simulated flame and determine its approximate direction.

Basic control process
Read Flame Sensors
       ↓
Flame Detected?
       ↓
Determine Direction
       ↓
Turn Toward Flame
       ↓
Move Forward


The robot's movement could therefore respond to its environment instead of following only predetermined commands.

8. Stage 3 — Fire Extinguishing

Stage 3 introduced the water-extinguishing system.

Components added
Water tank
Water pump
Servo motor
Tubing
Nozzle
Operation

Once the robot approaches the simulated fire, the extinguishing mechanism can be activated.

Detect Fire
     ↓
Approach Fire
     ↓
Stop
     ↓
Position Extinguishing System
     ↓
Activate Pump
     ↓
Spray Water


This stage transformed the robot from a detection system into a response system.

9. Stage 4 — Smoke Detection

Stage 4 introduced an MQ-2 smoke/gas sensor.

The purpose was to provide an additional method of detecting environmental conditions associated with a simulated fire.

Basic process
Read MQ-2 Sensor
       ↓
Evaluate Sensor Reading
       ↓
Combine With Other Sensor Information
       ↓
Fire Response


The additional sensor increased the amount of environmental information available to the robot.

10. Stage 5 — Autonomous Navigation

Stage 5 introduced obstacle detection using an HC-SR04 ultrasonic sensor.

The robot could use distance information to identify obstacles and adjust its movement.

Basic navigation process
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


The final stage combined the navigation system with the other capabilities developed previously.

11. Final Robot Operation

The final system follows a general sequence:

START
  ↓
Navigate
  ↓
Check for Obstacles
  ↓
Avoid Obstacles if Necessary
  ↓
Detect Smoke
  ↓
Detect Flame
  ↓
Determine Fire Direction
  ↓
Approach Fire
  ↓
Stop
  ↓
Activate Extinguishing System
  ↓
Spray Water
  ↓
END


The exact behavior depends on the sensor readings and the control logic implemented in the final program.

12. Structure Diagram

The project's system structure and wiring can be documented using the structure diagram included with the project.

The interactive project website also contains additional project information:

Project Website:
https://fire-fighter-rho.vercel.app/

13. Testing

Testing was performed progressively throughout development.

Instead of waiting until the final stage, each major feature was tested after implementation.

Stage 1

Movement was tested by checking:

Forward movement
Backward movement
Left turns
Right turns
Stopping
Stage 2

The flame sensors were tested with the simulated fire positioned in different directions.

The team observed whether the robot responded appropriately.

Stage 3

The water system was tested to verify:

Pump activation
Water flow
Servo movement
Extinguishing mechanism operation
Stage 4

The MQ-2 sensor was tested in the intended simulated environment.

Stage 5

The ultrasonic sensor was tested by placing obstacles at different distances from the robot.

14. Challenges

During development, the team encountered challenges involving:

Motor control
Sensor readings
Electrical wiring
Power management
Programming logic
Hardware/software integration
Physical placement of components
Testing the complete system

The staged development process helped the team isolate problems and address them individually.

15. Development Methodology

The team used an iterative development approach.

Design
  ↓
Build
  ↓
Test
  ↓
Find Problems
  ↓
Debug
  ↓
Improve
  ↓
Next Stage


This approach made it easier to identify problems early and improve the robot gradually.

16. Team Contributions

The project was developed collaboratively by an 11-member team.

Different members contributed to different areas, including:

Programming
Electronics
Robot construction
Sensor integration
Motor control
Testing
Troubleshooting
Documentation

Individual contributions should be documented here according to the actual work performed by each team member.

17. Team Members
Abubeker Amru
Amar Bahredin
Amen Yordanos
Biniyam Sisay
Delina Gebresilassie
Eyosiyas Abiyot
Fayo Ibrahim
Irfan Jibril
Nathan Samuel
Natnael Solomon
Samuel Abeselom
18. Skills Developed

The project provided hands-on experience in:

Programming
Arduino
C/C++
Conditional logic
Sensor input
Motor control
Robotics
Mobile robotics
Sensor integration
Autonomous navigation
Actuator control
Electronics
Motor drivers
Sensors
Wiring
Power systems
Troubleshooting
Engineering
Prototyping
Iterative development
Testing
Debugging
System integration
Teamwork
Collaborative development
Dividing responsibilities
Communication
Coordinating multiple subsystems
19. Limitations

This robot is an educational prototype designed for a simulated fire environment.

It is not intended to replace professional firefighting equipment.

Potential limitations include:

Limited sensor range
Limited water capacity
Battery limitations
Simplified fire-detection logic
Limited navigation capabilities
Sensor readings can be affected by environmental conditions
20. Future Improvements

Future versions could include:

Camera-based fire detection
Improved flame localization
More advanced obstacle avoidance
Wireless monitoring
Real-time telemetry
Improved water targeting
Larger water capacity
More efficient power management
More advanced navigation algorithms
Automatic return-to-base functionality
21. Project Resources
GitHub Repository

https://github.com/Robo-X-team/Fire-fighter

Project Website

https://fire-fighter-rho.vercel.app/

Source Code

The Arduino programs for all five development stages are located in the code directory.

22. License

This project is licensed under the MIT License.

See the LICENSE file for the complete license text.

23. Conclusion

The Firefighter Robot project demonstrates how a complex robotic system can be developed through incremental stages.

Starting with basic movement, the team progressively introduced fire detection, water extinguishing, smoke detection, and autonomous navigation.

The project provided practical experience in robotics, programming, electronics, testing, debugging, system integration, and teamwork.

The five-stage development process allowed the team to build and test individual capabilities before integrating them into the final robotic system.

Project Information

Robo-X Team
EAII Summer Camp
2026

Design. Build. Test. Improve.
