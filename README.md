# MedSecure — Segmented Enterprise & Healthcare SOC Home Lab

**Platform:** Microsoft Hyper-V · pfSense CE 2.8.1 · Windows infrastructure · SOC tooling  
**Progress:** Phase 1 firewall installation verified; Phase 2 network segmentation pending.

## Mission
Build a realistic, isolated enterprise and simulated clinical security environment to demonstrate network architecture, segmentation, identity management, endpoint monitoring, SIEM analysis, detection engineering, incident response, vulnerability management and recovery. No real patient data or production assets are used.

## Current architecture
| Zone | Hyper-V switch | pfSense NIC | Address / status |
|---|---|---|---|
| WAN | Default Switch | hn0 | DHCP; observed 172.21.139.31/20 |
| CORP | MED-CORP-SW | hn4 | 10.10.10.1/24 — configured |
| SOC | MED-SOC-SW | hn3 | 10.10.20.1/24 — planned |
| CLINICAL | MED-CLINICAL-SW | hn1 | 10.10.30.1/24 — planned |
| ATTACK | MED-ATTACK-SW | hn2 | 10.10.40.1/24 — planned |

The internal switches are Hyper-V **Private** switches. The host does not automatically have access to them. A management VM or a deliberately configured management path will be required.

## Completed and verified
- Assessed GHOST host (Intel N95, 4 cores, ~32 GB RAM, NVMe storage).
- Confirmed firmware virtualization enabled and Hyper-V operation.
- Created four dedicated private switches.
- Provisioned FW01 with five adapters and deterministic MAC addresses.
- Mapped WAN hn0, CORP hn4, SOC hn3, CLINICAL hn1 and ATTACK hn2 by MAC.
- Diagnosed an ISO attachment/readability boot error and subsequently booted the Netgate installer.
- Installed pfSense Community Edition 2.8.1 on a 20 GB Hyper-V virtual disk using GPT and ZFS single-disk stripe.
- Observed successful boot, WAN DHCP address and CORP gateway 10.10.10.1/24.

## Documentation
- [Project objectives and success criteria](docs/01-objectives-and-scope.md)
- [Architecture, assets, MAC and IP plan](docs/02-architecture.md)
- [Phase 1 build journal and troubleshooting](docs/03-build-journal.md)
- [Screenshot evidence register](docs/04-evidence-register.md)
- [Implementation roadmap](docs/05-roadmap.md)
- [Troubleshooting records](docs/06-troubleshooting.md)
- [Verification matrix and boot evidence](docs/07-verification.md)

## Next milestone
Complete the remaining pfSense interface assignments, configure gateways and least-privilege firewall policies, validate isolation and connectivity, and preserve a known-good backup.

## Evidence and publication policy
**30 sanitized Phase 1 screenshots are published**, organized into host baseline, Hyper-V networking, pfSense installation and boot verification. Browse the [evidence register](docs/04-evidence-register.md#published-screenshot-inventory). Remove emails, account names, device IDs, secrets, tokens, personal paths and unrelated private information before committing images. Never publish ISO files, VHDX disks, credentials or clinical information.

**Maintainer:** Ayobami Odulaja

## Verified milestone

![pfSense CE 2.8.1 initial boot with private identifiers redacted](evidence/phase-01/04-boot-verification/30-pfsense-initial-boot-verification.png)

The console verifies installation and initial WAN/CORP addressing. Later segmentation, client connectivity and SOC tooling remain roadmap milestones.
