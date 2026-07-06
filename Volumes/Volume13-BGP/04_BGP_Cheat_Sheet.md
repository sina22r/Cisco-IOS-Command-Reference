# BGP Cheat Sheet

---

## Basic Configuration

| Command | Purpose |
|---------|---------|
| `router bgp 65001` | Enable BGP |
| `bgp router-id 1.1.1.1` | Configure Router ID |
| `neighbor x.x.x.x remote-as xxxx` | Configure Neighbor |
| `neighbor x.x.x.x description TEXT` | Neighbor Description |
| `neighbor x.x.x.x password PASSWORD` | MD5 Authentication |
| `neighbor x.x.x.x shutdown` | Disable Neighbor |

---

## Route Advertisement

| Command | Purpose |
|---------|---------|
| `network A.B.C.D mask M.M.M.M` | Advertise Network |
| `aggregate-address A.B.C.D M.M.M.M` | Route Summarization |
| `default-information originate` | Advertise Default Route |
| `redistribute connected` | Redistribute Connected Routes |
| `redistribute static` | Redistribute Static Routes |

---

## Neighbor Options

| Command | Purpose |
|---------|---------|
| `neighbor x.x.x.x update-source Loopback0` | Loopback Peering |
| `neighbor x.x.x.x next-hop-self` | Modify Next Hop |
| `neighbor x.x.x.x send-community` | Advertise Communities |
| `neighbor x.x.x.x ebgp-multihop N` | Multi-Hop eBGP |
| `neighbor x.x.x.x ttl-security hops N` | GTSM Protection |
| `neighbor x.x.x.x default-originate` | Advertise Default Route |
| `neighbor x.x.x.x remove-private-as` | Remove Private AS |
| `neighbor x.x.x.x allowas-in` | Accept Own AS |
| `neighbor x.x.x.x local-as XXXX` | Alternate Local AS |

---

## Verification

| Command | Purpose |
|---------|---------|
| `show ip bgp` | Display BGP Table |
| `show ip bgp summary` | Neighbor Summary |
| `show ip bgp neighbors` | Neighbor Details |
| `show ip route bgp` | Installed BGP Routes |
| `show ip bgp community` | Community Information |
| `show ip bgp regexp` | Filter by AS Path |

---

## Troubleshooting

| Command | Purpose |
|---------|---------|
| `debug ip bgp` | General Debug |
| `debug ip bgp updates` | Update Messages |
| `debug ip bgp events` | Session Events |
| `clear ip bgp *` | Reset All Sessions |
| `clear ip bgp x.x.x.x soft in` | Soft Reset Inbound |
| `clear ip bgp x.x.x.x soft out` | Soft Reset Outbound |

---

---

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[03_BGP_Labs.md](03_BGP_Labs.md)**

➡️ Next: **[Volume 14 — Route Redistribution](../Volume14-Route-Redistribution/README.md)**
