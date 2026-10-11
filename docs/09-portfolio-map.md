# MedSecure — Portfolio Map

![MedSecure architecture map showing verified firewall addressing and planned zone workloads](../assets/diagrams/medsecure-architecture-map.svg)

## Build sequence

| Phase | Deliverable | Current status |
|---|---|---|
| 1 — Foundation | Hyper-V switches, FW01 and pfSense installation | Verified |
| 2 — Segmentation | Interface addresses, management access, firewall policies and flow tests | In progress: addresses verified |
| 3 — Enterprise systems | Active Directory, DNS and Windows clients | Planned |
| 4 — Monitoring | Splunk, Sysmon and endpoint security telemetry | Planned |
| 5 — Healthcare simulation | Clinical endpoints and restricted access with synthetic data | Planned |
| 6 — Security exercises | Authorized attack simulations, vulnerability checks and investigations | Planned |
| 7 — Recovery and portfolio | Recovery tests, reports and verification evidence | Planned |

The diagram is a project overview, not verification of future workloads. The four internal switches are Private. Ubuntu Desktop 24.04.5 LTS has now been installed and successfully booted to the desktop on the renamed Hyper-V VM **MED-UBUNTU-01**, attached to **MED-CORP-SW**. The installation ISO was detached. Guest hostname, IP assignment, pfSense web access, policy enforcement and recovery remain unverified. See [Ubuntu deployment journal](10-ubuntu-endpoint-deployment.md).

## Supporting documentation

- [Detailed architecture and asset plan](02-architecture.md)
- [Implementation roadmap](05-roadmap.md)
- [Phase 2 journal and screenshots](08-phase-02-network-segmentation.md)
- [Troubleshooting records](06-troubleshooting.md)
- [Verification evidence](07-verification.md)

## Project documentation summary

I mapped my verified pfSense foundation and four internal gateway addresses to the enterprise, SOC, clinical and controlled testing zones. I selected Ubuntu Desktop 24.04 LTS for the CORP management workstation, with installation and desktop login verified on MED-UBUNTU-01; network and security verification are pending. I distinguished planned workloads from completed infrastructure and documented the sequence from segmentation to monitoring, security exercises and recovery.
