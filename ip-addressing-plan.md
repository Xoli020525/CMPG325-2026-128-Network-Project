# IP Addressing Plan (VLSM)

Assigned block: **172.30.84.0/23** (512 addresses, 172.30.84.0 – 172.30.85.255)

VLSM was used so each VLAN receives a subnet close to its actual host requirement,
keeping the design efficient and leaving the majority of the block — all of
172.30.85.0/24 plus part of .84.0/25 — untouched for future growth.

| VLAN | Department / Purpose | Subnet | Mask | Gateway (SVI) | Usable Range | Hosts Req'd |
|---|---|---|---|---|---|---|
| 10 | Administration & Management | 172.30.84.0/27 | 255.255.255.224 | 172.30.84.1 | .2 – .30 | 12 |
| 20 | Editorial / Newsroom | 172.30.84.32/27 | 255.255.255.224 | 172.30.84.33 | .34 – .62 | 25 |
| 30 | Advertising & Sales | 172.30.84.64/27 | 255.255.255.224 | 172.30.84.65 | .66 – .94 | 18 |
| 40 | Design & Pre-Press Production | 172.30.84.96/27 | 255.255.255.224 | 172.30.84.97 | .98 – .126 | 12 |
| 50 | Boardroom (wired + wireless) | 172.30.84.128/28 | 255.255.255.240 | 172.30.84.129 | .130 – .142 | 10 |
| 60 | Servers (File / Print / DNS) | 172.30.84.144/29 | 255.255.255.248 | 172.30.84.145 | .146 – .150 | 5 |
| 70 | Voice / VoIP handsets (CR11) | 172.30.84.160/27 | 255.255.255.224 | 172.30.84.161 | .162 – .190 | 25 (reserve) |
| 99 | Device Management Plane (SSH) | 172.30.84.192/28 | 255.255.255.240 | 172.30.84.193 | .194 – .206 | 13 (devices) |
| — | WAN link (R1 ↔ ISP) | 172.30.84.208/30 | 255.255.255.252 | 172.30.84.209 | .209 – .210 | 2 |
| — | Reserved for future growth | 172.30.84.224/27 – 172.30.85.255/24 | — | — | unused block | — |

**Sizing rationale:** Editorial received the largest data subnet (/27, 30 usable) as
the biggest department by headcount; Servers received the smallest practical subnet
(/29); the Management/SSH plane (VLAN 99) and Boardroom (VLAN 50) were each sized at
/28; the WAN link uses a /30, the minimum for a point-to-point connection.
