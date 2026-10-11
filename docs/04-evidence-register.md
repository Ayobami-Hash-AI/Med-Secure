# Evidence Register

This register maps the screenshots shared during the lab build to their intended documentation sections. **Images are not yet published to this repository; do not interpret filenames below as committed evidence.** Before publishing, redact identifying information and verify each screenshot's subject.

| Evidence ID | Description | Document |
|---|---|---|
| E01 | Host hardware and virtualization discovery | 02-architecture |
| E02 | Hyper-V feature/cmdlet and initial switch inspection | 03-build-journal |
| E03 | Four private virtual switches | 02-architecture |
| E04 | FW01 Generation 2 VM settings and five network adapters | 03-build-journal |
| E05 | PowerShell verification of static MAC mapping | 02-architecture |
| E06 | ISO attachment failure and troubleshooting | 03-build-journal |
| E07 | Netgate installer boot and WAN/LAN assignment | 03-build-journal |
| E08 | CORP LAN IP/DHCP installer setup | 03-build-journal |
| E09 | CE edition, ZFS/GPT/stripe and 20 GB disk selection | 03-build-journal |
| E10 | Final pfSense 2.8.1 console boot and WAN/LAN address verification | 03-build-journal |

Recommended image naming: `e01-host-baseline.png`, `e05-static-mac-verification.png`, `e10-pfsense-boot-validation.png`. Store under `evidence/phase-01/` and embed beside corresponding documentation. Do not publish raw screenshots containing personal identifiers or machine-specific license IDs.
