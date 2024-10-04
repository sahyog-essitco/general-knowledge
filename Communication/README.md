# Communication Protocols

This folder contains documentation for various communication protocols used in embedded systems and microcontrollers. The primary protocols covered here are **I2C**, **UART**, and **SPI**, along with some additional methods of communication.

## Table of Contents

- [Overview](#overview)
- [Protocols](#protocols)
  - [I2C](#i2c)
  - [UART](#uart)
  - [SPI](#spi)
  - [Other Methods](#other-methods)
- [Comparison](#comparison)
  - [Similarities](#similarities)
  - [Differences](#differences)
- [Use Cases](#use-cases)

---

## Overview

Communication protocols are essential for enabling data exchange between microcontrollers and peripherals like sensors, displays, or memory devices. Each protocol has its specific use cases, advantages, and limitations. The three most commonly used protocols are **I2C**, **UART**, and **SPI**. These protocols differ in terms of wiring, speed, data transfer mechanisms, and application.

---

## Protocols

### I2C

**I2C** (Inter-Integrated Circuit) is a synchronous, multi-master, multi-slave, two-wire protocol commonly used for connecting low-speed peripherals such as sensors, displays, and EEPROMs.

- **Wiring:** Two lines (SDA - data, SCL - clock)
- **Addressing:** Supports multiple devices using unique addresses
- **Speed:** Typically 100 kbps, 400 kbps (Fast Mode), or 3.4 Mbps (High-Speed Mode)
- **Master-Slave:** One master can control multiple slaves
- **Applications:** Sensors, RTCs, LCD displays, EEPROM

For more information, see the [I2C documentation](I2C/README.md).

---

### UART

**UART** (Universal Asynchronous Receiver/Transmitter) is a simple, point-to-point asynchronous communication protocol. It is widely used for serial communication between microcontrollers and external devices.

- **Wiring:** Two lines (TX - transmit, RX - receive)
- **Full-Duplex:** Simultaneous two-way communication
- **Speed:** Typically up to 115 kbps but can go higher
- **Master-Slave:** No master-slave concept; it's typically point-to-point
- **Applications:** Debugging, GPS modules, Bluetooth modules, serial interfaces

For more information, see the [UART documentation](UART/README.md).

---

### SPI

**SPI** (Serial Peripheral Interface) is a synchronous, full-duplex communication protocol used for high-speed data transfer. It is typically employed in applications that require fast communication, such as memory cards and displays.

- **Wiring:** Four lines (MOSI - Master Out Slave In, MISO - Master In Slave Out, SCK - Clock, SS - Slave Select)
- **Full-Duplex:** Allows for simultaneous communication in both directions
- **Speed:** Can go up to 10 Mbps or more
- **Master-Slave:** One master can communicate with multiple slaves using separate chip-select lines
- **Applications:** SD cards, flash memory, LCD displays, audio codecs

For more information, see the [SPI documentation](SPI/README.md).

---

### Other Methods

- **1-Wire:** A low-speed, one-wire communication protocol typically used for temperature sensors (e.g., DS18B20).
- **CAN (Controller Area Network):** Used primarily in automotive and industrial applications for robust, long-distance communication between devices.
- **USB (Universal Serial Bus):** Common for connecting peripherals such as keyboards, mice, and storage devices to microcontrollers or computers.

---

## Comparison

### Similarities

| Feature              | I2C                        | UART                    | SPI                     |
|----------------------|----------------------------|--------------------------|--------------------------|
| **Serial Communication** | Yes                        | Yes                      | Yes                      |
| **Wiring**            | Shared bus (SDA, SCL)       | Point-to-point (TX, RX)   | Dedicated (MOSI, MISO, SCK, SS) |
| **Speed**             | Moderate (up to 3.4 Mbps)   | Slow to moderate (up to 115 kbps) | High-speed (up to 10 Mbps or more) |
| **Data Transfer**      | Synchronous                | Asynchronous             | Synchronous               |
| **Multiple Devices**  | Yes (multi-master, multi-slave) | No                       | Yes (master, multi-slave) |

### Differences

| Feature                | **I2C**                         | **UART**                         | **SPI**                          |
|------------------------|----------------------------------|----------------------------------|-----------------------------------|
| **Wiring**             | 2 wires (SDA, SCL)               | 2 wires (TX, RX)                 | 4 wires (MOSI, MISO, SCK, SS)    |
| **Clock Signal**        | Yes (synchronous)                | No (asynchronous)                | Yes (synchronous)                |
| **Full-duplex**        | No                               | Yes                              | Yes                              |
| **Data Speed**         | Moderate                         | Lower                            | High                             |
| **Device Support**     | Multiple devices (via addressing) | Point-to-point                   | Multiple devices (via chip select)|
| **Complexity**         | Medium                           | Simple                           | Medium                           |

---

## Use Cases

- **I2C:**
  - Connecting multiple low-speed devices like sensors and displays over short distances.
  - Example: Reading data from a temperature sensor (e.g., LM75) and displaying it on an OLED screen.
  
- **UART:**
  - Debugging embedded systems or interfacing with modules that support serial communication.
  - Example: Sending GPS data from a GPS module (e.g., NEO-6M) to a microcontroller for position tracking.
  
- **SPI:**
  - High-speed communication with peripherals like SD cards, flash memory, or displays.
  - Example: Writing data to an SD card in a data logger system or interfacing with a TFT display for graphics.

- **1-Wire:**
  - Monitoring temperature with a single-wire sensor, often used in industrial or consumer electronics applications.
  - Example: Reading temperature from a DS18B20 sensor in home automation systems.

- **CAN:**
  - Vehicle communication systems where robustness and reliability are crucial.
  - Example: Exchanging data between different ECUs in an automotive network (e.g., engine control and transmission control units).
