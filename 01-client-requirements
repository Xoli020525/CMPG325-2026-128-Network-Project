# Client Requirements Analysis

**Client:** Molemane Community Newspaper (Lichtenburg) — Media industry
**Project ID:** CMPG325-2026-128 | **Client ID:** CLI-128

The client's requirements were taken from the project brief CMPG325-2026-128 and converted into specific network design decisions, as shown below.

## Requirements traced to design responses

| # | Requirement | Source | Design Response |
|---|---|---|---|
| 1 | Provide reliable connectivity and suitable network services for all newspaper departments. | Client brief §6 | Use a hierarchical network consisting of an edge router, an L3 core switch, and dedicated access switches for each department. |
| 2 | Use the assigned 172.30.84.0/23 address block as the basis for the network. | Client brief §6 | Apply VLSM to create 8 VLANs and a WAN link, while keeping approximately 60% of the address space available for future growth. |
| 3 | Provide the boardroom with both dedicated wireless access and a wired presentation connection. | Design constraint §8 | Use VLAN 50 on SW-BOARD with a dedicated wired presentation port and a dedicated AP/SSID. |
| 4 | Configure, verify, and demonstrate secure SSH-based device management. | Networking challenge §9 | Use VLAN 99 as the management network and configure SSH-only VTY access on R1 and all switches. |
| 5 | Support future VoIP handsets without requiring the network to be redesigned. | Change request §10 | Reserve VLAN 70 for voice traffic, keeping it separate from data traffic and allowing room for future growth. |
| 6 | Develop a working and testable Cisco Packet Tracer network implementation. | Client brief §6 | Complete the actual Packet Tracer implementation during Milestone 2 using the Milestone 1 design. |

## Functional groups

- **Administration & Management** — office administration; needs shared file/print access.
- **Editorial / Newsroom** — largest user group; needs reliable internet and file storage access.
- **Advertising & Sales** — client-facing staff selling ad space.
- **Design & Pre-Press Production** — page layout and print preparation.
- **Boardroom** — shared meeting space; requires simultaneous dedicated wired and wireless presentation connectivity.
- **Supporting infrastructure** — server function (file/print/DNS), SSH device-management plane, and a voice VLAN reserved for the CR11 VoIP roll-out.

