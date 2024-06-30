
# Combinatorics

# Conception 



# Combinatorics  Framework

Combinatorics is an industrial framework composed of individual electronic modules (power modules, motor control modules,
sensors, etc.). Like building with Lego blocks, these modules can be assembled to create diverse projects across various
industrial sectors, embodying the essence of convergence.

**Combinatorics** is an industrial framework consisting of various types of elements:

- Basic electronic modules with a standard interface
- FPGA-based hubs that bring the modules together into a unified system
- Standard connectors
- Standard motors
- Sensors

With these elements, you can create various robotic systems, much like assembling Lego blocks, from completely different
industrial sectors. The more basic modules you have, the more equipment variations you can create.


#### Robots

In popular perception, industrial robots are often associated with robotic arms widely used in car manufacturing.
However, in practice, these robots are quite versatile, albeit with a limited application range. Their precision under
high load conditions is inferior to specialized machines.

In a broader sense, an industrial robot is a device that combines motion actuators and various position sensors, which
can take different forms, such as linear motors or solenoids. The simplest industrial robot might consist of a solenoid
coil and a microcontroller that controls it.

Specialized devices such as 3D printers, CNC milling, and turning machines stand apart. Each of these types has unique
solutions, like specialized motherboards for 3D printers or controllers for CNC machines.

In modern times, such specialization is becoming less relevant. Virtually identical electronic modules are used in
various types of equipment, with the main difference lying in the software. Developing specialized hardware solutions
for different types of equipment is economically inefficient compared to using universal modules with specialized
software.

Combinatorics is an innovative framework that allows for the creation of diverse equipment, tightly integrated with
computer systems, on a common elemental base, opening new horizons in industrial automation.


# Conception

A modern industrial equipment control system should not resemble an electric control panel with a tangle of wires. It
should appear more like a server rack containing state-of-the-art equipment. Inside such a panel, there should be a
combination of high electrical power hardware and high-performance data processing systems.

The reason for the abundance of wires within control panels with machine controllers is the use of outdated standards
and data transmission protocols.

The Combinatorics framework introduces a new standard for expansion boards based on the M.2
interface, allowing the elimination of numerous wires and equipping equipment with high-speed data communication lines.


### Combinatorics name

# Architecture

### Combinatorics Framework Components

- **Electronics** - electronic modules
  - Hubs - modules that combine other modules
  - Modules - electronic modules
  - SmartModules - smart modules
- **Connections** - connectors for module interconnections
  - Power - power connectors
  - Data - data connectors
  - Cables - cables for connections
- **Sensors** - sensors of various types
- **Drivers** - various drivers
- **Mechanics** - mechanical elements
  - Profiles - aluminum profiles
  - Fasteners - fastening elements
  - Cases - enclosures where modules are placed
  - Linear - linear guides


### Hub

The Hub module is a board that contains multiple M2E connectors along one or more edges (using M.2 connectors
labeled B). The board contains an FPGA for integrating signals from connected modules. Each M2E connector is connected
to a separate FPGA port, allowing data transmission voltages ranging from 0.6V to 3.3V. Hub boards can be generated
using the Combinatorics platform service.


### Modules

M2E modules can include multiple connectors for connecting computational cores based on FPGA SOSC or ARM, which require
more data exchange lines. Data processing cores connect to these connectors, and multiple data exchange interfaces can
be attached to the same connectors. The data transmission interface of M2E modules includes 8 differential pairs and 8
regular data transmission lines.


#### Inverted Module Connectors

Unlike standard M.2 connectors, module boards use female connectors (Mama). This is done for two reasons: modules can be
manufactured based on boards of varying thickness, and the receiving board can be made on an aluminum substrate. M.2
requires a thickness of 0.8 and a double-sided board based on fiberglass; hence, male connectors are located on the Hub
board.


### Smart Modules

Smart modules are a key component of the Combinatorics architecture. Each module features an embedded microcontroller
and two UIC connectors, allowing them to be linked in chains. One connector is used for data input, while the other
connects to the next smart module.

