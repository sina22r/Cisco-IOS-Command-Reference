# Cisco IOS Command Reference

# Style Guide

---

## Purpose

This document defines the writing standards used throughout the Cisco IOS Command Reference repository.

Every document in this repository should follow these guidelines to maintain consistency, readability, and professional quality.

---

# Repository Structure

```
Cisco-IOS-Command-Reference/
│
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── STYLE_GUIDE.md
├── Common-Mistakes/
├── Volumes/
│
├── Volume01-IOS-Fundamentals/
├── Volume02-Interface-Configuration/
├── ...
└── Volume25-Hidden-Commands/
```

---

# Volume Structure

Each volume contains exactly four files.

```
README.md

01_Configuration_Commands.md

02_Verification_Commands.md

03_Labs.md

04_CheatSheet.md
```

---

# Command Documentation Format

Every command must follow this structure.

```
# Command Name

## Syntax:

...

## Example:

...

## Description:

...
```

Never change this order.

---

# Command Titles

Always use

```
# command
```

Example

```
# show ip route
```

Do not use

```
## show ip route
```

or

```
### show ip route
```

---

# Syntax

Syntax should contain only Cisco IOS syntax.

Do not include explanations.

Correct

```
ip route NETWORK MASK NEXT_HOP
```

Incorrect

```
Configure a static route

ip route ...
```

---

# Examples

Examples must use realistic Cisco IOS CLI output.

Good

```
R1(config)# ip route 10.10.10.0 255.255.255.0 192.168.1.2
```

Avoid unrealistic or incomplete examples.

---

# Description

Descriptions must

- explain what the command does

- explain when it is used

- explain important behavior

Descriptions should not be only one sentence.

---

# Line Length

Wrap paragraphs around 70–80 characters.

Avoid extremely long lines.

---

# Markdown

Use Markdown only.

Never use HTML.

---

# Tables

Always use GitHub Markdown tables.

Example

| Command | Purpose |
|---------|---------|
| show ip route | Displays routing table |

---

# Navigation

Every file must end with

```
Navigation

⬆️ Back to Contents

⬅️ Previous

➡️ Next
```

Never omit navigation.

---

# Contents

Every document begins with a Contents section.

Every entry must link to its heading.

Example

```
- show ip route

- show ip interface

- ping
```

---

# Topologies

Labs should use ASCII topology diagrams.

Example

```
LAN ---- R1 ===== R2 ---- LAN
```

For CCNP-level labs, use enterprise-style topologies whenever possible.

---

# CLI Output

Whenever possible, include realistic Cisco IOS output.

Avoid shortened or fictional output unless used for clarity.

---

# Naming Convention

Volumes

```
Volume09-Static-Routing
```

Files

```
01_Static_Route_Configuration_Commands.md
```

Never rename existing files.

---

# Duplicate Commands

Duplicate commands are allowed.

Example

```
show ip route
```

may appear in

- IPv4

- Static Routing

- RIP

- EIGRP

- OSPF

- BGP

- Troubleshooting

Each volume should be usable independently.

---

# Labs

Every lab should contain

- Objective

- Topology

- Tasks

- Configuration

- Verification

- Expected Result

Never skip a section.

---

# Cheat Sheets

Cheat Sheets should contain

Configuration Commands

Verification Commands

Frequently Used Commands

Troubleshooting Commands

Quick Reference Tables

---

# English

All documentation must be written in English.

---

# Cisco IOS Versions

Commands should target modern Cisco IOS XE releases unless noted otherwise.

Legacy commands may be included when historically important.

---

# Repository Philosophy

This repository is designed to be

- a Cisco IOS command reference

- a learning resource

- a CCNA reference

- a CCNP reference

- an enterprise operations reference

Every contribution should improve consistency, technical accuracy, and usability.
