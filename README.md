# 🔥 FIREBUDDY – Automatic Fire Extinguishing Robot

An intelligent robotic fire-response system that detects flames, navigates autonomously, avoids obstacles and automatically activates a water-based fire extinguishing mechanism. The robot also supports Wi-Fi-based remote manual control using ESP32.

---

## 📌 Project Overview

Fire accidents pose serious threats to human life and property. Traditional firefighting methods often require people to enter hazardous environments, exposing them to extreme temperatures, smoke and other dangers.

**FIREBUDDY** is a physical working prototype developed to automate initial fire-response operations using robotics, embedded systems and Internet of Things (IoT) technology.

The robot uses multiple flame sensors to detect fire and identify its approximate direction. An Arduino Uno processes sensor readings and controls the robot's movement. An ultrasonic sensor helps detect obstacles, while an L298N motor driver controls the DC motors.

When the robot reaches a suitable position, it activates a relay-controlled water pump to extinguish the fire. A servo motor adjusts the direction of the water spray. The pump automatically stops when the flame sensors indicate that the fire is no longer detected.

The system supports both autonomous operation and Wi-Fi-based manual control through ESP32.

## 🎯 Project Objectives

- Develop an automated fire detection and extinguishing robot.
- Detect flames using multiple flame sensors.
- Identify the approximate direction of the detected fire.
- Navigate towards the fire autonomously.
- Detect and avoid obstacles using an ultrasonic sensor.
- Automatically activate and deactivate the water pump.
- Control the water-spraying direction using a servo motor.
- Enable remote manual operation through Wi-Fi.
- Reduce the need for direct human involvement during initial fire response.

## ⚙️ Key Features

| Feature | Description |
|---|---|
| 🔥 Fire Detection | Multiple flame sensors detect flames from different directions. |
| 🧭 Direction Identification | Compares sensor readings to estimate fire direction. |
| 🤖 Autonomous Navigation | Moves towards the detected fire using sensor inputs. |
| 🚧 Obstacle Avoidance | Ultrasonic sensor detects nearby obstacles. |
| 💧 Automatic Extinguishing | Relay activates the water pump when required. |
| 🎯 Directional Water Spraying | Servo motor adjusts the nozzle direction. |
| 🛑 Automatic Pump Stop | Pump stops when the flame sensors no longer detect fire. |
| 📡 Wi-Fi Control | ESP32 enables remote manual operation. |
| 🔄 Dual Operating Modes | Supports autonomous and manual control. |

## 🛠️ Hardware Requirements

| Component | Purpose |
|---|---|
| Arduino Uno | Main controller |
| ESP32 | Wi-Fi communication and remote control |
| Multiple Flame Sensors | Fire detection and direction identification |
| Ultrasonic Sensor | Obstacle detection |
| L298N Motor Driver | DC motor control |
| DC Motors | Robot movement |
| Relay Module | Water pump switching |
| Water Pump | Fire extinguishing |
| Servo Motor | Water-spray direction control |
| Robot Chassis | Mechanical structure |
| Power Supply | Powers the electronic and mechanical components |

## 💻 Software Requirements

- Arduino IDE
- Embedded C/C++
- Arduino Uno board support
- ESP32 board support
- Appropriate sensor and motor-control libraries, depending on the implementation

## 🏗️ System Architecture

FIREBUDDY consists of five major modules:

1. **Fire Detection Module:** Multiple flame sensors monitor the surroundings and provide readings to the Arduino Uno.
2. **Navigation Module:** The Arduino processes sensor readings and determines the approximate direction of the fire.
3. **Obstacle Avoidance Module:** The ultrasonic sensor measures distances and helps the robot avoid obstacles.
4. **Fire Extinguishing Module:** A relay-controlled water pump and servo motor perform the extinguishing operation.
5. **Wireless Communication Module:** ESP32 provides Wi-Fi-based remote manual control.

### System Workflow

```text
                 FIREBUDDY
                     |
          +----------+----------+
          |                     |
     Fire Detection       Obstacle Detection
          |                     |
    Multiple Flame         Ultrasonic
       Sensors               Sensor
          |                     |
          +----------+----------+
                     |
                 Arduino Uno
                     |
           Sensor Processing
                     |
             Fire Direction
              Identification
                     |
              Motor Driver
                (L298N)
                     |
                DC Motors
                     |
             Robot Navigation
                     |
            Fire Reaches Suitable
                  Position
                     |
               Relay Module
                     |
                Water Pump
                     |
              Servo Motor
                     |
              Water Spraying
                     |
            Continuous Flame
                Monitoring
                     |
              Fire Not Detected
                     |
                Pump OFF
```

**Wireless Control:**

```text
Mobile / Wi-Fi Interface
          |
         ESP32
          |
   Control Commands
          |
    Robot Movement
```

## 🔄 Working Principle

### 1. System Initialization
The Arduino Uno initializes the connected sensors, motor driver, relay and servo motor. The ESP32 establishes its wireless communication functionality.

### 2. Fire Detection
Multiple flame sensors continuously monitor the surrounding environment and detect the presence of flames.

