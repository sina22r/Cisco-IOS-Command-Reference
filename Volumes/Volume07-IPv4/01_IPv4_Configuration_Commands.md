# IPv4 Configuration Commands

---

**Volume:** 07 • IPv4

**Estimated Reading Time:** 60 Minutes

---

## Contents

- [ip address](#ip-address)
- [ip address secondary](#ip-address-secondary)
- [no ip address](#no-ip-address)
- [ip unnumbered](#ip-unnumbered)
- [ip mtu](#ip-mtu)
- [ip tcp adjust-mss](#ip-tcp-adjust-mss)
- [ip directed-broadcast](#ip-directed-broadcast)
- [no ip redirects](#no-ip-redirects)
- [no ip proxy-arp](#no-ip-proxy-arp)

---

# ip address

## Syntax:

    ip address IP_ADDRESS SUBNET_MASK

## Example:

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ip address 192.168.10.1 255.255.255.0

## Description:

**Assigns an IPv4 address and subnet mask to a Layer 3
interface. The interface must be administratively enabled
before it can forward IPv4 traffic.**

------------------------------------------------------------

# ip address secondary

## Syntax:

    ip address IP_ADDRESS SUBNET_MASK secondary

## Example:

    R1(config-if)# ip address 192.168.20.1 255.255.255.0 secondary

## Description:

**Adds an additional IPv4 address to the same interface.
Secondary addresses are commonly used during network
migration or when supporting multiple logical subnets on a
single physical interface.**

------------------------------------------------------------

# no ip address

## Syntax:

    no ip address

## Example:

    R1(config-if)# no ip address

## Description:

**Removes all IPv4 addresses configured on the interface,
returning it to an unnumbered state.**

------------------------------------------------------------

# ip unnumbered

## Syntax:

    ip unnumbered INTERFACE

## Example:

    R1(config)# interface Serial0/0/0

    R1(config-if)# ip unnumbered Loopback0

## Description:

**Assigns the IPv4 address of another local interface to the
current interface. This feature conserves IPv4 address space
and is commonly used on point-to-point links.**

------------------------------------------------------------

# ip mtu

## Syntax:

    ip mtu BYTES

## Example:

    R1(config-if)# ip mtu 1400

## Description:

**Configures the maximum IPv4 packet size that the interface
can transmit without fragmentation. This command affects only
IPv4 traffic and does not modify the Layer 2 MTU.**

------------------------------------------------------------

# ip tcp adjust-mss

## Syntax:

    ip tcp adjust-mss BYTES

## Example:

    R1(config-if)# ip tcp adjust-mss 1360

## Description:

**Adjusts the TCP Maximum Segment Size (MSS) for connections
passing through the interface. This command is commonly used
to prevent fragmentation on VPN, GRE, and PPPoE links.**

------------------------------------------------------------

# ip directed-broadcast

## Syntax:

    ip directed-broadcast

## Example:

    R1(config-if)# ip directed-broadcast

## Description:

**Allows the router to forward directed broadcast packets
received for the connected subnet. This command is disabled
by default on modern Cisco IOS releases due to security
considerations.**

------------------------------------------------------------

# no ip redirects

## Syntax:

    no ip redirects

## Example:

    R1(config-if)# no ip redirects

## Description:

**Disables the generation of ICMP Redirect messages on the
interface. This command is commonly recommended on routed
interfaces for improved security and predictable routing
behavior.**

------------------------------------------------------------

# no ip proxy-arp

## Syntax:

    no ip proxy-arp

## Example:

    R1(config-if)# no ip proxy-arp

## Description:

**Disables Proxy ARP on the interface. When disabled, the
router no longer responds to ARP requests on behalf of other
devices, reducing unnecessary ARP traffic and improving
security.**

------------------------------------------------------------

# ip helper-address

## Syntax:

    ip helper-address IP_ADDRESS

## Example:

    R1(config-if)# ip helper-address 192.168.100.10

## Description:

**Forwards selected UDP broadcast packets received on the
interface to the specified destination. This command is most
commonly used to relay DHCP requests across different IP
subnets.**

------------------------------------------------------------

# ip virtual-reassembly

## Syntax:

    ip virtual-reassembly

## Example:

    R1(config-if)# ip virtual-reassembly

## Description:

**Enables virtual packet reassembly to process fragmented IP
packets before features such as NAT or security policies are
applied. This helps protect against certain fragmentation-
based attacks.**

------------------------------------------------------------

# ip verify unicast source reachable-via

## Syntax:

    ip verify unicast source reachable-via {rx | any}

## Example:

    R1(config-if)# ip verify unicast source reachable-via rx

## Description:

**Enables Unicast Reverse Path Forwarding (uRPF) on the
interface. The router verifies that the source IP address of
incoming packets is reachable through the routing table,
helping to prevent IP spoofing attacks.**

------------------------------------------------------------

# ip verify unicast source reachable-via allow-default

## Syntax:

    ip verify unicast source reachable-via rx allow-default

## Example:

    R1(config-if)# ip verify unicast source reachable-via rx allow-default

## Description:

**Allows uRPF to use the default route when validating source
addresses. This option is useful in networks where the
primary path to many destinations is through a default
gateway.**

------------------------------------------------------------

# ip verify unicast source reachable-via allow-self-ping

## Syntax:

    ip verify unicast source reachable-via rx allow-self-ping

## Example:

    R1(config-if)# ip verify unicast source reachable-via rx allow-self-ping

## Description:

**Permits locally generated ICMP echo packets while uRPF is
enabled. This option helps preserve management connectivity
during source validation.**

------------------------------------------------------------

## IPv4 Summary

IPv4 interface configuration provides Layer 3 connectivity by
assigning IP addresses, controlling packet forwarding
behavior, and applying interface-specific features such as
MTU, MSS adjustment, Proxy ARP, directed broadcasts, and
source validation.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_IPv4_Verification_Commands.md](02_IPv4_Verification_Commands.md)**
