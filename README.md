# Cisco IOS Command Reference

> A comprehensive, practical, and continuously growing Cisco IOS command reference for **CCNA**, **CCNP ENCOR**, and real-world Enterprise Networking.

---

## About

This repository is designed to be a practical Cisco IOS reference rather than a traditional networking book.

Instead of lengthy theoretical explanations, every command includes:

- The command itself
- A real CLI example
- A short and practical explanation

The goal is to provide a resource that network engineers can quickly search and use during study, labs, or production environments.

---

# Project Goals

- Cover Cisco IOS commands from beginner to advanced
- Include commands used in both CCNA and CCNP ENCOR
- Focus on real-world usage
- Keep explanations concise and practical
- Organize commands by technology
- Continuously expand with new Cisco IOS features

---

# Repository Structure

```
Cisco-IOS-Command-Reference/

├── README.md
├── CONTRIBUTING.md
├── CHANGELOG.md
├── LICENSE
│
├── Volumes/
│
│   ├── Volume01-Basic-IOS/
│   ├── Volume02-Interface-Configuration/
│   ├── Volume03-VLAN/
│   ├── Volume04-Trunk/
│   ├── Volume05-STP/
│   ├── Volume06-EtherChannel/
│   ├── Volume07-IPv4/
│   ├── Volume08-IPv6/
│   ├── Volume09-Static-Routing/
│   ├── Volume10-RIP/
│   ├── Volume11-EIGRP/
│   ├── Volume12-OSPF/
│   ├── Volume13-BGP/
│   ├── Volume14-Route-Redistribution/
│   ├── Volume15-ACL/
│   ├── Volume16-NAT/
│   ├── Volume17-DHCP/
│   ├── Volume18-FHRP/
│   ├── Volume19-QoS/
│   ├── Volume20-Security/
│   ├── Volume21-AAA/
│   ├── Volume22-SNMP/
│   ├── Volume23-Automation/
│   ├── Volume24-Troubleshooting/
│   └── Volume25-Hidden-Commands/
|
├── Labs/
│
├── CheatSheets/
│
├── PDFs/
│
├── Images/
│
├── Assets/
│
├── Templates/
│   ├── Command-Template.md
│   ├── README-Template.md
│   ├── Lab-Template.md
│   └── CheatSheet-Template.md
│
└── Scripts/
```

---

# Repository Organization

Each volume is organized independently.

Example:

```
Volume12-OSPF/

README.md

01-OSPF-Commands.md

02-Verification.md

03-Labs.md

04-CheatSheet.md
```

This structure keeps the repository clean, scalable, and easy to navigate.

---

# Command Format

Every command follows the same simple format:

```
Command Name

Command

Example

Description
```

Example:

```
show version

Command

show version

Example

R1# show version

Description

Displays the IOS version, uptime, hardware information,
boot image, and licensing details.
```

The objective is simplicity and quick access to information.

---

# Covered Technologies

- Cisco IOS Fundamentals
- Interface Configuration
- VLAN
- Trunking
- STP
- EtherChannel
- IPv4
- IPv6
- Static Routing
- RIP
- EIGRP
- OSPF
- BGP
- Route Redistribution
- ACL
- NAT
- DHCP
- FHRP (HSRP, VRRP, GLBP)
- QoS
- Layer 2 Security
- AAA
- SNMP
- Network Automation
- Troubleshooting
- Hidden IOS Commands

---

# Labs

Most volumes include practical labs designed to reinforce configuration and troubleshooting skills.

The labs are based on real Cisco IOS scenarios whenever possible.

---

# Cheat Sheets

Each volume includes a concise cheat sheet summarizing the most commonly used commands.

These are intended for quick review before exams or while working on production networks.

---

# Who Is This Repository For?

- CCNA Students
- CCNP ENCOR Students
- Network Engineers
- System Administrators
- NOC Engineers
- SOC Engineers
- Cisco Enthusiasts

---

# Progress Tracker

| Volume | Status |
|---------|--------|
| [Volume 01 - IOS Fundamentals](Volumes/Volume01-IOS-Fundamentals/README.md) | ✅ Completed |
| [Volume 02 - Interface Configuration](Volumes/Volume02-Interface-Configuration/README.md) | ✅ Completed |
| [Volume 03 - VLAN](Volumes/Volume03-VLAN/README.md) | ✅ Completed |
| [Volume 04 - Trunk](Volumes/Volume04-Trunk/README.md) | ✅ Completed |
| [Volume 05 - STP](Volumes/Volume05-STP/README.md) | ✅ Completed |
| [Volume 06 - EtherChannel](Volumes/Volume06-EtherChannel/README.md) | ✅ Completed |
| [Volume 07 - IPv4](Volumes/Volume07-IPv4/README.md) | ✅ Completed |
| [Volume 08 - IPv6](Volumes/Volume08-IPv6/README.md) | ✅ Completed |
| [Volume 09 - Static Routing](Volumes/Volume09-Static-Routing/README.md) | ✅ Completed |
| [Volume 10 - RIP](Volumes/Volume10-RIP/README.md) | ✅ Completed |
| [Volume 11 - EIGRP](Volumes/Volume11-EIGRP/README.md) | ✅ Completed |
| [Volume 12 - OSPF](Volumes/Volume12-OSPF/README.md) | ✅ Completed |
| [Volume 13 - BGP](Volumes/Volume13-BGP/README.md) | ✅ Completed |
| [Volume 14 - Route Redistribution](Volumes/Volume14-Route-Redistribution/README.md) | 🚧 In Progress |
| [Volume 15 - ACL](Volumes/Volume15-ACL/README.md) | ⏳ Planned |
| [Volume 16 - NAT](Volumes/Volume16-NAT/README.md) | ⏳ Planned |
| [Volume 17 - DHCP](Volumes/Volume17-DHCP/README.md) | ⏳ Planned |
| [Volume 18 - FHRP](Volumes/Volume18-FHRP/README.md) | ⏳ Planned |
| [Volume 19 - QoS](Volumes/Volume19-QoS/README.md) | ⏳ Planned |
| [Volume 20 - Security](Volumes/Volume20-Security/README.md) | ⏳ Planned |
| [Volume 21 - AAA](Volumes/Volume21-AAA/README.md) | ⏳ Planned |
| [Volume 22 - SNMP](Volumes/Volume22-SNMP/README.md) | ⏳ Planned |
| [Volume 23 - Automation](Volumes/Volume23-Automation/README.md) | ⏳ Planned |
| [Volume 24 - Troubleshooting](Volumes/Volume24-Troubleshooting/README.md) | ⏳ Planned |
| [Volume 25 - Hidden Commands](Volumes/Volume25-Hidden-Commands/README.md) | ⏳ Planned |


---

# Additional References

| Section | Status |
|---------|--------|
| [Common Mistakes](Common-Mistakes/README.md) | ⏳ Planned |

---


# Contributing

Contributions, corrections, and suggestions are always welcome.

Please read **CONTRIBUTING.md** before submitting a Pull Request.

---

# License

This project is licensed under the MIT License.

---

# Disclaimer

Cisco®, Cisco IOS®, CCNA®, CCNP®, CCIE®, IOS XE®, and related names are trademarks of Cisco Systems, Inc.

This repository is an independent educational project and is not affiliated with or endorsed by Cisco Systems.
