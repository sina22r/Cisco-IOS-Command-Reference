# EtherChannel Verification Commands

---

**Volume:** 06 • EtherChannel

**Estimated Reading Time:** 35 Minutes

---

## Contents

- [show etherchannel summary](#show-etherchannel-summary)
- [show etherchannel detail](#show-etherchannel-detail)
- [show etherchannel port-channel](#show-etherchannel-port-channel)
- [show pagp neighbor](#show-pagp-neighbor)
- [show lacp neighbor](#show-lacp-neighbor)
- [show interfaces port-channel](#show-interfaces-port-channel)
- [show running-config interface port-channel](#show-running-config-interface-port-channel)

---

# show etherchannel summary

## Syntax:

    show etherchannel summary

## Example:

    SW1# show etherchannel summary

## Description:

**Displays a summary of all EtherChannel groups, including the
Port-Channel number, protocol (LACP, PAgP, or None), bundle
status, and the state of each member interface. This is the
primary command for verifying EtherChannel operation.**

------------------------------------------------------------

# show etherchannel detail

## Syntax:

    show etherchannel detail

## Example:

    SW1# show etherchannel detail

## Description:

**Displays detailed information about every EtherChannel,
including protocol details, member interfaces, operational
status, load-balancing information, and interface
capabilities.**

------------------------------------------------------------

# show etherchannel port-channel

## Syntax:

    show etherchannel port-channel

## Example:

    SW1# show etherchannel port-channel

## Description:

**Displays information about all logical Port-Channel
interfaces, including operational state, member interfaces,
and configuration details.**

------------------------------------------------------------

# show pagp neighbor

## Syntax:

    show pagp neighbor

## Example:

    SW1# show pagp neighbor

## Description:

**Displays neighboring devices participating in PAgP,
including their Port-Channel information and negotiation
status.**

------------------------------------------------------------

# show lacp neighbor

## Syntax:

    show lacp neighbor

## Example:

    SW1# show lacp neighbor

## Description:

**Displays neighboring devices participating in LACP,
including system IDs, port priorities, and operational
states.**

------------------------------------------------------------

# show interfaces port-channel

## Syntax:

    show interfaces port-channel NUMBER

## Example:

    SW1# show interfaces port-channel 1

## Description:

**Displays operational information for the specified
Port-Channel interface, including interface status, traffic
statistics, MTU, bandwidth, and encapsulation details.**

------------------------------------------------------------

# show running-config interface port-channel

## Syntax:

    show running-config interface port-channel NUMBER

## Example:

    SW1# show running-config interface port-channel 1

## Description:

**Displays the running configuration of the specified
Port-Channel interface, allowing verification of VLAN,
trunking, IP addressing, and other interface-specific
settings.**

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_EtherChannel_Configuration_Commands.md](01_EtherChannel_Configuration_Commands.md)**

➡️ Next: **[03_EtherChannel_Labs.md](03_EtherChannel_Labs.md)**
