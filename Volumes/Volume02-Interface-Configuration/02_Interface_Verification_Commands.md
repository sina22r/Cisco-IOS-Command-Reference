# Interface Verification Commands

---

**Volume:** 02 • Interface Configuration

**Estimated Reading Time:** 35 Minutes

---

## Contents

- [show interfaces](#show-interfaces)
- [show interfaces description](#show-interfaces-description)
- [show ip interface](#show-ip-interface)
- [show ip interface brief](#show-ip-interface-brief)
- [show ipv6 interface](#show-ipv6-interface)
- [show controllers](#show-controllers)
- [show interfaces status](#show-interfaces-status)
- [show interfaces counters](#show-interfaces-counters)
- [show interfaces counters errors](#show-interfaces-counters-errors)
- [show interfaces switchport](#show-interfaces-switchport)
- [show interfaces trunk](#show-interfaces-trunk)
- [show interfaces capabilities](#show-interfaces-capabilities)

---

# show interfaces

## Syntax

    show interfaces

## Example

    R1# show interfaces

## Description

    Displays detailed information for all interfaces,
    including operational status, bandwidth, duplex,
    speed, MTU, traffic statistics, and error counters.

------------------------------------------------------------

# show interfaces description

## Syntax

    show interfaces description

## Example

    R1# show interfaces description

## Description

    Displays a summary of interface descriptions,
    administrative status, and operational status.

------------------------------------------------------------

# show ip interface

## Syntax

    show ip interface

## Example

    R1# show ip interface

## Description

    Displays detailed Layer 3 information for all IPv4
    interfaces, including addressing, helper addresses,
    ACLs, and routing-related settings.

------------------------------------------------------------

# show ip interface brief

## Syntax

    show ip interface brief

## Example

    R1# show ip interface brief

    Interface              IP-Address      OK? Method Status Protocol
    GigabitEthernet0/0     192.168.1.1     YES manual up     up
    GigabitEthernet0/1     unassigned      YES unset  down   down

## Description

    Displays a summarized view of all IPv4 interfaces,
    including IP addresses, administrative status,
    and line protocol state.

------------------------------------------------------------

# show ipv6 interface

## Syntax

    show ipv6 interface

## Example

    R1# show ipv6 interface

## Description

    Displays detailed IPv6 information for every interface,
    including configured addresses, link-local addresses,
    multicast groups, and Neighbor Discovery settings.

------------------------------------------------------------

# show controllers

## Syntax

    show controllers

## Example

    R1# show controllers

## Description

    Displays hardware controller information for supported
    interfaces. This command is commonly used when
    troubleshooting physical interface problems.

------------------------------------------------------------

# show interfaces status

## Syntax

    show interfaces status

## Example

    SW1# show interfaces status

## Description

    Displays a summary of switch interface status, including
    VLAN assignment, duplex mode, speed, interface type,
    and operational state.

------------------------------------------------------------

# show interfaces counters

## Syntax

    show interfaces counters

## Example

    SW1# show interfaces counters

## Description

    Displays packet and byte counters for switch interfaces.
    This command is useful for monitoring interface traffic
    and utilization.

------------------------------------------------------------

# show interfaces counters errors

## Syntax

    show interfaces counters errors

## Example

    SW1# show interfaces counters errors

## Description

    Displays interface error counters, including CRC errors,
    runts, giants, collisions, and other physical layer
    problems that may affect network performance.

------------------------------------------------------------

# show interfaces switchport

## Syntax

    show interfaces switchport

## Example

    SW1# show interfaces switchport

## Description

    Displays Layer 2 switchport information, including the
    administrative mode, operational mode, access VLAN,
    native VLAN, and trunk configuration.

------------------------------------------------------------

# show interfaces trunk

## Syntax

    show interfaces trunk

## Example

    SW1# show interfaces trunk

## Description

    Displays all active trunk interfaces, including the trunk
    encapsulation, native VLAN, allowed VLANs, and forwarding
    state for each trunk.

------------------------------------------------------------

# show interfaces capabilities

## Syntax

    show interfaces capabilities

## Example

    SW1# show interfaces capabilities

## Description

    Displays the capabilities of each interface, including
    supported speeds, duplex modes, media types, and optional
    hardware features available on the platform.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_Interface_Configuration_Commands.md](01_Interface_Configuration_Commands.md)**

➡️ Next: **[03_Interface_Labs.md](03_Interface_Labs.md)**
