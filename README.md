🔥🤖 Firefighter Robot

A semi-autonomous firefighter robot designed, built, and programmed by an 11-member team at EAII Summer Camp 2026.

Our goal was to develop a robot capable of detecting a simulated fire, navigating toward it, and extinguishing it. We developed the robot progressively through five stages, testing and improving the system at each step.

🌐 Project Links
	
GitHub Repository	https://github.com/lordcode-dev/Fire-fighter/
Project Website	https://fire-fighter-rho.vercel.app/
📥 Clone the Repository

To download the project and its source code:

git clone https://github.com/lordcode-dev/Fire-fighter.git
cd Fire-fighter

📸 Project
The Robot
Building & Development
Testing
🚀 Development Stages
Stage 1 — Basic Movement

We developed the robot's basic movement system using an Arduino Uno, motor driver, and four DC motors.

The robot was programmed to move forward, backward, and turn left and right.

Stage 2 — Fire Detection

We introduced flame sensors to allow the robot to detect the direction of a simulated fire.

The robot could use the sensor readings to determine where the flame was located and move toward it.

Stage 3 — Fire Extinguishing

We added a water-based extinguishing system consisting of a water tank, pump, servo motor, tubing, and nozzle.

The robot could approach the detected fire and activate the water system.

Stage 4 — Smoke Detection

An MQ-2 smoke/gas sensor was integrated into the system to provide additional environmental detection.

This stage expanded the robot's ability to identify conditions associated with a simulated fire.

Stage 5 — Autonomous Navigation

The final stage added obstacle detection and navigation using an HC-SR04 ultrasonic sensor.

The completed system combined the capabilities developed throughout the previous stages.

Final mission:
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
Stop
   ↓
Activate Water System

🔌 System Structure

The robot combines an Arduino-based control system with motor control, environmental sensors, fire detection, and a water-extinguishing mechanism.

The complete structure and wiring documentation are available on our project website.

💻 Source Code

Each development stage has its own Arduino program.

code/
├── stage1.ino
├── stage2.ino
├── stage3.ino
├── stage4.ino
└── stage5.ino


The five programs demonstrate how the robot evolved from basic movement into the final integrated system.

🧰 Hardware
Arduino Uno
L298N motor driver
4 DC motors
Flame sensors
MQ-2 smoke/gas sensor
HC-SR04 ultrasonic sensor
Servo motor
Water pump
Water tank
LED
Battery
Breadboard and jumper wires
🧠 Skills & Technologies
Arduino / Embedded Programming
C/C++
Robotics
Electronics
Sensor Integration
Motor Control
Autonomous Navigation
Hardware Troubleshooting
System Integration
Team Collaboration
👥 Team

This project was developed collaboratively by:

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
🏕️ Project Background

EAII Summer Camp — 2026

The project was developed as a hands-on robotics project where our team learned to design, program, build, test, and improve a working robotic system.

📚 What We Learned

Throughout the project, we gained practical experience in:

Designing and building robotic systems
Programming microcontrollers
Working with sensors and actuators
Integrating hardware and software
Debugging electrical and programming problems
Testing systems incrementally
Collaborating as a large engineering team
📈 Development Approach

Rather than attempting to build the complete robot at once, we divided the project into five stages.

This allowed us to build, test, identify problems, and improve the system at each stage before moving forward.

Stage 1
Basic Movement
    ↓
Stage 2
Fire Detection
    ↓
Stage 3
Water Extinguishing
    ↓
Stage 4
Smoke Detection
    ↓
Stage 5
Autonomous Navigation

⭐ Project Outcome

The final result was a working firefighter robot that combined multiple sensing, movement, navigation, and extinguishing systems into one robotic platform.

Built by our team at EAII Summer Camp 2026.
