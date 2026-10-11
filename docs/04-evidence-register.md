# Evidence Register

This register maps the screenshots shared during the lab build to their intended documentation sections. **Publication update: all 30 retrieved Phase 1 screenshots are now committed under `evidence/phase-01/`.** The original E01–E10 categories are retained below; S01–S30 identify individual images.

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

## Published screenshot inventory

| ID | Screenshot | Implementation group |
|---|---|---|
| S01 | [host hardware baseline](../evidence/phase-01/01-host-baseline/01-host-hardware-baseline.png) | 01-host-baseline |
| S02 | [host storage capacity](../evidence/phase-01/01-host-baseline/02-host-storage-capacity.png) | 01-host-baseline |
| S03 | [firmware virtualization enabled](../evidence/phase-01/01-host-baseline/03-firmware-virtualization-enabled.png) | 01-host-baseline |
| S04 | [host system information](../evidence/phase-01/01-host-baseline/04-host-system-information.png) | 01-host-baseline |
| S05 | [host network inventory redacted](../evidence/phase-01/01-host-baseline/05-host-network-inventory-redacted.png) | 01-host-baseline |
| S06 | [virtual adapter and vbs state](../evidence/phase-01/01-host-baseline/06-virtual-adapter-and-vbs-state.png) | 01-host-baseline |
| S07 | [hypervisor security state](../evidence/phase-01/01-host-baseline/07-hypervisor-security-state.png) | 01-host-baseline |
| S08 | [hyper v feature diagnostic](../evidence/phase-01/02-hyper-v-networking/08-hyper-v-feature-diagnostic.png) | 02-hyper-v-networking |
| S09 | [hyper v initial switch](../evidence/phase-01/02-hyper-v-networking/09-hyper-v-initial-switch.png) | 02-hyper-v-networking |
| S10 | [private zone switches](../evidence/phase-01/02-hyper-v-networking/10-private-zone-switches.png) | 02-hyper-v-networking |
| S11 | [reference topology not implemented](../evidence/phase-01/02-hyper-v-networking/11-reference-topology-not-implemented.png) | 02-hyper-v-networking |
| S12 | [netgate installer media selection](../evidence/phase-01/02-hyper-v-networking/12-netgate-installer-media-selection.png) | 02-hyper-v-networking |
| S13 | [fw01 secure boot settings](../evidence/phase-01/02-hyper-v-networking/13-fw01-secure-boot-settings.png) | 02-hyper-v-networking |
| S14 | [fw01 five network adapters](../evidence/phase-01/02-hyper-v-networking/14-fw01-five-network-adapters.png) | 02-hyper-v-networking |
| S15 | [initial adapter mac state](../evidence/phase-01/02-hyper-v-networking/15-initial-adapter-mac-state.png) | 02-hyper-v-networking |
| S16 | [static mac zone verification](../evidence/phase-01/02-hyper-v-networking/16-static-mac-zone-verification.png) | 02-hyper-v-networking |
| S17 | [iso attachment error redacted](../evidence/phase-01/03-pfsense-installation/17-iso-attachment-error-redacted.png) | 03-pfsense-installation |
| S18 | [netgate installer start](../evidence/phase-01/03-pfsense-installation/18-netgate-installer-start.png) | 03-pfsense-installation |
| S19 | [wan interface selection](../evidence/phase-01/03-pfsense-installation/19-wan-interface-selection.png) | 03-pfsense-installation |
| S20 | [wan dhcp mode](../evidence/phase-01/03-pfsense-installation/20-wan-dhcp-mode.png) | 03-pfsense-installation |
| S21 | [lan interface selection](../evidence/phase-01/03-pfsense-installation/21-lan-interface-selection.png) | 03-pfsense-installation |
| S22 | [lan default settings before change](../evidence/phase-01/03-pfsense-installation/22-lan-default-settings-before-change.png) | 03-pfsense-installation |
| S23 | [wan lan assignment confirmation](../evidence/phase-01/03-pfsense-installation/23-wan-lan-assignment-confirmation.png) | 03-pfsense-installation |
| S24 | [community edition selection](../evidence/phase-01/03-pfsense-installation/24-community-edition-selection.png) | 03-pfsense-installation |
| S25 | [zfs gpt installation options](../evidence/phase-01/03-pfsense-installation/25-zfs-gpt-installation-options.png) | 03-pfsense-installation |
| S26 | [zfs stripe no redundancy](../evidence/phase-01/03-pfsense-installation/26-zfs-stripe-no-redundancy.png) | 03-pfsense-installation |
| S27 | [virtual disk selection](../evidence/phase-01/03-pfsense-installation/27-virtual-disk-selection.png) | 03-pfsense-installation |
| S28 | [virtual disk overwrite confirmation](../evidence/phase-01/03-pfsense-installation/28-virtual-disk-overwrite-confirmation.png) | 03-pfsense-installation |
| S29 | [pfsense version selection](../evidence/phase-01/03-pfsense-installation/29-pfsense-version-selection.png) | 03-pfsense-installation |
| S30 | [pfsense initial boot verification](../evidence/phase-01/04-boot-verification/30-pfsense-initial-boot-verification.png) | 04-boot-verification |

## Privacy review
Opaque masks remove the sign-in identity/email, personal user path, controller instance identifier, Netgate device identifier, actual host labels and unrelated home-network addressing. Images are flattened RGB PNGs without original metadata. Deliberately assigned synthetic lab MAC addresses and lab IP ranges remain to support reproducibility. Originals were not committed.

The planning-reference image is explicitly labelled; installer defaults are distinguished from the final configuration. No Phase 2–7 completion is inferred from these images.

## Phase 2 evidence

See the [Phase 2 journal](08-phase-02-network-segmentation.md) for P2-01 checkpoint inventory, P2-02 startup verification and P2-03 interface inventory/assignment prompt. These three screenshots are sanitized; actual optional-interface assignment remains pending.
