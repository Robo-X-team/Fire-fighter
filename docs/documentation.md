# 🔥🤖 Firefighter Robot

# Technical Project Documentation

<div align="center">

|                     |                      |
| ------------------- | -------------------- |
| **Team**            | Robo-X Team          |
| **Program**         | EAII Summer Camp     |
| **Year**            | 2026                 |
| **Team Size**       | 11 Members           |
| **Project Type**    | Educational Robotics |
| **Main Controller** | Arduino Uno          |

</div>

---

# 📖 Table of Contents

* [1. Project Overview](#1-project-overview)
* [2. Project Objectives](#2-project-objectives)
* [3. System Architecture](#3-system-architecture)
* [4. Hardware Components](#4-hardware-components)
* [5. Software](#5-software)
* [6. Development Stages](#6-development-stages)
* [7. Final System](#7-final-system)
* [8. Testing](#8-testing)
* [9. Challenges](#9-challenges)
* [10. Team](#10-team)
* [11. Skills Developed](#11-skills-developed)
* [12. Limitations](#12-limitations)
* [13. Future Improvements](#13-future-improvements)
* [14. Project Resources](#14-project-resources)
* [15. License](#15-license)
* [16. Conclusion](#16-conclusion)

---

# 1. Project Overview

The **Firefighter Robot** is a multi-stage educational robotics project developed collaboratively by the **Robo-X Team** during the **EAII Summer Camp 2026**.

The project was created to demonstrate how robotics, electronics, sensors, actuators, and embedded programming can be combined to create a robotic system capable of detecting and responding to a **simulated fire environment**.

The robot was designed as a semi-autonomous platform capable of combining multiple systems, including:

* 🚗 Mobile movement
* 🔥 Flame detection
* 💨 Smoke and gas detection
* 🧭 Obstacle detection
* 💧 Water-based fire extinguishing
* 🤖 Semi-autonomous control

Rather than developing the complete system all at once, the Robo-X Team used a progressive development approach.

The robot was built and improved through several stages:

```text
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
```

This approach allowed the team to build, test, debug, and improve individual subsystems before integrating them into a more complex robotic platform.

> ⚠️ **Important:** The Firefighter Robot is an educational prototype designed and tested in controlled environments using simulated fire conditions. It is not professional firefighting equipment.

---

# 2. Project Objectives

The Robo-X Team established several objectives for the project.

The main objectives were to:

* Build a functional four-wheel robotic platform
* Control multiple DC motors using an Arduino Uno
* Develop reliable forward, backward, and turning movement
* Detect a simulated flame using flame sensors
* Determine the approximate direction of a detected flame
* Navigate toward the simulated fire
* Detect smoke or gas using an MQ-2 sensor
* Detect obstacles using an HC-SR04 ultrasonic sensor
* Develop a water-based extinguishing system
* Control a water pump and servo mechanism
* Integrate multiple sensors and actuators
* Test and improve individual robotic subsystems
* Gain practical experience in robotics and electronics
* Develop teamwork and engineering problem-solving skills

---

# 3. System Architecture

The **Arduino Uno** acts as the central controller of the Firefighter Robot.

It receives input from the robot's sensors, processes the information using programmed control logic, and sends commands to the movement and extinguishing systems.

The overall system architecture is shown below:

```text
                         ┌──────────────────┐
                         │   ARDUINO UNO    │
                         │ Main Controller  │
                         └────────┬─────────┘
                                  │
            ┌─────────────────────┼─────────────────────┐
            │                     │                     │
            ▼                     ▼                     ▼
     ┌─────────────┐       ┌─────────────┐       ┌─────────────┐
     │    Flame    │       │    MQ-2     │       │   HC-SR04   │
     │   Sensors   │       │ Smoke Sensor│       │ Ultrasonic  │
     └──────┬──────┘       └──────┬──────┘       └──────┬──────┘
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
             │    L298N    │             │ Extinguishing│
             │ Motor Driver│             │    System    │
             └──────┬──────┘             └──────┬──────┘
                    │                           │
                    ▼                           ▼
               4 DC Motors                 Pump + Servo
```

---

## 3.1 System Operation

The robot follows a general decision-making process.

```text
START
  ↓
Navigate Through Environment
  ↓
Check for Obstacles
  ↓
Monitor Environmental Sensors
  ↓
Detect Smoke or Gas
  ↓
Detect Flame
  ↓
Determine Fire Direction
  ↓
Approach Target
  ↓
Stop at Safe Distance
  ↓
Position Water System
  ↓
Activate Water Pump
  ↓
Spray Water
  ↓
END
```

The exact behavior of the robot depends on the stage of development and the integrated hardware systems.

---

# 4. Hardware Components

## 4.1 Component Overview

| Component          |    Quantity | Purpose                             |
| ------------------ | ----------: | ----------------------------------- |
| Arduino Uno        |           1 | Main controller                     |
| L298N Motor Driver |           1 | Controls the DC motors              |
| DC Motors          |           4 | Robot movement                      |
| Flame Sensors      |    Multiple | Flame detection                     |
| MQ-2 Sensor        |           1 | Smoke and gas detection             |
| HC-SR04 Sensor     |           1 | Obstacle detection                  |
| Servo Motor        |           1 | Controls water system positioning   |
| Water Pump         |           1 | Pumps water to the target           |
| Water Tank         |           1 | Stores water                        |
| LED                |          1+ | Status indication                   |
| Battery            |           1 | Provides electrical power           |
| Breadboard         |           1 | Circuit connections and prototyping |
| Jumper Wires       |    Multiple | Electrical connections              |
| Tubing             | As required | Water delivery                      |
| Nozzle             |           1 | Directs water toward the target     |

---

## 4.2 Arduino Uno

The **Arduino Uno** is the main controller of the robot.

It coordinates communication between the sensors and the output systems.

### Main Responsibilities

The Arduino is responsible for:

* Reading sensor values
* Processing sensor information
* Executing programmed control logic
* Controlling motor movement
* Controlling direction
* Monitoring obstacles
* Controlling the servo motor
* Activating the water pump
* Coordinating the overall robot behavior

---

## 4.3 L298N Motor Driver

The **L298N motor driver** provides the connection between the Arduino and the DC motors.

The Arduino sends control signals to the L298N, while the motor driver provides the required motor control functionality.

The motor driver allows the robot to:

* Move forward
* Move backward
* Turn left
* Turn right
* Stop

The L298N is an important component because the Arduino cannot directly power the DC motors.

---

## 4.4 DC Motors and Movement System

The robot uses four DC motors to create a four-wheel-drive mobile platform.

The motors are controlled through the L298N motor driver.

By changing the direction of the motors, the robot can perform different movement operations.

### Basic Movement Functions

| Movement | Description          |
| -------- | -------------------- |
| Forward  | Robot moves ahead    |
| Backward | Robot moves backward |
| Left     | Robot turns left     |
| Right    | Robot turns right    |
| Stop     | Motors are stopped   |

The movement system was developed first because all later stages depend on the robot being able to move reliably.

---

## 4.5 Flame Sensors

Flame sensors are used to detect the presence of a simulated flame.

Multiple sensors can be used to compare readings from different directions.

This allows the robot to estimate where the flame is located.

### General Process

```text
Read Flame Sensors
        ↓
Flame Detected?
      /     \
    No       Yes
    ↓         ↓
Continue   Compare Sensors
Movement        ↓
           Determine Direction
                  ↓
            Turn Toward Flame
                  ↓
              Move Forward
```

---

## 4.6 MQ-2 Smoke and Gas Sensor

The **MQ-2 sensor** provides smoke and gas detection.

It gives the robot additional environmental information that can be used alongside flame sensor data.

The MQ-2 sensor was introduced during the smoke detection stage of development.

### Purpose

* Detect smoke-related environmental conditions
* Detect certain combustible gases
* Provide additional environmental awareness
* Support the simulated fire detection process

---

## 4.7 HC-SR04 Ultrasonic Sensor

The **HC-SR04 ultrasonic sensor** is used for obstacle detection.

It measures the approximate distance between the robot and nearby objects.

The robot can use this information to decide whether it can continue moving forward or needs to stop and change direction.

### Navigation Logic

```text
Move Forward
     ↓
Measure Distance
     ↓
Obstacle Detected?
   /             \
 No               Yes
 ↓                 ↓
Continue         Stop
                    ↓
             Change Direction
                    ↓
                Continue
```

---

## 4.8 Water Extinguishing System

The Firefighter Robot uses a water-based system to respond to a detected simulated fire.

### Components

* Water tank
* Water pump
* Servo motor
* Tubing
* Nozzle

The pump moves water from the tank through the tubing.

The servo motor can be used to position or control the direction of the water delivery mechanism.

### Extinguishing Process

```text
Fire Detected
      ↓
Approach Target
      ↓
Stop
      ↓
Position Nozzle
      ↓
Activate Water Pump
      ↓
Spray Water
```

---

# 5. Software

The Firefighter Robot was programmed using:

* **Arduino**
* **C/C++**

The software was developed progressively to match the development stages of the robot.

Each stage represents a milestone in the project.

### Planned Code Structure

```text
code/
├── stage1.ino
├── stage2.ino
├── stage3.ino
├── stage4.ino
└── stage5.ino
```

Each program is intended to demonstrate the evolution of the robot from a basic mobile platform into a more advanced integrated system.

---

# 6. Development Stages

## 🟢 Stage 1 — Basic Movement

### Goal

Create a reliable mobile robotic platform.

### Components

* Arduino Uno
* L298N Motor Driver
* Four DC Motors
* Battery

### Functions

The robot was programmed to:

* Move forward
* Move backward
* Turn left
* Turn right
* Stop

### Result

The team successfully developed the basic movement system that became the foundation for the remaining stages of the project.

---

## 🔴 Stage 2 — Fire Detection

### Goal

Enable the robot to detect and respond to a simulated flame.

### Components Added

* Flame sensors

### Process

```text
Read Sensors
     ↓
Flame Detected?
     ↓
Determine Direction
     ↓
Turn Toward Flame
     ↓
Move Forward
```

### Result

The robot gained the ability to detect the approximate direction of a simulated flame and respond using sensor information.

---

## 🔵 Stage 3 — Fire Extinguishing

### Goal

Add a physical response mechanism to the robot.

### Components Added

* Water tank
* Water pump
* Servo motor
* Tubing
* Nozzle

### Process

```text
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
```

### Result

The robot gained a water-based extinguishing capability for responding to simulated fires.

---

## 🟡 Stage 4 — Smoke Detection

### Goal

Add another method of environmental detection.

### Component Added

* MQ-2 Smoke and Gas Sensor

### Process

```text
Read MQ-2 Sensor
        ↓
Evaluate Reading
        ↓
Combine With Other Sensor Data
        ↓
Continue Fire Response
```

### Result

The robot gained additional environmental sensing capabilities.

---

## 🟣 Stage 5 — Autonomous Navigation

### Goal

Improve the robot's ability to navigate through its environment.

### Component Added

* HC-SR04 Ultrasonic Sensor

### Process

```text
Move Forward
     ↓
Check Distance
     ↓
Obstacle?
   /       \
 No         Yes
 ↓           ↓
Move        Stop
              ↓
      Change Direction
              ↓
          Continue
```

### Result

The robot gained obstacle detection and improved navigation capabilities.

---

# 7. Final System

The final system combines the capabilities developed throughout all five stages.

## Final Mission

```text
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
│ Obstacles   │
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
│  Approach   │
│    Fire     │
└──────┬──────┘
       ↓
┌─────────────┐
│    STOP     │
└──────┬──────┘
       ↓
┌─────────────┐
│Position     │
│Water System │
└──────┬──────┘
       ↓
┌─────────────┐
│Activate Pump│
└──────┬──────┘
       ↓
┌─────────────┐
│ Spray Water │
└──────┬──────┘
       ↓
     END
```

The final robot integrates movement, sensing, navigation, and a water-based response mechanism into a single educational robotic platform.

---

# 8. Testing

Testing was performed throughout the development process.

Each major subsystem was tested before new features were added.

## Testing Areas

| Stage   | Main Test                         |
| ------- | --------------------------------- |
| Stage 1 | Motor movement and direction      |
| Stage 2 | Flame detection and direction     |
| Stage 3 | Pump, servo, and water flow       |
| Stage 4 | MQ-2 sensor response              |
| Stage 5 | Obstacle detection and navigation |

---

## Testing Process

The general testing cycle followed by the team was:

```text
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
```

Testing allowed the team to identify problems early and improve each subsystem before integrating additional features.

---

# 9. Challenges

During development, the Robo-X Team worked through several engineering challenges.

These included:

* Motor control
* Sensor readings
* Circuit wiring
* Hardware placement
* Power management
* Programming logic
* Sensor calibration
* Pump integration
* Combining multiple subsystems
* Troubleshooting hardware problems
* Coordinating development across a large team

Breaking the project into multiple stages made it easier to isolate problems and solve them individually.

---

# 10. Team

The Firefighter Robot was developed collaboratively by the **Robo-X Team**.

The project involved an 11-member team working together across different areas of robotics and engineering.

## Team Members

|  # | Name                 |
| -: | -------------------- |
|  1 | Abubeker Amru        |
|  2 | Amar Bahredin        |
|  3 | Amen Yordanos        |
|  4 | Biniyam Sisay        |
|  5 | Delina Gebresilassie |
|  6 | Eyosiyas Abiyot      |
|  7 | Fayo Ibrahim         |
|  8 | Irfan Jibril         |
|  9 | Nathan Samuel        |
| 10 | Natnael Solomon      |
| 11 | Samuel Abeselom      |

## Team Contributions

The team collaborated across areas including:

* 💻 Programming
* ⚡ Electronics
* 🤖 Robot construction
* 🔥 Sensor integration
* ⚙️ Motor control
* 🧪 Testing
* 🛠️ Troubleshooting
* 📚 Documentation

The Firefighter Robot represents the combined effort of the entire Robo-X Team.

---

# 11. Skills Developed

The project provided practical experience across several areas of technology and engineering.

## 💻 Programming

* Arduino programming
* C/C++
* Conditional logic
* Sensor processing
* Motor control

## 🤖 Robotics

* Mobile robotics
* Sensor integration
* Semi-autonomous systems
* Obstacle detection
* Actuator control

## ⚡ Electronics

* Motor drivers
* Sensors
* Circuit wiring
* Power systems
* Hardware troubleshooting

## 🛠️ Engineering

* Prototyping
* Iterative development
* Testing
* Debugging
* System integration

## 👥 Collaboration

* Team-based development
* Task division
* Communication
* Problem solving
* Coordinating multiple subsystems

---

# 12. Limitations

The Firefighter Robot is an educational prototype and was designed for simulated fire environments.

It is not professional firefighting equipment.

Current limitations include:

* Limited sensor range
* Limited water capacity
* Battery limitations
* Simplified fire detection logic
* Limited navigation capabilities
* Environmental effects on sensor readings
* Limited autonomous decision-making

These limitations provide opportunities for future development and improvement.

---

# 13. Future Improvements

The project could be expanded with more advanced technologies.

Possible future improvements include:

* 📷 Camera-based fire detection
* 🧠 Computer vision
* 🧭 More advanced autonomous navigation
* 🔥 Improved flame localization
* 🚧 Better obstacle avoidance
* 📡 Wireless monitoring
* 📊 Real-time telemetry
* 💧 More accurate water targeting
* 🔋 Improved power management
* 🗺️ Mapping and navigation
* 🏠 Automatic return-to-base functionality
* 🤖 More advanced autonomous decision-making

---

# 14. Project Resources

## 💻 GitHub Repository

Source code and project files:

https://github.com/Robo-X-team/Fire-fighter

---

## 🌐 Project Website

Interactive project documentation and project information:

https://fire-fighter-rho.vercel.app/

---

## 📁 Documentation

Additional technical information is available in:

```text
docs/
└── documentation.md
```

---

# 15. License

This project is licensed under the **MIT License**.

See the [`LICENSE`](../LICENSE) file for the complete license terms.

---

# 16. Conclusion

The **Firefighter Robot** project demonstrates how a complex robotic system can be developed using an incremental engineering approach.

The Robo-X Team began with a basic four-wheel movement system and progressively introduced additional technologies and capabilities.

```text
Movement
    ↓
Fire Detection
    ↓
Fire Extinguishing
    ↓
Smoke Detection
    ↓
Autonomous Navigation
```

Throughout the project, the team applied an iterative engineering process:

```text
Design
  ↓
Build
  ↓
Test
  ↓
Debug
  ↓
Improve
```

The final result is an educational semi-autonomous robotic platform that integrates motors, sensors, actuators, navigation systems, and a water-based response mechanism.

More importantly, the project provided the **11-member Robo-X Team** with practical experience in robotics, programming, electronics, engineering, testing, debugging, system integration, and teamwork.

---

<div align="center">

# 🔥🤖 Robo-X Team

### EAII Summer Camp — 2026

**Design. Build. Test. Debug. Improve.**

*Turning ideas into working technology through teamwork and engineering.*

</div>
