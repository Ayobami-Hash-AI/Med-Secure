# Phase 2 — Network Segmentation

**Status:** All five interface assignments are applied and verified at the console. Optional-interface IP configuration remains pending.

## Checkpoint 1 — Baseline review
The supplied Hyper-V view shows FW01 off and a checkpoint named `FW01 - pfSense 2.8.1 Clean Install`. This confirms a checkpoint entry exists, not that restore has been tested. The next console screenshot shows pfSense CE 2.8.1 completing startup, WAN hn0 receiving 172.28.254.188/20 by DHCP, and CORP/LAN hn4 retaining 10.10.10.1/24. ISO removal was instructed but is not directly proved by these screenshots.

![P2-01: Hyper-V clean-install checkpoint](../evidence/phase-02/01-interface-assignment/01-fw01-clean-install-checkpoint.png)

![P2-02: pfSense startup and addressing verification](../evidence/phase-02/01-interface-assignment/02-pfsense-startup-wan-corp-verification.png)

## Checkpoint 2 — Interface inventory before assignment
I opened console option 1 (Assign Interfaces), reviewed the five detected Hyper-V NICs, and selected `n` for VLAN setup. The screenshot is paused at the WAN interface-name prompt; assignment has not been committed.

| Role | Guest NIC | Deliberate lab MAC | Observed link state | Assignment status |
|---|---|---|---|---|
| WAN | hn0 | 00:15:5d:01:00:01 | up | Existing; preserve |
| CORP / LAN | hn4 | 00:15:5d:01:00:02 | up | Existing; preserve |
| SOC / OPT1 | hn3 | 00:15:5d:01:00:03 | down | Planned |
| CLINICAL / OPT2 | hn1 | 00:15:5d:01:00:04 | down | Planned |
| ATTACK / OPT3 | hn2 | 00:15:5d:01:00:05 | down | Planned |

The NICs are detected even where link state is down. Peer VM connectivity and Hyper-V switch attachments must be checked before interpreting this as a fault. MAC correlation preserves the mapping despite guest enumeration order.

![P2-03: Detected interfaces and WAN assignment prompt](../evidence/phase-02/01-interface-assignment/03-interface-inventory-before-assignment.png)

## Checkpoint 3 — Assignment summary reviewed
I entered WAN hn0, LAN hn4, OPT1 hn3, OPT2 hn1 and OPT3 hn2. The proposed assignment summary matches the five-zone plan. The corrected screenshot is paused at the proceed prompt with a blank input field; this is not evidence that the configuration has been applied. The earlier screenshot was superseded at the same evidence path to avoid duplicate publication.

![P2-04: Five-interface assignment summary before confirmation](../evidence/phase-02/01-interface-assignment/04-five-interface-assignment-summary.png)

## Checkpoint 4 — Applied assignments verified
After confirming the assignment, I returned to the console menu. The resulting interface list verifies WAN hn0, LAN hn4, OPT1 hn3, OPT2 hn1 and OPT3 hn2. WAN retains DHCP address 172.28.254.188/20 and LAN retains 10.10.10.1/24. OPT1, OPT2 and OPT3 have no displayed IP addresses yet. This verifies interface assignment, not client connectivity or firewall-policy enforcement.

![P2-05: Applied five-interface assignments and preserved WAN/CORP addressing](../evidence/phase-02/01-interface-assignment/05-applied-interface-assignment-verification.png)

## Checkpoint 5 — SOC interface selection
I opened console option 2 and verified the displayed interface numbers: WAN/hn0 is 1, LAN/hn4 is 2, OPT1/hn3 is 3, OPT2/hn1 is 4 and OPT3/hn2 is 5. The screenshot is paused before selecting an interface. No SOC IP address has been entered or verified yet.

![P2-06: Console IP configuration interface selection](../evidence/phase-02/02-interface-addressing/06-soc-interface-selection.png)

## Checkpoint 6 — SOC static IPv4 values entered
I selected interface 3 (OPT1/hn3), declined DHCP for its IPv4 address, entered 10.10.20.1 with prefix 24, and left the upstream gateway blank because SOC is an internal network. The console is paused at the DHCP6 question. These are entered values; completion and applied addressing still require subsequent evidence.

![P2-07: SOC static IPv4 entry and IPv6 configuration prompt](../evidence/phase-02/02-interface-addressing/07-soc-static-ipv4-entry.png)

## Next procedure — Complete SOC address prompts
At the DHCP6 question, enter `n`. At the new IPv6 address prompt, press Enter for none, consistent with the current IPv4 lab plan. If prompted to enable a DHCP server on OPT1, enter `n` for now; client addressing will be configured separately. Retain HTTPS if asked to revert the webConfigurator to HTTP. Capture the resulting console interface list to verify 10.10.20.1/24 is applied. See [Netgate console menu documentation](https://docs.netgate.com/pfsense/en/latest/config/console-menu.html).

## Remaining validation
- Configure SOC 10.10.20.1/24, CLINICAL 10.10.30.1/24 and ATTACK 10.10.40.1/24.
- Establish a controlled management path; verify client DHCP, DNS and approved egress.
- Test allowed and denied inter-zone flows; export a configuration backup and validate recovery.

## Publication and privacy
Seven screenshots have been reviewed for privacy. The first three have host labels and the Netgate device identifier masked; P2-04 through P2-07 contain no visible personal information or sensitive identifiers and required no redaction. Deliberately assigned lab MACs and private lab addressing remain for reproducibility. Each screenshot appears once in this journal; other documentation links here rather than duplicating images.

## Project documentation summary
I reviewed my clean-install checkpoint, verified pfSense startup and the existing WAN/CORP addressing, and correlated all five guest interfaces with the static lab MAC plan. I declined VLAN setup because the planned zones use separate virtual adapters. I entered the five interface names and reviewed the proposed summary against the zone plan. I subsequently verified all five applied assignments at the console, with WAN and CORP addressing preserved. The three optional interfaces still require IP configuration.
