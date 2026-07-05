# Static Route Configuration Commands

---

**Volume:** 09 • Static Routing

**Estimated Reading Time:** 60 Minutes

---

## Contents

- [ip route](#ip-route)
- [ipv6 route](#ipv6-route)
- [ip default-network](#ip-default-network)
- [ip classless](#ip-classless)
- [ip route permanent](#ip-route-permanent)
- [Floating Static Route](#floating-static-route)
- [Recursive Static Route](#recursive-static-route)
- [Fully Specified Static Route](#fully-specified-static-route)
- [Directly Attached Static Route](#directly-attached-static-route)
- [Null Route](#null-route)

---

# ip route

## Syntax:

    ip route NETWORK MASK {NEXT_HOP | EXIT_INTERFACE}

## Example:

    R1(config)# ip route 10.10.10.0 255.255.255.0 192.168.1.2

## Description:

**Creates a static IPv4 route by specifying either the
next-hop IPv4 address or the outgoing interface. Static
routes are manually configured and remain in the routing
table until removed or the associated interface becomes
unavailable.**

------------------------------------------------------------

# ipv6 route

## Syntax:

    ipv6 route PREFIX/PREFIX_LENGTH {NEXT_HOP | EXIT_INTERFACE}

## Example:

    R1(config)# ipv6 route 2001:DB8:20::/64 FE80::2 GigabitEthernet0/0

## Description:

**Creates a static IPv6 route. When using a link-local
next-hop address, the outgoing interface must also be
specified.**

------------------------------------------------------------

# ip default-network

## Syntax:

    ip default-network NETWORK

## Example:

    R1(config)# ip default-network 172.16.0.0

## Description:

**Defines a candidate default network for routing decisions.
This legacy command exists primarily for compatibility with
older Cisco IOS deployments. Modern networks typically use a
static default route instead.**

------------------------------------------------------------

# ip classless

## Syntax:

    ip classless

## Example:

    R1(config)# ip classless

## Description:

**Enables classless routing behavior. When enabled, Cisco IOS
uses the longest prefix match available in the routing table
instead of dropping packets because of missing classful
subnet information. This command is enabled by default on
modern Cisco IOS releases.**

------------------------------------------------------------

# ip route permanent

## Syntax:

    ip route NETWORK MASK {NEXT_HOP | EXIT_INTERFACE} permanent

## Example:

    R1(config)# ip route 10.20.30.0 255.255.255.0 192.168.1.2 permanent

## Description:

**Creates a permanent static route that remains installed in
the routing table even if the outgoing interface or next-hop
becomes unavailable. This option should be used only when the
network design specifically requires persistent routing
entries.**

------------------------------------------------------------

# Floating Static Route

## Syntax:

    ip route NETWORK MASK NEXT_HOP ADMINISTRATIVE_DISTANCE

## Example:

    R1(config)# ip route 172.16.20.0 255.255.255.0 192.168.1.2 200

## Description:

**Creates a backup static route by assigning an
administrative distance higher than the preferred routing
source. The route is installed only when the primary route
is unavailable.**

------------------------------------------------------------

# Recursive Static Route

## Syntax:

    ip route NETWORK MASK NEXT_HOP

## Example:

    R1(config)# ip route 10.50.0.0 255.255.0.0 192.168.1.2

## Description:

**Creates a recursive static route. Cisco IOS performs an
additional routing table lookup to determine how to reach the
specified next-hop address before forwarding packets.**

------------------------------------------------------------

# Fully Specified Static Route

## Syntax:

    ip route NETWORK MASK EXIT_INTERFACE NEXT_HOP

## Example:

    R1(config)# ip route 10.60.0.0 255.255.0.0 GigabitEthernet0/0 192.168.1.2

## Description:

**Creates a fully specified static route by defining both the
outgoing interface and the next-hop address. This approach
eliminates recursive lookups and is commonly recommended on
multi-access networks such as Ethernet.**

------------------------------------------------------------

# Directly Attached Static Route

## Syntax:

    ip route NETWORK MASK EXIT_INTERFACE

## Example:

    R1(config)# ip route 10.70.0.0 255.255.0.0 Serial0/0/0

## Description:

**Creates a static route that forwards packets directly out
of the specified interface. This method is commonly used on
point-to-point links where recursive next-hop resolution is
unnecessary.**

------------------------------------------------------------

# Null Route

## Syntax:

    ip route NETWORK MASK Null0

## Example:

    R1(config)# ip route 172.16.0.0 255.240.0.0 Null0

## Description:

**Creates a static route that forwards matching packets to
the Null0 interface, silently discarding the traffic. Null
routes are commonly used for route summarization, loop
prevention, and protection against routing black holes.**

------------------------------------------------------------

## Static Routing Summary

Static routing provides deterministic packet forwarding,
minimal CPU utilization, and complete administrative control.
Cisco IOS supports several types of static routes, including
standard, floating, recursive, fully specified, directly
attached, permanent, and Null routes for both IPv4 and IPv6
networks.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_Static_Route_Verification_Commands.md](02_Static_Route_Verification_Commands.md)**
