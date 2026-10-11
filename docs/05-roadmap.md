# Roadmap

## Phase 1 — Firewall foundation: verified
Host assessment, Hyper-V selection, private switches, FW01 NIC mapping, pfSense CE 2.8.1 installation, initial boot.

## Phase 2 — Network segmentation: in progress
- Detach installer ISO and verify reboot.
- Assign hn3 SOC, hn1 CLINICAL, hn2 ATTACK.
- Configure gateways and DHCP where appropriate.
- Provision a secure management path (private switches do not connect the host).
- Implement and test least-privilege inter-zone and egress policies.
- Backup pfSense configuration and record rollback steps.

## Phase 3 — Enterprise identity
Windows Server AD DS, DNS, workstation join, GPO and identity logging.

## Phase 4 — Clinical simulation
Synthetic clinical assets, application/service flows, protected data pathways, access control.

## Phase 5 — SOC telemetry
SIEM, Windows event forwarding/Sysmon, firewall logs, endpoint detection, dashboards.

## Phase 6 — Security validation
Isolated Kali simulation, rule validation, detections, incident reports, MITRE ATT&CK mapping.

## Phase 7 — Hardening and recovery
Vulnerability assessment, remediation, configuration backup, disaster-recovery drill, final portfolio walkthrough.
