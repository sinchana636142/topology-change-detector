# Topology Change Detector using Mininet and POX

## 📌 Overview

This project demonstrates how to detect and monitor topology changes in a Software Defined Network (SDN) using the Mininet emulator and the POX controller.
The system observes traffic and dynamically identifies changes in network structure such as link additions, removals, or host connectivity.

---

## ⚙️ Requirements

* Ubuntu (18.04/20.04 recommended)
* Python 3.6–3.9 (POX compatible)
* Mininet
* POX Controller

---

## 📁 Project Structure

```
project/
│── topo.py                # Custom Mininet topology
│── topo_detect.py         # Topology detection module
│── README.md              # Project documentation
```

---

## 🚀 How to Run

### 1. Start POX Controller

```
cd ~/pox
./pox.py forwarding.l2_learning topo_detect openflow.discovery
```

### 2. Run Mininet Topology

```
sudo mn --custom topo.py --topo mytopo --controller remote --mac
```

### 3. Test Connectivity

```
mininet> pingall
```

---

## 🔍 Features

* Detects topology changes in real-time
* Logs traffic between hosts
* Uses OpenFlow discovery for link detection
* Displays MAC-level communication

---

## 📊 Sample Output

```
INFO:topo_detect:Topology Detector Started
INFO:openflow.of_01:[00-00-00-00-00-01 2] connected
INFO:topo_detect:Traffic: h1 -> h2
```

---

## ⚠️ Notes

* If you see Python version warnings, install a supported version (3.6–3.9)
* Clean Mininet before running:

```
sudo mn -c
```

* Free controller port if needed:

```
sudo fuser -k 6633/tcp
```

---

## 📚 Concepts Used

* Software Defined Networking (SDN)
* OpenFlow Protocol
* Network Topology Discovery
* Packet Forwarding

---

## 👨‍💻 Author

Sinchana M