Regardless of the cost of the sensor included in the smart module, even if it's as low as one cent, the module is always
equipped with a microcontroller and an industrial UIC connector. Despite the higher cost, this approach offers several
benefits that justify the expense, such as reduced installation, maintenance, and troubleshooting time for personnel.


# Microchips

Solenopsys community is on a mission to design our own microchips. Our aim is to develop chips that are tailor-made for
the demands of modern industrial automation.


**Why is Creating Custom Chips Important?**
Modern chips offer complex functionalities beyond the reach of traditional circuit board designs. This is particularly crucial for developing high-frequency (RF) devices, where the physical constraints and electrical properties of standard circuit board elements are unsuitable.

**Outdated Industrial Protocols:**
Current industrial data exchange protocols are severely outdated, operating at a throughput a thousand times less efficient than what modern technology can achieve.

**Historical Overview and Bandwidth Capacities**

- **I2C:** Created in 1982, with a bandwidth of 400kbps.
- **UART:** In use since 1962, speeds up to 100kbs.
- **SPI:** Introduced in 1979, capable of speeds up to 10Mbps.
- **CAN:** Developed in 1983, with speeds reaching up to 1Mbps.

To create new data transmission transmitters at a low cost, custom microchips are necessary, as small-scale FPGA units already cost an average of 3-5 dollars each.

Moreover, the scope of creation extends beyond integrated circuits. Most modern transistors, like GAN and FET, are manufactured using standard lithographic processes. Developing custom microchips is thus a major leap towards enhancing the functionality and cost-effectiveness of various electronic devices.


### Why is This Feasible for the Solenopsys Community?

Thanks to OpenRoad, an OpenSource Integrated Development Environment (IDE) for chip development, the Solenopsys community is well-equipped to make significant advancements in chip design. We aim to integrate OpenRoad with Detonation systems, offering our community members a powerful yet user-friendly tool for creating their own chips.

Additionally, there's an active chip manufacturing program at the SkyWater facilities, supported by Google. This initiative enables any interested person to produce their own chip.


# Measurement

Scientific research is an essential part of the innovation process and is necessary for the creation of new
technologies. New products with improved characteristics often go beyond the current technological boundaries.
Therefore, technological startups need to conduct scientific research and development.

To assess the results of development, any tests or scientific research require measurements. In modern conditions,
experiments and measurements can and should be fully automated.

The Combinatorics framework provides modules for the automation of measurements and experiments.


### Current State of Measurement Equipment

In the realm of scientific research and the development of new equipment, a variety of measurement instruments are
employed. This includes devices like oscilloscopes, spectrum analyzers, signal generators, multimeters, etc.

Professional-grade measurement equipment can be prohibitively expensive. For instance, an oscilloscope with a bandwidth
of 40Gs per second can cost around $100,000. A similar pricing structure applies to spectrum analyzers.

Upon dissecting such an oscilloscope, it becomes apparent that its core indispensable components are the chip and the
board responsible for signal capture and digital conversion. A significant portion of the oscilloscope's cost can be
attributed to its software and data processing system.


### Existing Issues

- High cost of equipment
- Complex integration of devices into a single system (usually either impossible or very expensive)
- Each device has its own screen and interface
- Difficulties in processing data from different devices


### Strategy for Increasing the Accessibility

Our strategy revolves around designing relatively simple and cost-effective front-end modules for signal capture and its
digital conversion, leveraging our OpenSource chip technology. 

This approach is complemented by the use of OpenSource
software for data processing on existing computer accelerators like GPUs. 

Consequently, the most expensive component
becomes the computer chip for signal capture, while the rest of the system relies on software and standard computer
hardware.

### Advantages of Using Combinatorics

- Low cost of equipment
- Easy integration of devices into a single system
- All devices have a single interface
- Easy processing of data from different devices in Detonation


#### Front Modules

Front modules are lightweight measurement modules whose primary function is to capture the signal under study, convert
it into a digital form, and transmit the data for processing to a cluster.


