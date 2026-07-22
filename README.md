<div align="center">

# 🌐 Implementation of Static Routing with Four Networks Using Cisco Packet Tracer

[![Department](https://img.shields.io/badge/ECE-Velagapudi%20Ramakrishna%20Siddhartha%20Engineering%20College-blue.svg)](#)
[![Simulation Tool](https://img.shields.io/badge/Tool-Cisco%20Packet%20Tracer-orange.svg)](#)
[![Status](https://img.shields.io/badge/Status-Verified%20%26%20Tested-brightgreen.svg)](#)

A complete simulation project focusing on designing, configuring, and verifying static routing across four distinct network segments using Cisco 1841 routers and 2960 switches in Cisco Packet Tracer.

<br />

![Network Topology](<routingss/Screenshot from 2026-07-22 10-06-54.png>)

</div>

---

## 📸 Project Simulation Gallery

| Network Topology Setup | Outbound Simulation Flow | Successful Packet Delivery Return |
| :---: | :---: | :---: |
| ![Network Topology](<routingss/Screenshot from 2026-07-22 10-06-54.png>) | ![Simulation Flow](<routingss/Screenshot from 2026-07-22 10-07-17.png>) | ![Return Flow](<routingss/Screenshot from 2026-07-22 10-07-37.png>) |

---

## 💡 Key Features

* **Multi-Subnet Interconnectivity:** Establishes full communication across four distinct local area networks (LANs).
* **Manual Route Control:** Configures explicit static routes with next-hop IP addressing to ensure precise packet control and security.
* **Deterministic Path Selection:** Eliminates dynamic protocol overhead, conserving network bandwidth across serial links.
* **Full End-to-End Verification:** Validated through ICMP ping tests and Packet Tracer simulation mode with 0% packet loss.

---

## 🛠️ Hardware Stack & Specifications

| Component | Function / Role |
| :--- | :--- |
| **Cisco 1841 Routers (x4)** | Central routing nodes performing inter-subnet forwarding |
| **Cisco 2960 Switches (x4)** | Layer 2 access layer switches connecting end-user host devices |
| **Host PCs (x8)** | End-user workstations distributed across subnets (2 PCs per network) |
| **Serial WAN Links** | High-speed interconnects linking adjacent routers in a linear topology |

---

## ⚙️ Logic Flow

```text
  +------------------+         +--------------------------+         +-------------------+
  |    Source Host   | ------> |      Access Switch       | ------> |    Local Gateway  |
  |  (192.168.1.2)   |         |        (Layer 2)         |         |     (Router 1)    |
  +------------------+         +--------------------------+         +-------------------+
                                                                              |
                                                                              v (Static Hop)
  +------------------+         +--------------------------+         +-------------------+
  | Destination Host | <------ |      Access Switch       | <------ |   Remote Gateway  |
  |  (192.168.4.3)   |         |        (Layer 2)         |         |     (Router 4)    |
  +------------------+         +--------------------------+         +-------------------+
