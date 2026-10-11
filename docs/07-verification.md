# Verification Evidence

## Lab verification matrix

| Control or milestone | Status | Evidence / limitation |
|---|---|---|
| Firmware virtualization | Observed enabled | Task Manager S03; initial command output differed. |
| Four Private zone switches | Verified in inventory | S10 shows CORP, SOC, CLINICAL and ATTACK. |
| Five FW01 adapters / static mapping | Verified in inventory | S14 and S16; guest selection S19 confirms interface order. |
| pfSense CE 2.8.1 installed and booted | Verified | S30 displays version and Bootup complete. |
| WAN DHCP / CORP gateway | Verified in console | S30: WAN hn0 DHCP; LAN hn4 10.10.10.1/24. |
| CORP client DHCP / internet / DNS | Pending | No client lease or reachability test supplied. |
| All four internal gateway addresses | Verified in console | [P2-11](08-phase-02-network-segmentation.md#checkpoint-10--consolidated-interface-and-address-verification): CORP 10.10.10.1/24, SOC 10.10.20.1/24, CLINICAL 10.10.30.1/24 and ATTACK 10.10.40.1/24. |
| Inter-zone isolation and firewall policies | Pending | No allowed/denied traffic-test evidence supplied. |
| MED-UBUNTU-01 VM rename | Verified | [P2-25–P2-26](10-ubuntu-endpoint-deployment.md): Hyper-V title shows MED-UBUNTU-01; earlier name was CORP-WS01. |
| Ubuntu Desktop 24.04.5 LTS installation and desktop | Verified | P2-23 installation-complete screen; P2-25 login; P2-26 desktop. |
| Ubuntu installation ISO detached | Verified | P2-24: DVD Drive set to None; subsequent login and desktop shown. |
| Ubuntu guest hostname and networking | Pending | VM display name is verified; guest hostname, IP, route and DNS require terminal evidence. |
| pfSense management access from MED-UBUNTU-01 | Pending | No successful gateway or HTTPS browser test supplied. |
| pfSense backup, restore and FW01 ISO-detached reboot | Pending | No recovery evidence supplied; Ubuntu ISO-detachment evidence does not establish FW01 media state. |

## Initial boot evidence

### S30 — Pfsense initial boot verification

Bootup complete; pfSense CE 2.8.1, WAN DHCP and CORP LAN 10.10.10.1/24. This initial checkpoint precedes the later four-zone addressing verification in P2-11. Client connectivity and policy enforcement still require testing.

![S30: pfsense initial boot verification](../evidence/phase-01/04-boot-verification/30-pfsense-initial-boot-verification.png)

## Publication checks
All 30 sanitized PNGs were decoded locally and all relative image paths checked before publication. Post-publication checks on 2026-10-11 confirmed that all 30 committed PNGs match the sanitized local files byte for byte and decode successfully. GitHub's rendered architecture page loaded 10 evidence images, and its build journal loaded the remaining 20; every image reported complete loading and a nonzero natural width. The README milestone image also loaded correctly. All six original documentation files remain present. GitHub rendering checks concern portfolio integrity, not lab connectivity.

## Next evidence to collect
Record MED-UBUNTU-01 guest hostname, IP and route, then gateway and pfSense HTTPS access, DHCP client leases, allowed and blocked traffic tests, DNS/egress checks, configuration backup and restore validation. Add new screenshots to their implementation phase only after privacy review.