#### Detailed Steps for Implementation:

1. Develop OpenSource chips for signal capture and digital conversion.
2. Design minimalistic front-end modules for efficient signal capture and conversion to digital form.
3. Create Open Source software modules based on Detonation for data processing on existing computing technologies.
4. Develop Open Source modules for visualizing signals on various devices based on Converged.


# Power



### Parts

For safety reasons, the power supply is divided into 2 parts:

- **Low Voltage:** from 0 to 50 volts
    - Safe for human life and allows transmitting power up to 1 kilowatt per electronic module.

- **High Voltage:** from 50 to 1000 volts
    - Not safe for human life, but allows transmitting power up to 100 kilowatts per hub.


### Low Voltage

#### 48 Volts

At 48 volts, there are several important advantages:

- High power, up to a kilowatt, can be transmitted to a single electronic module, and it remains safe for humans.
- Most connectors are rated for voltages not lower than 50 volts, which aligns with this voltage.
- There is a wide variety of affordable voltage converters with input voltages up to 60 volts.

#### 12 Volts
Used for internal power supply; this voltage is primarily required for controlling MOSFETs.

#### 3.3 Volts
Used to power various microchips, microcontrollers, and FPGA, CPU, GPU.



### High Voltage 

#### 400 Volts

The choice of 400 volts is justified by the following factors:

- Availability of inexpensive switches, including most GANFET SICFET, with a nominal voltage of 650 volts. This ensures reliable electrical strength for these switches.
- There are many electrolytic capacitors on the market at a reasonable price with voltages ranging from 450 to 550 volts.
- The ability to control most powerful 3-phase motors, servo drives, and spindles without the need for transformer inverters.

#### 800 Volts

Using 800 volts when supplying high-power devices such as 3-phase motors, welding equipment, electrolysis equipment, induction furnaces, and powerful microwave heaters has the following advantages:

- Reduces energy losses during transmission and conversion, leading to cost savings on energy transmission cables.
- Enables the use of power factor correction modules (PFMs) based on SiC (silicon carbide) transistors in virtually any 3-phase power grid in the world, with voltages ranging from 380 to 600 volts. These PFMs have high efficiency and minimal losses.
- Resonant voltage inverters with an 800V input voltage also have very low losses, typically 1-2%.


### Grid System

Grid is a power system based on spatial separation of buses.

The system allows the use of both printed circuit boards and powerful buses for
powering modules. This approach enables delivering high power and currents up to
thousands of amperes.


# Examples

#### Examples of Front Modules

- Oscilloscope
- Logic Analyzer
- Digital Signal Generator
- Signal Generator
- Spectrum Analyzer
- Multimeter



### Examples of Smart Modules
- Motors
    - Stepper motor with integrated driver.
    - Closed-loop stepper motor with integrated driver and built-in angle sensor.
    - Closed-loop servo motor with integrated driver and built-in angle sensor.
- Sensors
    - End sensesor with integrated microcontroller.
    - Temperature sensor with integrated microcontroller.
    - Hall sensor with integrated microcontroller.
    - Angle sensor with integrated microcontroller.
- Electronic Modules
    - Extruder controller - heater, fans, sensor.
    - Solid-state relay with integrated microcontroller and voltage presence sensor.


### Examples of exists Open Source chips

- **OpenFPGA:** An open-source FPGA platform.
- **Rocket-Chip:** A RISC-V processor implemented in Chisel.
- **OpenRiscV:** An open-source processor core.
- **ZipCPU:** A compact and efficient RISC processor.
- **OpenRAM:** Advanced technology for database processing.


# Connectors

### Why are industrial connectors so important?

When creating complex industrial equipment that includes dozens or hundreds of electronic modules, the system's
reliability is determined by the modules' reliability by 50%, and the other 50% depends on the connectors. For this
reason, the cost of connectors can reach up to $1000 each.


### How much do modern industrial connectors cost?

Connectors are a highly technological area in industry. The reliability of complex systems depends directly on the
reliability of the connectors that link the system's modules.

