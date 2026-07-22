<div align="center">

# 🌐 Implementation of Static Routing with Four Networks Using Cisco Packet Tracer

[![Simulation Tool](https://img.shields.io/badge/Tool-Cisco%20Packet%20Tracer-orange.svg)](#)
[![Status](https://img.shields.io/badge/Status-Verified%20%26%20Tested-brightgreen.svg)](#)

A complete simulation project focusing on designing, configuring, and verifying static routing across four distinct network segments using Cisco 1841 routers and 2960 switches in Cisco Packet Tracer.


---

## 📸 Project Simulation outputs

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



## 🗺️ Network Addressing Scheme

### 1. Host Subnets & Interfaces
| Network | Device | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **Network 1** | PC0 | `192.168.1.2` | `255.255.255.0` | `192.168.1.1` |
| | PC1 | `192.168.1.3` | `255.255.255.0` | `192.168.1.1` |
| **Network 2** | PC2 | `192.168.2.2` | `255.255.255.0` | `192.168.2.1` |
| | PC3 | `192.168.2.3` | `255.255.255.0` | `192.168.2.1` |
| **Network 3** | PC4 | `192.168.3.2` | `255.255.255.0` | `192.168.3.1` |
| | PC5 | `192.168.3.3` | `255.255.255.0` | `192.168.3.1` |
| **Network 4** | PC6 | `192.168.4.2` | `255.255.255.0` | `192.168.4.1` |
| | PC7 | `192.168.4.3` | `255.255.255.0` | `192.168.4.1` |

### 2. Router WAN Connections
* **Router 1:** LAN: `192.168.1.1` | Serial (to R2): `11.0.0.2`
* **Router 2:** LAN: `192.168.2.1` | Serial (to R1): `11.0.0.3` | Serial (to R3): `12.0.0.2`
* **Router 3:** LAN: `192.168.3.1` | Serial (to R2): `12.0.0.3` | Serial (to R4): `13.0.0.2`
* **Router 4:** LAN: `192.168.4.1` | Serial (to R3): `13.0.0.3`

---

## 📂 Repository File Structure

```text
Implementation-of-Static-Routing-with-four-networks-using-Cisco-Packet-Tracer/
│
├── routingss/
│   ├── Screenshot from 2026-07-22 10-06-54.png   # Network topology overall view
│   ├── Screenshot from 2026-07-22 10-07-17.png   # Simulation outbound packet path
│   └── Screenshot from 2026-07-22 10-07-37.png   # Simulation return packet verification
│
├── ciscostatic4network.pkt                      # Cisco Packet Tracer project file
└── README.md                                    # Project documentation


## 🚀 How to Run & Test
1. Open **Cisco Packet Tracer**.
2. Load the project file `ciscostatic4network.pkt`.
3. Open command prompt on **PC0** (`192.168.1.2`)[cite: 1].
4. Execute ping command to test connectivity across the network[cite: 1]:
   ```
   ping 192.168.4.3
   ```


1. Switch to Simulation Mode to visually inspect packet forwarding through Router 1 → Router 2 → Router 3 → Router 4[cite: 1].
