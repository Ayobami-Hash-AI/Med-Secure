# Phase 2 — Network Segmentation

**Status:** Baseline and interface inventory observed; additional interface assignments not yet confirmed.

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

## Next procedure — Pending user execution
Enter hn0 for WAN, hn4 for LAN, hn3 for OPT1, hn1 for OPT2, and hn2 for OPT3, pressing Enter after each. Submit an empty response at the next optional-interface prompt to finish the list. Review the summary before confirming. Record the post-assignment console as evidence; then configure zone addresses and test client connectivity and firewall policy. OPT labels can be renamed to zone names in the web interface later.

## Remaining validation
- Confirm saved WAN/LAN/OPT assignments.
- Configure SOC 10.10.20.1/24, CLINICAL 10.10.30.1/24 and ATTACK 10.10.40.1/24.
- Establish a controlled management path; verify client DHCP, DNS and approved egress.
- Test allowed and denied inter-zone flows; export a configuration backup and validate recovery.

## Publication and privacy
Three screenshots are preserved as flattened PNGs with host labels and the Netgate device identifier masked. Deliberately assigned lab MACs and private lab addressing remain for reproducibility. Each screenshot appears once in this journal; other documentation links here rather than duplicating images.

## Project documentation summary
I reviewed my clean-install checkpoint, verified pfSense startup and the existing WAN/CORP addressing, and correlated all five guest interfaces with the static lab MAC plan. I declined VLAN setup because the planned zones use separate virtual adapters. I recorded the remaining interface assignments as pending until confirmed by subsequent console evidence.