Modern industrial connectors can cost tens of dollars each and are not always technologically advanced enough to create
cables using them on automated assembly lines. Cable assembly is often done manually.

The cost of an industrial connector is approximately $20. In comparison, the cost of a display port connector is about
$2, while the quality and technological level are almost the same.


### Why do we need to solve the problem of industrial connectors?

Combinatorics is a framework for creating digital factories, and any digital factory includes thousands of
interconnected modules. Therefore, without solving the issue of standardized connectors, it is challenging to achieve a
high-quality implementation of digital factory technology.

To create a scalable and reliable infrastructure, we need universal connectors with a very low cost, as otherwise, the
cost of these connectors will significantly impact the overall system cost.

As an example, the cost of simple devices like temperature sensors or limit switches can be $0.1, so the connector's
cost should not exceed the device's cost. With connectors priced at $20, it may seem like an unsolvable problem, but
there are excellent opportunities in the market to address this issue.

Various computer connectors that are widely produced and available at a minimal cost are now prevalent.


### Why can we create the required connector?

Developing several types of connectors for a large community and making them an open standard is not a significant
challenge. These connectors can be manufactured in quantities of 10,000 pieces.



### Start Strategy

Considering the high costs of creating connectors from scratch, our approach is to utilize existing connectors and adapt them to industrial requirements.

#### Examples
- USB-C - UIC for smart modules
- M.2 - M2E for hub modules
- Mini-fit - UPW for powerful connections


### Data connectors

#### What are the connector requirements?
Small size, high retention reliability, shielded housing for shielded cables, current transmission of several amperes
per pin, Voltage Rating, ease of manufacturing in industrial conditions, the ability to assemble in home conditions, and
low cost, around $0.1 per connector.

#### Low Speed
This shielded connector supports data transfer speeds of up to 1 gigabit per second. It is designed for most devices and
sensors, and it should be a straightforward connector with minimal pins.

#### High Speed
It supports data transfer speeds of up to 40 gigabits per second, enabling high-speed data exchange between FPGAs via
SerDes, video streaming through MIPI interfaces, and module connections using 10G Ethernet.


### Power Connectors

For robust connectors, we will utilize computer power connectors commonly used for motherboard power supply. They have a
high permissible current and voltage and are cost-effective.

Another significant advantage of computer connectors is the redundancy of contacts. This allows for a substantial
increase in connection reliability through redundancy.

For high-power connections, we will employ Mini-fit connectors capable of transmitting up to 20 amperes with a maximum
voltage of 600 Volts AC (RMS) or 600 Volts DC.


# Advantages

### Device Management

We move away from interactive screens built into equipment and any device-specific control elements. All types of equipment are managed through the unified UI interface of Converged.

Equipment may have small standard screens solely for displaying the current configuration and status of the device. Each piece of equipment should only have a power-on button.

### Control Options:
- Directly control the device's controller by connecting to it via a websocket over WiFi.
- Manage hundreds of devices operating in a Detonation cluster by connecting to the cluster via WiFi or remotely.
- Control multiple clusters of devices scattered around the world through the decentralized Solenopsys platform, connecting to it over the internet.

 



### Advantages of Smart Modules

**Ease of Installation and Maintenance**: All connectors in the system are identical and have a standardized interface,
simplifying device connection to just plugging in a cord, with the rest managed by software.

**Transactional Data Transfer Interface**: Ensures certainty in device communication. There are only two outcomes:
successful or unsuccessful data transfer. Analog interfaces, prone to various interferences, can lead to rare but
damaging failures. Such faults are hard to diagnose.

**Continuous Device Monitoring**: Prevents a range of equipment malfunctions during operation. For example, a mechanical
limit switch with a broken wire will only be detected during operation. With smart modules, such issues are diagnosed
before the device starts working.

**Serial Module Connection**: Significantly reduces the number of wires needed for device connections.

**Reprogrammable Smart Modules**: Can change their operational algorithms through firmware updates.

