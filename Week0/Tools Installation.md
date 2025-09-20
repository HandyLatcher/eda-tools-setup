
## **🛠️ Week 0 – Tool Installation & Setup**
<div align="center">

![Program](https://img.shields.io/badge/Program-VSD%20SoC%20Tapeout-orange?style=for-the-badge) [![Week 0](https://img.shields.io/badge/Week-0-blue?style=for-the-badge)](#) [![Tools](https://img.shields.io/badge/Tools-Setup%20%26%20Installation-success?style=for-the-badge)](#)  

</div>

## **1. Introduction** 📖

In **Week 0** of the **VLSI System Design (VSD) Program**, the focus is on preparing the **development environment** for the upcoming digital VLSI and SoC design tasks.

This includes:

* Installing and configuring **open-source EDA tools** for synthesis, simulation, and layout.
* Setting up a **virtual machine (VM)** to provide a stable workspace.
* Ensuring all tools are tested and verified before starting design experiments.

The program aims to provide hands-on experience in the **RTL → GDSII design flow**, using open-source tools to understand the complete VLSI process.

---

## **2. System Requirements** 💻

To run the required tools smoothly, the following **system configuration** is recommended:

| Component            | Specification    |
| -------------------- | ---------------- |
| **Operating System** | Ubuntu 20.04+    |
| **RAM**              | 6 GB             |
| **Storage**          | 50 GB HDD        |
| **vCPU**             | 4                |

Additionally, the tools will be installed and executed inside a **Virtual Machine (VM)** using **Oracle VirtualBox**.

---

## 3. Tools for Week0 Setup⚙️

This week focuses on installing the essential open-source tools for VLSI design. The tools include **Yosys** for RTL synthesis, **Icarus Verilog** for simulation, **GTKWave** for waveform analysis, **Ngspice** for circuit simulation, and **Magic VLSI** for layout design.

---

### **1. Yosys – RTL Synthesis Tool** 🟦

**Purpose:**
Yosys is an **open-source RTL synthesis tool** used to convert Verilog designs into gate-level netlists. It is essential for **logic synthesis, verification, and preparing designs for further VLSI implementation**.

**Installation Steps:**

```bash
$ sudo apt-get update
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make (If make is not installed please install it)
$ sudo apt-get install build-essential clang bison flex \
 libreadline-dev gawk tcl-dev libffi-dev git \
 graphviz xdot pkg-config python3 libboost-system-dev \
 libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make
$ sudo make install 
```
<div align="center">
  <img width="600" alt="Yosys Installation Screenshot" src="https://github.com/user-attachments/assets/1821d3df-59b3-41f0-a0ea-f0c45a76db2b" />
</div>

<div align="center">
  <b>🟢Yosys was successfully installed</b>
</div>

---

### **2. Icarus Verilog – Simulation Tool** 🟩

**Purpose:**
Icarus Verilog (iverilog) is an **open-source Verilog simulator**. It is used to **compile and simulate Verilog RTL designs**, allowing verification of logic correctness before synthesis and hardware implementation.

**Installation Steps:**

```bash
# Update system packages
sudo apt-get update

# Install Icarus Verilog
sudo apt-get install iverilog
```

**Verification:**

```bash
iverilog -v
```

> This command prints the installed Icarus Verilog version, confirming that the tool is successfully installed.

---

<div align="center">
  <img width="600" alt="Icarus Verilog Installation Screenshot" src="https://github.com/user-attachments/assets/0e470569-d788-42b8-aabd-e272284ca15a" />
</div>
<div align="center">
  <b>🟢Icarus Verilog was successfully installed</b>
</div>

---
### **3. Gtkwave** 
**Purpose:**
GTKWave: Look At Your Waveforms, Openly | Software ReviewGTKWave's purpose is to serve as a waveform viewer
**Installation Steps:**
```bash
$ sudo apt update
$ sudo apt install gtkwave
```
---
<p align="center">
  <img src="https://github.com/user-attachments/assets/18cdb725-28d1-4150-ac15-69bfeedbf56f" width="800" alt="GTKWave Screenshot">
</p>
<div align="center">
  <b>🟢GTKWave was successfully installed</b>
</div>

---

### **4. Ngspice – Circuit Simulator**
**Purpose:**
 It acts as a free, open-source electronic circuit simulator
**Installation Steps:**
```bash
$ tar -zxvf ngspice-37.tar.gz
$ cd ngspice-37
$ mkdir release
$ cd release
$ ../configure --with-x --with-readline=yes --disable-debug
$ make
$ sudo make install
```
<p align="center">
  <img src="https://github.com/user-attachments/assets/536d2e06-ce20-4968-84dc-0dc557b54023" width="500" alt="Ngspice Installation Screenshot">
  <br>
  <b🟢Ngspice was successfully installed</b>
</p>
 
