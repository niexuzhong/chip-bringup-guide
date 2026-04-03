# Chip Bring-up Guide

A practical, engineering-oriented guide for developing software support
for a new MCU/SoC platform.

This project documents real-world experience in:

- Chip bring-up
- RTOS porting
- Driver development
- Debugging
- Unit testing

---

## ✨ Features

- Focus on **practical engineering workflows**
- Covers **full lifecycle of chip development**
- Based on real project experience
- Bilingual documentation (中文 / English)

---

## 📚 Documentation

### 中文文档

- [01 为什么要写这个指南](docs/zh/01-为什么要写这个指南.md)
- [02 芯片开发整体流程](docs/zh/02-芯片开发整体流程.md)
- [05 驱动开发](docs/zh/05-驱动开发.md)

---

### English Documentation

- [01 Why This Guide](docs/en/01-why-this-guide.md)
- [02 Chip Development Workflow](docs/en/02-chip-development-workflow.md)
- [05 Driver Development](docs/en/05-driver-development.md)

---

## 🧠 Key Topics

This guide focuses on the following core ideas:

- Difference between traditional HAL and modern RTOS design
- How Zephyr separates hardware and software
- Role of:
  - Kconfig
  - DeviceTree (DTS)
  - CMake
- Scalable driver architecture design

---

## ⚙️ Example Platform

Current example platform used in this guide:

- AT32F425

---

## 🚧 Status

This project is a **work in progress**.

More content will be added, including:

- Boot process
- Debugging techniques
- Unit testing
- Real case studies

---

## 🤝 Contributing

Contributions, issues, and discussions are welcome!

---

## 📄 License

MIT License
