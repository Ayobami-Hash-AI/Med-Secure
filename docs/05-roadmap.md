# Roadmap

## Phase 1 — Firewall foundation: verified
Host assessment, Hyper-V selection, private switches, FW01 NIC mapping, pfSense CE 2.8.1 installation and initial boot.

## Phase 2 — Network segmentation and management: in progress

### Completed
- Verified all five interface assignments and four internal gateway addresses.
- Created the CORP management VM on MED-CORP-SW: Generation 2, 4096 MB RAM, 2 vCPU and a dynamically expanding 40 GB VHDX.
- Installed Ubuntu Desktop 24.04.5 LTS, renamed the Hyper-V VM from CORP-WS01 to **MED-UBUNTU-01**, detached the Ubuntu ISO and verified login and desktop boot.
- Published 26 Phase 2 screenshots across the [segmentation journal](08-phase-02-network-segmentation.md) and [Ubuntu deployment journal](10-ubuntu-endpoint-deployment.md).

### Next session
1. Inspect MED-UBUNTU-01 with `hostnamectl`, `ip -br a` and `ip route`. The Hyper-V display-name change does not verify the Linux guest hostname.
2. Test the CORP gateway at 10.10.10.1 and pfSense HTTPS management access.
3. Verify DHCP, DNS and approved egress; apply Ubuntu updates when connectivity is established.
4. Implement and test least-privilege inter-zone and egress policies.
5. Export a pfSense configuration backup, record rollback steps and validate recovery. Confirm FW01 installation-media detachment separately.

## Phase 3 — Enterprise identity
Windows Server AD DS, DNS, Windows workstation join, GPO and identity logging.

## Phase 4 — SOC telemetry
SIEM, Windows event forwarding/Sysmon, firewall logs, endpoint detection and dashboards.

## Phase 5 — Clinical simulation
Synthetic clinical assets, application/service flows, protected data pathways and access control.

## Phase 6 — Security validation
Isolated Kali simulation, rule validation, detections, incident reports and MITRE ATT&CK mapping.

## Phase 7 — Hardening and recovery
Vulnerability assessment, remediation, configuration backup, disaster-recovery drill and final portfolio walkthrough.
