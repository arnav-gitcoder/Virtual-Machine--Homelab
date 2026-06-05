# Cybersecurity Home Lab

## Overview

This repository documents the design and development of my personal Cybersecurity Home Lab. The environment is built using virtualization technologies to simulate real-world networking and security scenarios in a safe and isolated setting.

The lab serves as a platform for learning networking, system administration, virtualization, firewall management, and cybersecurity through hands-on experimentation. It is designed to evolve over time, allowing new technologies, operating systems, and security tools to be integrated as the environment grows.

---

## Objectives

* Build a realistic virtual network environment.
* Gain practical experience with enterprise networking concepts.
* Learn firewall deployment and administration.
* Practice Linux system administration.
* Develop cybersecurity skills through hands-on experimentation.
* Create a flexible platform for future security projects and labs.

---

## High-Level Architecture

```text
Host System
    │
    ▼
Virtualization Platform
    │
    ▼
Network Security Layer
    │
    ▼
Internal Lab Network
    │
    ├── Security Workstations
    ├── Linux Servers
    ├── Test Machines
    └── Future Lab Components
```

The architecture is intentionally modular and may change as additional systems, services, and security tools are introduced.

---

## Core Components

### Network Security Layer

The lab utilizes a dedicated firewall solution to provide:

* Network segmentation
* Routing
* DHCP services
* DNS services
* Firewall rule management
* Controlled internet access

### Security Workstations

Security-focused operating systems are deployed for:

* Security research
* Penetration testing practice
* Tool development and testing
* Network analysis
* System administration

### Server Systems

General-purpose server operating systems are used for:

* Service deployment
* Application testing
* Linux administration
* Infrastructure experimentation
* Future enterprise simulations

---

## Technologies Used

The technologies used within the lab may evolve over time and currently include:

| Technology                 | Purpose                                 |
| -------------------------- | --------------------------------------- |
| VirtualBox                 | Virtualization Platform                 |
| pfSense                    | Firewall & Routing                      |
| Kali Linux                 | Security Workstation                    |
| Ubuntu Linux               | General-Purpose Linux System            |
| Linux Networking Utilities | Network Configuration & Troubleshooting |

---

## Network Design Principles

The lab follows several core design principles:

* Isolation from production systems
* Secure network segmentation
* Reproducible configurations
* Scalability for future expansion
* Hands-on learning through practical implementation

---

## Current Environment

The current environment includes:

* pfSense Firewall
* Kali Linux
* Ubuntu Linux

Additional systems and services will be incorporated as the lab evolves.

---

## Future Enhancements

Potential future additions include:

* Active Directory
* Windows Server
* Security Information and Event Management (SIEM)
* Intrusion Detection / Prevention Systems
* Vulnerability Management Platforms
* Cloud Security Labs
* Network Monitoring Solutions
* Additional Linux Servers
* Containerized Applications
* Capture The Flag (CTF) Environments

---

## Purpose of This Repository

This repository serves as a central reference point for the design, configuration, and evolution of my cybersecurity home lab. Individual projects, configurations, and experiments conducted within the environment may be documented in separate repositories and linked here.

---

## Disclaimer

This lab is intended solely for educational, research, and authorized testing purposes. All activities are performed within systems owned, controlled, or explicitly authorized for use.
