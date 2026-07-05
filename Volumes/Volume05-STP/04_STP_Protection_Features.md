# STP Protection Features

---

**Volume:** 05 • Spanning Tree Protocol

**Estimated Reading Time:** 35 Minutes

---

## Contents

- [spanning-tree portfast](#spanning-tree-portfast)
- [spanning-tree portfast default](#spanning-tree-portfast-default)
- [spanning-tree bpduguard enable](#spanning-tree-bpduguard-enable)
- [spanning-tree portfast bpduguard default](#spanning-tree-portfast-bpduguard-default)
- [spanning-tree bpdufilter enable](#spanning-tree-bpdufilter-enable)
- [spanning-tree portfast bpdufilter default](#spanning-tree-portfast-bpdufilter-default)
- [spanning-tree guard root](#spanning-tree-guard-root)
- [spanning-tree guard loop](#spanning-tree-guard-loop)

---

# spanning-tree portfast

## Syntax:

    spanning-tree portfast

## Example:

    SW1(config-if)# spanning-tree portfast

## Description:

**Enables PortFast on an access interface, allowing the port
to transition directly to the Forwarding state without
passing through the Listening and Learning states.**

------------------------------------------------------------

# spanning-tree portfast default

## Syntax:

    spanning-tree portfast default

## Example:

    SW1(config)# spanning-tree portfast default

## Description:

**Enables PortFast by default on all eligible access ports.
Trunk interfaces are not affected by this command.**

------------------------------------------------------------

# spanning-tree bpduguard enable

## Syntax:

    spanning-tree bpduguard enable

## Example:

    SW1(config-if)# spanning-tree bpduguard enable

## Description:

**Enables BPDU Guard on an interface. If a BPDU is received,
the interface is placed into the err-disabled state to help
protect the network from switching loops.**

------------------------------------------------------------

# spanning-tree portfast bpduguard default

## Syntax:

    spanning-tree portfast bpduguard default

## Example:

    SW1(config)# spanning-tree portfast bpduguard default

## Description:

**Automatically enables BPDU Guard on all interfaces where
PortFast is enabled. This is a recommended security best
practice in enterprise networks.**

------------------------------------------------------------

# spanning-tree bpdufilter enable

## Syntax:

    spanning-tree bpdufilter enable

## Example:

    SW1(config-if)# spanning-tree bpdufilter enable

## Description:

**Prevents the interface from sending and receiving BPDUs.
This command should be used only in carefully controlled
network environments.**

------------------------------------------------------------

# spanning-tree portfast bpdufilter default

## Syntax:

    spanning-tree portfast bpdufilter default

## Example:

    SW1(config)# spanning-tree portfast bpdufilter default

## Description:

**Enables BPDU Filter by default on interfaces where PortFast
is active. If a BPDU is received, normal STP operation is
restored automatically.**

------------------------------------------------------------

# spanning-tree guard root

## Syntax:

    spanning-tree guard root

## Example:

    SW1(config-if)# spanning-tree guard root

## Description:

**Prevents an interface from becoming a Root Port. If a
superior BPDU is received, the interface is placed into the
Root-Inconsistent state until the condition is cleared.**

------------------------------------------------------------

# spanning-tree guard loop

## Syntax:

    spanning-tree guard loop

## Example:

    SW1(config-if)# spanning-tree guard loop

## Description:

**Prevents alternate or root ports from transitioning to the
Forwarding state when expected BPDUs are no longer received.
This feature helps prevent Layer 2 loops caused by
unidirectional link failures.**

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[03_RSTP_Commands.md](03_RSTP_Commands.md)**

➡️ Next: **[05_STP_Labs.md](05_STP_Labs.md)**
