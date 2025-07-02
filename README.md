# 📡 GTPDoor: Control-Plane C2 Simulation for Telecom Environments

**GTPDoor** is a lightweight simulation framework designed to emulate a control-plane backdoor (C2) operating over the **GPRS Tunneling Protocol Control plane (GTP-C, UDP/2123)** — inspired by adversarial techniques used by state-sponsored threat actors like **Liminal Panda**.

The project includes:
- A Python-based `gtpdoor` listener that executes simulated C2 commands
- AES encrypted communication with pre-shared key
- A companion **simulator** script that sends crafted GTP-C packets
- PCAP generation and logging support for **NDR** and **telecom detection research**

> ⚠️ This project is for **research and defense purposes only**. It should only be used in isolated lab environments such as Dockerized srsRAN/Open5GS setups.

---

## 📷 Screenshots

> Server with malicious service: ![image](https://github.com/user-attachments/assets/7126b41a-a6b4-4e7a-9135-f20e28d3bd36)
> Client receiving output: ![image](https://github.com/user-attachments/assets/5d97f186-374b-4cca-913a-2d3454e68dc0)
> AES Encrypted Traffic: ![aes_encrypted_traffic](https://github.com/user-attachments/assets/c38166b8-4715-4d3f-9fd5-da6219bbcc89)
 
---

## ✨ Features

- 🛰️ **Simulates adversary behavior** abusing GTP-C for command-and-control
- 🧪 **Triggers MITRE ATT&CK control-plane techniques** (e.g., T1095, T1048, etc.)
- 📝 **Logs executed commands and raw traffic**
- 📁 **Auto-captures PCAPs** for use with Suricata, Zeek, or ML models
- ⚡ Supports **packet-based C2**, not application-layer (no TCP/HTTP)

## 🧪 Use Case: Telecom NDR / Detection Engineering

This simulation is ideal for:
- Testing **telecom-aware network detection rules**
- Generating labeled datasets for **AI/ML training**
- Research into **low-and-slow C2 over non-standard ports**
- Validating detection of **control-plane abuse in 4G/5G networks**

---

## 🚀 Quick Start

### 1. Start the GTPDoor listener
Run inside your srsRAN/Open5GS Docker container:

```python3 gtpdoor.py```

_Python Requirements_:
```pip3 install pycryptodome==3.19.0```

## 🧠 Inspired by…

This simulation was inspired by public threat intel on:
- Liminal Panda (UNC215)
- GTPdoor-style implants
- Real-world telecom espionage behaviors

---

## 🔐 Disclaimer

This project is for educational and research purposes only.
Do not run this on production networks or any system without explicit permission.
