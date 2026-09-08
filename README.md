# 🔥🤖 Firefighter Robot

### An Educational Robotics Project by Robo-X Team

> A semi-autonomous firefighter robot designed, built, and programmed by an 11-member team during the **EAII Summer Camp 2026**.

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Project Links](#-project-links)
- [Development Stages](#-development-stages)
- [Final Mission](#-final-mission)
- [System Structure](#-system-structure)
- [Hardware](#-hardware)
- [Source Code](#-source-code)
- [Skills & Technologies](#-skills--technologies)
- [Team](#-team)
- [Project Background](#-project-background)
- [What We Learned](#-what-we-learned)
- [Development Approach](#-development-approach)
- [Project Outcome](#-project-outcome)
- [License](#-license)

---

# 📖 About the Project

The **Firefighter Robot** is a semi-autonomous educational robotics project designed, built, and programmed collaboratively by the **Robo-X Team**, an 11-member team during the **EAII Summer Camp 2026**.

Our goal was to develop a robot capable of detecting a simulated fire, navigating toward it, avoiding obstacles, and activating a water-based extinguishing system.

The project was developed progressively through multiple stages. Instead of building the complete robot at once, the team developed, tested, and improved each system step by step.

The robot combines:

- 🚗 **Mobile movement**
- 🔥 **Flame detection**
- 💨 **Smoke detection**
- 🧭 **Obstacle detection**
- 💧 **Water-based extinguishing**
- 🤖 **Semi-autonomous control**

> ⚠️ **Note:** This robot is an educational prototype designed for simulated fire environments. It is not intended for real-world firefighting operations.

---

# 🌐 Project Links

🔗 **GitHub Repository:**  
https://github.com/Robo-X-team/Fire-fighter

🌐 **Project Website:**  
https://fire-fighter-rho.vercel.app/

---

# 📥 Clone the Repository

To download the project and its source code:

```bash
git clone https://github.com/Robo-X-team/Fire-fighter.git
cd Fire-fighter
```

---

# 📸 Project

## 🤖 The Robot
photo_2026-09-08_22-20-21.jpg

-->

---

## 🛠️ Building & Development

> Add photos showing the team building and assembling the robot here.

---

## 🧪 Testing

> Add photos or videos showing the robot being tested here.

---

# 🚀 Development Stages

The project was developed through a progressive engineering approach.

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

---

## 🟢 Stage 1 — Basic Movement

The first stage focused on developing the robot's basic movement system.

Using an **Arduino Uno**, **L298N motor driver**, and **four DC motors**, the team created the foundation of the robot's mobility system.

### Features

- Move forward
- Move backward
- Turn left
- Turn right
- Stop

This stage created the mobile platform used for the rest of the project.

---

## 🔴 Stage 2 — Fire Detection

During Stage 2, flame sensors were introduced to allow the robot to detect a simulated fire.

The robot uses sensor readings to determine the approximate direction of the flame and respond accordingly.

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

This stage introduced environmental sensing and fire detection to the robotic system.

---

## 🔵 Stage 3 — Fire Extinguishing

The third stage introduced the robot's water-based extinguishing system.

### Components Added

- 💧 Water tank
- 🚿 Water pump
- ⚙️ Servo motor
- 🧪 Tubing
- 🎯 Water nozzle

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

This allowed the robot to physically respond to a detected simulated fire.

---

## 🟡 Stage 4 — Smoke Detection

An **MQ-2 smoke and gas sensor** was added to provide additional environmental detection.

The sensor helps detect conditions associated with smoke or gas.

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

This stage expanded the robot's environmental awareness.

---

## 🟣 Stage 5 — Autonomous Navigation

The final stage introduced obstacle detection and navigation using an **HC-SR04 ultrasonic sensor**.

The sensor measures the distance between the robot and nearby objects.

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

This improved the robot's ability to navigate through its environment.

---

# 🎯 Final Mission

The completed robot combines all the systems developed throughout the five stages.

```text
START
  ↓
Navigate
  ↓
Avoid Obstacles
  ↓
Detect Smoke
  ↓
Detect Flame
  ↓
Approach Fire
  ↓
STOP
  ↓
Activate Water System
  ↓
Spray Water
  ↓
END
```

The final system integrates movement, sensors, navigation, and the water-based extinguishing mechanism into one robotic platform.

---

# ⚙️ System Structure

The **Arduino Uno** acts as the central controller of the robot.

It receives information from the sensors, processes the data using programmed logic, and controls the robot's movement and extinguishing systems.

```text
                    ┌──────────────────┐
                    │   ARDUINO UNO    │
                    │ Main Controller  │
                    └────────┬─────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ▼                  ▼                  ▼
   ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
   │   Flame     │    │    MQ-2     │    │   HC-SR04   │
   │  Sensors    │    │ Smoke Sensor│    │ Ultrasonic  │
   └──────┬──────┘    └──────┬──────┘    └──────┬──────┘
          │                  │                  │
          └──────────────────┼──────────────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │  CONTROL LOGIC   │
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
          4 DC Motors                Pump + Servo
```

---

# 🧰 Hardware

| Component | Purpose |
|---|---|
| 🧠 Arduino Uno | Main controller |
| ⚙️ L298N Motor Driver | Controls the DC motors |
| 🚗 4 × DC Motors | Robot movement |
| 🔥 Flame Sensors | Fire detection |
| 💨 MQ-2 Sensor | Smoke and gas detection |
| 📏 HC-SR04 | Obstacle detection |
| 🔄 Servo Motor | Controls nozzle positioning |
| 💧 Water Pump | Pumps water toward the target |
| 🛢️ Water Tank | Stores water |
| 💡 LED | Status indication |
| 🔋 Battery | Power source |
| 🔌 Breadboard | Circuit connections |
| 🧵 Jumper Wires | Electrical connections |

---

# 💻 Source Code

The project was developed using **Arduino and C/C++**.

The source code is organized by development stages:

```text
code/
├── stage1.ino
├── stage2.ino
├── stage3.ino
├── stage4.ino
└── stage5.ino
```

Each stage represents a milestone in the development of the Firefighter Robot.

---

# 🧠 Skills & Technologies

### 💻 Programming

- Arduino
- C/C++
- Embedded programming
- Conditional logic
- Sensor processing

### 🤖 Robotics

- Mobile robotics
- Motor control
- Sensor integration
- Autonomous navigation
- Actuator control

### ⚡ Electronics

- Motor drivers
- Flame sensors
- Smoke sensors
- Ultrasonic sensors
- Servo motors
- Water pumps
- Circuit wiring

### 🛠️ Engineering

- Prototyping
- System integration
- Testing
- Debugging
- Hardware troubleshooting
- Iterative development

### 👥 Collaboration

- Team-based development
- Task division
- Communication
- Problem solving
- Coordinating multiple subsystems

---

# 👥 Team

This project was developed collaboratively by the **Robo-X Team**.

| # | Team Member |
|---|---|
| 1 | Abubeker Amru |
| 2 | Amar Bahredin |
| 3 | Amen Yordanos |
| 4 | Biniyam Sisay |
| 5 | Delina Gebresilassie |
| 6 | Eyosiyas Abiyot |
| 7 | Fayo Ibrahim |
| 8 | Irfan Jibril |
| 9 | Nathan Samuel |
| 10 | Natnael Solomon |
| 11 | Samuel Abeselom |

The project represents the collaborative work of the entire team across areas including programming, electronics, construction, testing, troubleshooting, sensor integration, and documentation.

---

# 🏕️ Project Background

### EAII Summer Camp — 2026

The Firefighter Robot was developed as a hands-on educational robotics project during the **EAII Summer Camp 2026**.

The project gave the Robo-X Team an opportunity to apply engineering concepts in a practical environment.

Throughout the project, the team designed, built, programmed, tested, and improved a working robotic system.

---

# 📚 What We Learned

Through the development of this project, the team gained practical experience in:

- 🤖 Designing and building robotic systems
- 💻 Programming microcontrollers
- 🔥 Working with environmental sensors
- ⚙️ Controlling motors and actuators
- 🔌 Integrating hardware and software
- 🛠️ Debugging electrical and programming problems
- 🧪 Testing systems incrementally
- 👥 Collaborating as a large engineering team

---

# 📈 Development Approach

Rather than attempting to build the complete robot at once, the Robo-X Team divided the project into progressive development stages.

This allowed the team to:

1. Build individual systems
2. Test each feature
3. Identify problems
4. Debug the system
5. Improve the design
6. Integrate new components

The engineering cycle followed throughout the project was:

```text
Design
  ↓
Build
  ↓
Test
  ↓
Observe
  ↓
Identify Problems
  ↓
Debug
  ↓
Improve
  ↓
Retest
```

This incremental approach made it easier to understand and solve problems as the complexity of the robot increased.

---

# ⭐ Project Outcome

The final result was a working educational firefighter robot that combines multiple systems into one robotic platform.

The project integrates:

**Movement**  
⬇️  
**Fire Detection**  
⬇️  
**Smoke Detection**  
⬇️  
**Obstacle Detection**  
⬇️  
**Navigation**  
⬇️  
**Water-Based Extinguishing**

The Firefighter Robot demonstrates how a complex engineering project can be developed progressively through testing, debugging, collaboration, and continuous improvement.

More importantly, the project represents the combined effort and learning experience of the **11-member Robo-X Team**.

---

# 🔮 Future Improvements

Possible future improvements include:

- 📷 Camera-based fire detection
- 🧠 Computer vision
- 🧭 Advanced autonomous navigation
- 🔥 Improved flame localization
- 🚧 Better obstacle avoidance
- 📡 Wireless monitoring
- 📊 Real-time telemetry
- 💧 More accurate water targeting
- 🔋 Improved power management
- 🗺️ Mapping and navigation
- 🏠 Automatic return-to-base functionality

---

# 📄 License

This project is licensed under the **MIT License**.

See the [LICENSE](LICENSE) file for more information.

---

<div align="center">

## 🔥🤖 Robo-X Team

### EAII Summer Camp — 2026

**Design. Build. Test. Debug. Improve.**

⭐ *Building ideas into reality through teamwork and engineering.*

</div>
