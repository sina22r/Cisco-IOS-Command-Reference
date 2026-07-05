# Static Routing Cheat Sheet

---

**Volume:** 09 • Static Routing

**Estimated Reading Time:** 15 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `ip route NETWORK MASK NEXT_HOP` | Configure an IPv4 static route |
| `ip route NETWORK MASK EXIT_INTERFACE` | Configure a directly attached static route |
| `ip route NETWORK MASK EXIT_INTERFACE NEXT_HOP` | Configure a fully specified static route |
| `ip route NETWORK MASK NEXT_HOP AD` | Configure a floating static route |
| `ip route NETWORK MASK NEXT_HOP permanent` | Configure a permanent static route |
| `ip route NETWORK MASK Null0` | Configure a Null Route |
| `ip route 0.0.0.0 0.0.0.0 NEXT_HOP` | Configure a default route |
| `ipv6 route PREFIX/LENGTH NEXT_HOP` | Configure an IPv6 static route |
| `ipv6 route PREFIX/LENGTH LINK_LOCAL_ADDRESS INTERFACE` | Configure an IPv6 static route using a link-local next-hop |
| `ip classless` | Enable classless routing |
| `ip default-network NETWORK` | Configure a candidate default network (legacy) |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show ip route` | Display the IPv4 routing table |
| `show ipv6 route` | Display the IPv6 routing table |
| `show ip route static` | Display only IPv4 static routes |
| `show running-config \| include ip route` | Display configured IPv4 static routes |
| `show running-config \| include ipv6 route` | Display configured IPv6 static routes |
| `show ip cef` | Display the IPv4 CEF table |
| `show ipv6 cef` | Display the IPv6 CEF table |
| `ping ADDRESS` | Verify IPv4 connectivity |
| `ping ipv6 ADDRESS` | Verify IPv6 connectivity |
| `traceroute ADDRESS` | Trace an IPv4 forwarding path |
| `traceroute ipv6 ADDRESS` | Trace an IPv6 forwarding path |

---

## Static Route Types

| Route Type | Example |
|------------|---------|
| Standard Static Route | `ip route 10.10.10.0 255.255.255.0 192.168.1.2` |
| Default Route | `ip route 0.0.0.0 0.0.0.0 192.168.1.1` |
| Floating Static Route | `ip route 10.10.10.0 255.255.255.0 192.168.2.2 200` |
| Recursive Static Route | `ip route 10.10.10.0 255.255.255.0 192.168.1.2` |
| Fully Specified Static Route | `ip route 10.10.10.0 255.255.255.0 GigabitEthernet0/0 192.168.1.2` |
| Directly Attached Static Route | `ip route 10.10.10.0 255.255.255.0 Serial0/0/0` |
| Permanent Static Route | `ip route 10.10.10.0 255.255.255.0 192.168.1.2 permanent` |
| Null Route | `ip route 172.16.0.0 255.240.0.0 Null0` |
| IPv6 Static Route | `ipv6 route 2001:DB8:20::/64 FE80::2 GigabitEthernet0/0` |

---

## Frequently Used Commands

| Task | Command |
|------|---------|
| Configure an IPv4 static route | `ip route` |
| Configure an IPv6 static route | `ipv6 route` |
| Configure a default route | `ip route 0.0.0.0 0.0.0.0` |
| Display routing table | `show ip route` |
| Display IPv6 routing table | `show ipv6 route` |
| Verify static routes | `show ip route static` |
| Test connectivity | `ping`, `ping ipv6` |
| Trace packet path | `traceroute`, `traceroute ipv6` |

---

## Common Troubleshooting Commands

| Problem | Verification Command |
|---------|----------------------|
| Static route missing | `show ip route` |
| IPv6 static route missing | `show ipv6 route` |
| Incorrect next-hop | `show running-config \| include ip route` |
| Recursive lookup issue | `show ip cef` |
| IPv6 forwarding issue | `show ipv6 cef` |
| Destination unreachable | `ping`, `ping ipv6` |
| Incorrect forwarding path | `traceroute`, `traceroute ipv6` |

---

## Navigation

⬆️ [Back to Contents](#static-routing-cheat-sheet)

⬅️ Previous: **[03_Static_Route_Labs.md](03_Static_Route_Labs.md)**

➡️ Next: **[Volume 10 – RIP](../Volume10-RIP/README.md)**
