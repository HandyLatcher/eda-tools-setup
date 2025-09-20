## 🏗️ OpenLane – Introduction

🔹 **What is OpenLane?**
OpenLane is an **open-source RTL-to-GDSII flow** built on top of the \[OpenROAD project]. It automates the entire **ASIC (chip) design flow**, starting from RTL (Register Transfer Level) description of your circuit and ending with a final GDSII layout ready for fabrication.

🔹 **Where is it used?**

* 📐 Academic research and VLSI education
* 🏭 Industry prototyping for ASIC design
* 🧑‍💻 Open-source chip design projects (e.g., Google + Efabless shuttle runs)
* 🎓 Training programs (like **VSD** workshops and RTL-to-GDS journeys)

🔹 **Why do we need it?**

* 🚀 Provides a **fully automated pipeline** (no need to manually run each tool)
* 🌍 Uses **open-source PDKs** (like SkyWater 130nm) so anyone can design chips without expensive licenses
* 🔗 Integrates many tools (Yosys, OpenROAD, Magic, Netgen, etc.) into one smooth flow
* 🛠️ Helps students and engineers learn the **entire chip design process** in a practical way

🔹 **Key Features**

* ✅ RTL → GDSII in one flow
* ✅ Supports multiple PDKs (Sky130, GF180, etc.)
* ✅ Built on Docker → easy to install anywhere
* ✅ Verified through test designs

---

# 🏗️ OpenLane Installation Guide

### 🔹 Step 1: Update and upgrade your system

Keep your system packages up to date.

```bash
sudo apt-get update
sudo apt-get upgrade -y
```

---

### 🔹 Step 2: Install essential build tools and Python

These are required for compiling tools and managing environments.

```bash
sudo apt install -y build-essential python3 python3-venv python3-pip make git
```

---

### 🔹 Step 3: Install Docker dependencies

Install required packages to allow apt to use repositories over HTTPS.

```bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

---

### 🔹 Step 4: Add Docker’s official GPG key

This secures Docker packages with verified signatures.

```bash
sudo mkdir -p /usr/share/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

---

### 🔹 Step 5: Set up the Docker repository

Add Docker’s official repository to apt sources.

```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

### 🔹 Step 6: Install Docker Engine

Now install Docker itself.

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

---

### 🔹 Step 7: Verify Docker installation

Run the hello-world container to test Docker.

```bash
sudo docker run hello-world
```

---

### 🔹 Step 8: Run Docker without sudo (optional, recommended)

Add your user to the Docker group so you don’t need sudo every time.

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
sudo reboot
```

---

### 🔹 Step 9: Verify tools after reboot

Check that Docker and other tools are installed correctly.

```bash
docker run hello-world
git --version
docker --version
python3 --version
python3 -m pip --version
make --version
python3 -m venv -h
```

---

### 🔹 Step 🔟 Install OpenLane (PDKs + Tools)

Clone the OpenLane repository and build it.

```bash
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
```

---

✅ After this, OpenLane will be ready, and the `make test` step ensures that the flow + PDKs are installed and working.

---

<p align="center">
  <img src="https://github.com/user-attachments/assets/1278f1f1-1d9f-4d8d-8040-be690dac9b08" width="500" alt="Docker Installation Screenshot">
  <br>
  <b>🐳 Docker was successfully installed</b>
</p>

---
