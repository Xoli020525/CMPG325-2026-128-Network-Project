# CMPG325-2026-128 — Molemane Community Newspaper Network Project

Individual semester project for CMPG 325 (Computer Networks), NWU Mafikeng.
Client: **Molemane Community Newspaper**, Lichtenburg — Media industry.

## Project Summary

Design, simulation, and secure device management (SSH) implementation of a
switched/routed network for a small community newspaper, built on the
assigned addressing block **172.30.84.0/23**. The design accommodates a
boardroom with dedicated wired and wireless presentation connectivity, and
is provisioned in advance for a VoIP handset rollout (CR11).

| | |
|---|---|
| **Student** | Sentse, X (37940066) |
| **Client ID** | CLI-128 |
| **Assigned challenge** | SSH — secure device management plane |
| **Addressing block** | 172.30.84.0/23 |

## Repository Structure

## Project Status

- [x] **Milestone 1 (28 Aug 2026)** — Client requirements, IP addressing plan, initial Packet Tracer build
- [x] **Milestone 2 (2 Oct 2026)** — Full Packet Tracer build, SSH configuration, testing evidence
- [ ] **Final submission (16 Oct 2026)** — Full portfolio, technical report, video demonstration

---

## Milestone 2 — Implementation & SSH

### Completed Tasks
- ✅ Full Packet Tracer build with VLANs, trunks, and SVIs configured
- ✅ SSH implemented on all 7 devices (R1 + 6 switches)
- ✅ SSH tested successfully from management PC (VLAN 99)
- ✅ Telnet access rejected on all devices
- ✅ Inter-VLAN routing verified (all departments communicate)
- ✅ Configuration files exported for all devices
- ✅ Testing evidence documented with screenshots

### Assigned Feature: SSH (Secure Device Management Plane)

**Configuration applied on all devices:**
- Domain name: `molemane.local`
- RSA keys: 2048-bit
- Local admin user: `admin` (privilege 15)
- SSH version 2 enforced
- VTY lines restricted to SSH only (`transport input ssh`)
- Telnet disabled

**Management plane (VLAN 99):**
- Subnet: 172.30.84.192/28
- SW-CORE management IP: 172.30.84.193
- PC-MANAGEMENT: 172.30.84.194

**Devices configured:**
R1, SW-CORE, SW-ADMIN, SW-EDIT, SW-SALES, SW-DESIGN, SW-BOARD

### Verification
- Ping tests: all departments can reach each other across VLANs
- SSH login from PC-MANAGEMENT to SW-CORE successful
- Telnet connection to SW-CORE rejected (only SSH accepted)

### Testing Evidence
- [Connectivity Tests](07-testing/connectivity-tests.md)
- [SSH Verification](07-testing/ssh-verification.md)
- [Telnet Rejection](07-testing/telnet-rejection.md)

### Milestone 2 Additions
- `06-configuration/` — Running configurations for all 7 devices
- `07-testing/` — Test documentation and screenshots

---

## Academic Integrity

This is individual work submitted under NWU's academic integrity policy.
Any AI assistance used complies with the applicable NWU AI Policy; the
student remains responsible for the correctness, understanding, and
verification of everything submitted.
