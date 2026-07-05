# Static Route Verification Commands

---

**Volume:** 09 • Static Routing

**Estimated Reading Time:** 40 Minutes

---

## Contents

- [show ip route](#show-ip-route)
- [show ipv6 route](#show-ipv6-route)
- [show ip route static](#show-ip-route-static)
- [show running-config | include ip route](#show-running-config--include-ip-route)
- [show running-config | include ipv6 route](#show-running-config--include-ipv6-route)
- [show ip cef](#show-ip-cef)
- [show ipv6 cef](#show-ipv6-cef)
- [ping](#ping)
- [ping ipv6](#ping-ipv6)
- [traceroute](#traceroute)
- [traceroute ipv6](#traceroute-ipv6)

---

# show ip route

## Syntax:

    show ip route

## Example:

    R1# show ip route

    S    10.10.10.0/24 [1/0] via 192.168.1.2

## Description:

**Displays the IPv4 routing table, including static, connected,
local, and dynamically learned routes. Static routes are
identified by the code `S`.**

------------------------------------------------------------

# show ipv6 route

## Syntax:

    show ipv6 route

## Example:

    R1# show ipv6 route

    S   2001:DB8:20::/64
        via FE80::2, GigabitEthernet0/0

## Description:

**Displays the IPv6 routing table, including configured
static IPv6 routes and their associated next-hop
information.**

------------------------------------------------------------

# show ip route static

## Syntax:

    show ip route static

## Example:

    R1# show ip route static

## Description:

**Displays only static IPv4 routes, making it easier to
verify manually configured routing entries.**

------------------------------------------------------------

# show running-config | include ip route

## Syntax:

    show running-config | include ip route

## Example:

    R1# show running-config | include ip route

## Description:

**Displays all configured IPv4 static routes from the
running configuration.**

------------------------------------------------------------

# show running-config | include ipv6 route

## Syntax:

    show running-config | include ipv6 route

## Example:

    R1# show running-config | include ipv6 route

## Description:

**Displays all configured IPv6 static routes from the
running configuration.**

------------------------------------------------------------

# show ip cef

## Syntax:

    show ip cef

## Example:

    R1# show ip cef

## Description:

**Displays IPv4 Cisco Express Forwarding entries used to
forward packets toward static routes.**

------------------------------------------------------------

# show ipv6 cef

## Syntax:

    show ipv6 cef

## Example:

    R1# show ipv6 cef

## Description:

**Displays IPv6 Cisco Express Forwarding entries associated
with configured static routes.**

------------------------------------------------------------

# ping

## Syntax:

    ping IP_ADDRESS

## Example:

    R1# ping 10.10.10.1

## Description:

**Verifies IPv4 reachability through the configured static
route.**

------------------------------------------------------------

# ping ipv6

## Syntax:

    ping ipv6 IPV6_ADDRESS

## Example:

    R1# ping ipv6 2001:DB8:20::1

## Description:

**Verifies IPv6 reachability through the configured static
route.**

------------------------------------------------------------

# traceroute

## Syntax:

    traceroute IP_ADDRESS

## Example:

    R1# traceroute 10.10.10.1

## Description:

**Displays the Layer 3 forwarding path for IPv4 packets,
helping verify the operation of static routes.**

------------------------------------------------------------

# traceroute ipv6

## Syntax:

    traceroute ipv6 IPV6_ADDRESS

## Example:

    R1# traceroute ipv6 2001:DB8:20::1

## Description:

**Displays the Layer 3 forwarding path for IPv6 packets,
allowing verification of IPv6 static routing.**

------------------------------------------------------------

## Static Route Verification Summary

These commands verify IPv4 and IPv6 static routing,
forwarding, route installation, and end-to-end connectivity.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_Static_Route_Configuration_Commands.md](01_Static_Route_Configuration_Commands.md)**

➡️ Next: **[03_Static_Route_Labs.md](03_Static_Route_Labs.md)**