### 3. Fire Direction Identification
The Arduino compares the readings from multiple flame sensors to estimate the approximate direction of the detected fire.

### 4. Autonomous Navigation
The robot moves towards the detected fire using DC motors controlled through the L298N motor driver.

### 5. Obstacle Avoidance
The ultrasonic sensor measures the distance to nearby objects. If an obstacle is detected within the programmed threshold, the robot executes its obstacle-avoidance logic.

### 6. Automatic Fire Extinguishing
When the robot reaches a suitable position, the Arduino activates the relay module, switching on the water pump.

### 7. Directional Water Spraying
The servo motor adjusts the nozzle direction to direct water towards the detected fire.

### 8. Automatic Pump Deactivation
The flame sensors continue monitoring the fire. When the system detects that the fire is no longer present, the Arduino switches off the water pump.

## 🎮 Operating Modes

### 1. Autonomous Mode

In autonomous mode, the robot performs its programmed operations automatically:

- Detects flames.
- Identifies the approximate fire direction.
- Navigates towards the fire.
- Avoids obstacles.
- Activates the water pump.
- Adjusts the water-spray direction.
- Stops the pump when no flame is detected.

### 2. Wi-Fi-Based Manual Mode

In manual mode, the robot can be remotely controlled through the Wi-Fi functionality provided by ESP32.

The operator can send movement commands through the implemented control interface, allowing remote operation when autonomous navigation is unsuitable.

## 🧪 Testing and Evaluation

The prototype can be evaluated using the following test cases:

| Test | Expected Result |
|---|---|
| Flame Detection | Detect flames using multiple sensors. |
| Direction Identification | Estimate the direction of the flame. |
| Obstacle Detection | Identify nearby obstacles. |
| Motor Control | Execute programmed movements. |
| Autonomous Navigation | Move towards the detected fire. |
| Obstacle Avoidance | Avoid detected obstacles. |
| Water Pump Activation | Start water delivery. |
| Servo Control | Adjust water-spray direction. |
| Automatic Pump Stop | Stop the pump when no flame is detected. |
| Wi-Fi Control | Respond to remote movement commands. |

Performance metrics such as detection accuracy, response time and obstacle-avoidance success rate should be established through actual experimental testing.

## 📊 Performance Metrics

The following metrics can be used to evaluate the system:

**Fire Detection Accuracy**

```text
(Successful Detection Trials / Total Trials) × 100
```

**Fire Response Time**

Time taken between initial fire detection and activation of the extinguishing mechanism.

**Response Time Reduction**

```text
((Baseline Response Time - Robot Response Time)
 / Baseline Response Time) × 100
```

**Obstacle Avoidance Success Rate**

```text
(Successful Avoidance Trials / Total Trials) × 100
```

## 🚀 Future Enhancements

The project can be extended with additional technologies:

- **AI-Based Fire Detection:** Integrate machine learning and computer vision for improved fire classification.
- **Thermal Imaging:** Use thermal cameras to identify heat sources.
- **Smoke and Gas Detection:** Integrate additional sensors for environmental monitoring.
- **Real-Time Monitoring:** Develop a web or mobile dashboard to monitor robot status and sensor readings.
- **Advanced Navigation:** Implement improved path-planning and obstacle-avoidance algorithms.
- **Enhanced Communication:** Introduce additional communication technologies for improved remote operation.
- **Advanced Fire Extinguishing:** Select extinguishing mechanisms appropriate for different fire classifications.

## ⚠️ Limitations and Safety Considerations

- Flame sensors have limited detection ranges and may be affected by environmental lighting.
- Ultrasonic sensors cannot guarantee collision-free navigation in every environment.
- Wi-Fi manual control depends on network connectivity.
- The current prototype does not include a camera or computer-vision-based fire classification.
- Flame sensor readings alone cannot independently certify that a fire is completely extinguished.
- Water is not suitable for every fire class. Never use this prototype to spray water on energized electrical equipment or flammable-liquid fires.

**FIREBUDDY is an academic working prototype, not a certified firefighting device. It must not replace professional firefighting equipment or emergency-response procedures.**

## 📚 Technologies Used

- Arduino Uno
- ESP32
- Embedded C/C++
- Internet of Things (IoT)
- Flame Sensors
- Ultrasonic Sensors
- Motor Control Systems
- Robotics
- Servo Motor Control
- Wireless Communication

## 👩‍💻 Project Information

| Category | Details |
|---|---|
| Project Name | FIREBUDDY |
| Project Title | An Automatic Fire Extinguishing Robot |
| Project Type | Final-Year Academic Project |
| Project Status | Physical Working Prototype |
| Domain | Robotics, IoT and Embedded Systems |
| Main Controller | Arduino Uno |
| Wireless Module | ESP32 |
| Operating Modes | Autonomous and Wi-Fi-Based Manual Control |

## 🤝 Contributions

Contributions, suggestions and improvements are welcome.

If you would like to improve this project, feel free to fork the repository and submit a pull request.

## 📄 License

This project is intended for academic and educational purposes. Add an appropriate open-source license if you decide to publish the source code for reuse.

---

**FIREBUDDY – Bringing Robotics and IoT Together for Smarter Fire Response.** 🔥
