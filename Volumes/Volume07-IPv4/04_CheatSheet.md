# IPv4 Cheat Sheet

---

**Volume:** 07 • IPv4

**Estimated Reading Time:** 15 Minutes

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `ip address IP_ADDRESS SUBNET_MASK` | Assign an IPv4 address to an interface |
| `ip address IP_ADDRESS SUBNET_MASK secondary` | Configure a secondary IPv4 address |
| `no ip address` | Remove all IPv4 addresses from an interface |
| `ip unnumbered INTERFACE` | Use another interface's IPv4 address |
| `ip mtu BYTES` | Configure the IPv4 MTU |
| `ip tcp adjust-mss BYTES` | Adjust the TCP Maximum Segment Size (MSS) |
| `ip directed-broadcast` | Enable forwarding of directed broadcasts |
| `ip helper-address IP_ADDRESS` | Relay selected UDP broadcast packets |
| `no ip redirects` | Disable ICMP Redirect messages |
| `no ip proxy-arp` | Disable Proxy ARP |
| `ip virtual-reassembly` | Enable IP fragment reassembly |
| `ip verify unicast source reachable-via {rx \| any}` | Enable Unicast Reverse Path Forwarding (uRPF) |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show ip interface brief` | Display a summary of all IPv4 interfaces |
| `show ip interface` | Display detailed IPv4 interface information |
| `show ip protocols` | Display active IPv4 routing protocols |
| `show ip route` | Display the IPv4 routing table |
| `show ip arp` | Display the ARP table |
| `show arp` | Display cached ARP entries |
| `show hosts` | Display the local hostname table |
| `show running-config interface INTERFACE` | Display the interface configuration |
| `show ip cef` | Display the CEF forwarding table |
| `show ip cef exact-route SRC_IP DST_IP` | Display the exact forwarding decision |
| `ping IP_ADDRESS` | Test IPv4 connectivity |
| `traceroute IP_ADDRESS` | Display the Layer 3 path to a destination |

---

## Frequently Used Commands

| Task | Command |
|------|---------|
| Configure an IPv4 address | `ip address` |
| Configure a secondary address | `ip address ... secondary` |
| Remove an IPv4 address | `no ip address` |
| Display interface status | `show ip interface brief` |
| Display routing table | `show ip route` |
| Display ARP entries | `show ip arp` |
| Test connectivity | `ping` |
| Trace packet path | `traceroute` |

---

## Common Troubleshooting

| Problem | Verification Command |
|---------|----------------------|
| Interface is down | `show ip interface brief` |
| Incorrect interface configuration | `show running-config interface INTERFACE` |
| Incorrect IP address | `show ip interface` |
| Missing route | `show ip route` |
| ARP resolution failure | `show ip arp` |
| Forwarding issue | `show ip cef` |
| End-to-end connectivity failure | `ping`, `traceroute` |

---

## Navigation

⬆️ [Back to Contents](#ipv4-cheat-sheet)

⬅️ Previous: **[03_IPv4_Labs.md](03_IPv4_Labs.md)**

➡️ Next: **[Volume 08 – IPv6](../Volume08-IPv6/README.md)**
