# EtherChannel Configuration Commands

---

**Volume:** 06 • EtherChannel

**Estimated Reading Time:** 50 Minutes

---

## Contents

- [channel-group](#channel-group)
- [channel-protocol](#channel-protocol)
- [interface port-channel](#interface-port-channel)
- [port-channel load-balance](#port-channel-load-balance)
- [lacp system-priority](#lacp-system-priority)
- [lacp port-priority](#lacp-port-priority)
- [pagp learn-method](#pagp-learn-method)

---

# channel-group

## Syntax:

    channel-group GROUP_NUMBER mode {active | passive | desirable | auto | on}

## Example:

    SW1(config-if)# channel-group 1 mode active

## Description:

**Adds an interface to an EtherChannel group. The mode
determines whether LACP, PAgP, or a static EtherChannel is
used to negotiate or establish the bundle.**

------------------------------------------------------------

# channel-protocol

## Syntax:

    channel-protocol {lacp | pagp}

## Example:

    SW1(config-if)# channel-protocol lacp

## Description:

**Specifies the EtherChannel negotiation protocol before
assigning the interface to a channel group. Supported
protocols are LACP and PAgP.**

------------------------------------------------------------

# interface port-channel

## Syntax:

    interface port-channel NUMBER

## Example:

    SW1(config)# interface port-channel 1

## Description:

**Creates or enters the logical Port-Channel interface used
to configure settings that apply to the entire EtherChannel
bundle.**

------------------------------------------------------------

# port-channel load-balance

## Syntax:

    port-channel load-balance {src-mac | dst-mac | src-dst-mac | src-ip | dst-ip | src-dst-ip}

## Example:

    SW1(config)# port-channel load-balance src-dst-ip

## Description:

**Configures the load-balancing algorithm used by
EtherChannel. The selected method determines how traffic is
distributed across the physical member interfaces.**

------------------------------------------------------------

# lacp system-priority

## Syntax:

    lacp system-priority PRIORITY

## Example:

    SW1(config)# lacp system-priority 4096

## Description:

**Configures the LACP system priority. Lower values have a
higher priority and influence which switch becomes the active
LACP system during negotiation.**

------------------------------------------------------------

# lacp port-priority

## Syntax:

    lacp port-priority PRIORITY

## Example:

    SW1(config-if)# lacp port-priority 100

## Description:

**Configures the LACP priority for an individual interface.
Lower values increase the likelihood that the interface will
be selected as an active member of the EtherChannel.**

------------------------------------------------------------

# pagp learn-method

## Syntax:

    pagp learn-method {aggregate-port | physical-port}

## Example:

    SW1(config-if)# pagp learn-method aggregate-port

## Description:

**Specifies how PAgP learns and forwards MAC addresses.
Depending on the selected method, addresses are associated
with either the logical Port-Channel interface or the
individual physical interfaces.**

------------------------------------------------------------

## EtherChannel Summary

EtherChannel combines multiple physical Ethernet interfaces
into a single logical connection, providing increased
bandwidth, redundancy, and simplified management. Cisco IOS
supports three EtherChannel operating methods:

- **LACP (IEEE 802.3ad / IEEE 802.1AX)**
- **PAgP (Cisco Proprietary)**
- **Static EtherChannel (Mode `on`)**

When configuring EtherChannel, all member interfaces should
have matching speed, duplex, VLAN configuration, trunk mode,
and STP settings to ensure successful bundle formation.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_EtherChannel_Verification_Commands.md](02_EtherChannel_Verification_Commands.md)**
