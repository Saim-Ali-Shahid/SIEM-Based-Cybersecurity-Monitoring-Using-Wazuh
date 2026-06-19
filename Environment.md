# Lab Environment

This document describes the hardware, software, virtualization platform, and network configuration used to implement the **SIEM-Based Cybersecurity Monitoring Using Wazuh** project.

---

# Host Machine

| Component               | Specification                                                     |
| ----------------------- | ----------------------------------------------------------------- |
| Operating System        | Windows 11 (Host)                                                 |
| Virtualization Platform | VMware Workstation                                                |
| Purpose                 | Hosting all virtual machines used in the cybersecurity laboratory |

---

# Virtual Machines

## Ubuntu Wazuh Server

| Component        | Configuration                                 |
| ---------------- | --------------------------------------------- |
| Operating System | Ubuntu 24.04 LTS                              |
| RAM              | 8 GB                                          |
| CPU              | 4 Cores                                       |
| Storage          | 90 GB                                         |
| Role             | Wazuh Manager, Wazuh Dashboard, Wazuh Indexer |

### Services Installed

* Wazuh Manager
* Wazuh Dashboard
* Wazuh Indexer
* File Integrity Monitoring
* Log Collection

---

## Windows 10 Endpoint

| Component        | Configuration      |
| ---------------- | ------------------ |
| Operating System | Windows 10 x64     |
| RAM              | 4 GB               |
| CPU              | 2 Cores            |
| Storage          | 60 GB              |
| Role             | Monitored Endpoint |

### Installed Components

* Wazuh Agent
* Windows Event Logs
* Windows Defender

---

## Kali Linux

| Component        | Configuration             |
| ---------------- | ------------------------- |
| Operating System | Kali Linux 2025.x         |
| RAM              | 2.6 GB                    |
| CPU              | 2 Cores                   |
| Storage          | 80 GB                     |
| Role             | Attack Simulation Machine |

### Security Tools

* Hydra
* Nmap
* OpenSSH Client
* Linux Networking Utilities

---

# Network Configuration

Each virtual machine was configured with two virtual network adapters.

| Network Adapter | Purpose                                                     |
| --------------- | ----------------------------------------------------------- |
| NAT             | Internet connectivity for software installation and updates |
| Host-Only       | Secure communication between virtual machines               |

---

# Virtual Machine Roles

| Machine    | Primary Role       |
| ---------- | ------------------ |
| Ubuntu     | SIEM Server        |
| Windows 10 | Monitored Endpoint |
| Kali Linux | Attacker Machine   |

---

# Project Modules

The project was implemented in three phases.

## Module 1

Centralized Log Collection

* Linux Logs
* Windows Event Logs
* SSH Authentication Logs

---

## Module 2

File Integrity Monitoring (FIM)

* Real-time file monitoring
* Integrity verification
* Security alert generation

---

## Module 3

Endpoint Security Monitoring

### Attack Simulation

* SSH Brute Force Attack (Hydra)
* Network Reconnaissance (Nmap)

### Detection

* Custom Wazuh Rules
* Security Alerts
* MITRE ATT&CK Mapping

---

# Custom Detection Rules

| Rule ID | Description                          |
| ------- | ------------------------------------ |
| 100100  | SSH Authentication Failure Detection |
| 100101  | SSH Brute Force Detection            |

---

# Technologies Used

* Wazuh SIEM
* Ubuntu Linux
* Windows 10
* Kali Linux
* VMware Workstation
* XML
* SSH
* Hydra
* Nmap

---

# Skills Demonstrated

* SIEM Deployment
* Security Monitoring
* Endpoint Security
* File Integrity Monitoring
* Log Collection
* Threat Detection
* Security Event Analysis
* Linux Administration
* Windows Administration
* Virtualization
* Cyber Attack Simulation
* Custom Rule Development

---

# Repository Structure

```text
.
├── README.md
├── LICENSE
├── Environment.md
├── Documentation/
├── Configurations/
├── images/
└── screenshots/
```

---

# Notes

This laboratory environment was developed exclusively for educational and cybersecurity research purposes. All attack simulations were performed within an isolated virtual network using VMware Workstation to ensure that no production or external systems were affected.
