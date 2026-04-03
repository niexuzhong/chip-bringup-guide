# Why This Guide

[中文版本](../zh/01-为什么要写这个指南.md)

## 1. Background

In embedded systems development, bringing up a new chip (MCU/SoC)
is a fundamental yet challenging task.

This process typically includes:

- Boot code development
- RTOS porting
- Peripheral driver development
- Debugging and validation
- Unit testing and optimization

Although these tasks are repeated across projects, the knowledge is
often fragmented and lacks systematic documentation.

This guide aims to organize this process and provide a practical reference.

---

## 2. Traditional RTOS Development Model

In traditional embedded systems using RTOS such as FreeRTOS or RT-Thread,
a HAL-based architecture is commonly used:
Application
│
RTOS API
│
HAL
│
Driver
│
Hardware

Key characteristics:

- Hardware is abstracted through a HAL layer
- Applications interact with hardware via HAL
- Code reuse across different chips is possible

This model is widely accepted and familiar to many engineers.

---

## 3. How Zephyr is Different

The design philosophy of Zephyr RTOS is significantly different.

Zephyr does not provide a unified HAL layer. Instead, it relies on:

- A device model-based driver framework
- Heavy use of compile-time configuration
- Strong separation of hardware and software

This means:

- No unified HAL interface
- Different driver development approach
- Higher initial learning curve

---

## 4. Hardware–Software Separation in Zephyr

Zephyr achieves abstraction in a different way—through build-time configuration.

When using the traditional approach, code reuse can become problematic.
It is often difficult to directly reuse existing code when developing
for a new board.

This is similar to the early days of Linux, where different code had to
be written for each hardware platform. To address this issue, Linux
introduced DeviceTree (DTS) as a solution.

Similarly, embedded systems can adopt the same approach by representing
hardware structures in a tree format. This makes the hierarchical
relationships between components clear and easier to understand.

With this method, the porting structure becomes much clearer. DTS is
used to describe hardware resources such as register addresses and
configurable parameters. Differences between hardware platforms are
handled through Kconfig and CMakeLists.txt.

Kconfig defines a set of configuration options (macros), which are used
to control which source files are included in the build system.

The following sections will introduce these three systems in detail:

### 4.1 Kconfig

Used for feature configuration:
CONFIG_SERIAL=y
CONFIG_I2C=y
CONFIG_GPIO=y

---

### 4.2 DeviceTree

Used for hardware description:
uart0: serial@40013800 {
compatible = "vendor,uart";
reg = <0x40013800 0x400>;
};


---

### 4.3 CMake

Responsible for:

- Driver compilation
- Module selection
- Dependency management

---

### 4.4 Summary

Zephyr achieves hardware–software separation through the combination of
Kconfig, DeviceTree, and CMake, with most configuration resolved at build time.

---

## 5. Why Choose Zephyr

Despite the learning curve, Zephyr provides strong advantages:

### 5.1 Open Source Ecosystem

Zephyr is hosted by the Linux Foundation with active community support.

---

### 5.2 Clean Architecture

- Unified device model
- Modular driver framework
- Structured configuration system

---

### 5.3 Scalability

Suitable for:

- MCU
- MPU
- IoT devices
- Safety-critical systems

---

### 5.4 Engineering Quality

Zephyr includes:

- CI support
- Testing frameworks
- Static analysis tools

---

## 6. Goal of This Guide

This guide aims to cover:

- Chip bring-up process
- RTOS porting
- Driver development
- Debugging
- Unit testing

Using AT32F425 as an example.

---

## 7. Target Audience

- Embedded engineers
- Chip vendors
- RTOS developers

---

## 8. Status

This project is still a work in progress. More content will be added over time.
