# Troubleshooting Records

| Issue | Evidence | Findings and disposition | Remaining check |
|---|---|---|---|
| Conflicting firmware virtualization output | [S01–S07](02-architecture.md#host-baseline-evidence) | Initial processor output reported False; Task Manager later showed virtualization enabled and systeminfo detected a hypervisor. | Record a consistent post-reboot baseline. |
| Hyper-V cmdlets unavailable | [S08–S09](03-build-journal.md#s08--hyper-v-feature-diagnostic) | Initial feature state was Disabled; later Get-VMSwitch output shows the Default Switch. Exact intervening enablement steps were not captured. | Preserve the enablement/restart command on rebuild. |
| Guest NIC order differs from zone order | [S16](02-architecture.md#s16--static-mac-zone-verification) and [S19](03-build-journal.md#s19--wan-interface-selection) | Correlated static lab MAC suffixes to guest hn interfaces rather than assuming enumeration order. | Reconfirm after hardware changes. |
| ISO attachment failed | [S17](03-build-journal.md#s17--iso-attachment-error-redacted) | Error reported corrupted/unreadable media in a cloud-synced user path. Local copy or fresh download was recommended; exact correction was not captured. S18 demonstrates subsequent installer boot. | Validate media readability/hash during rebuild; no completed hash check claimed. |
| Installer LAN defaults differ from target | [S22](03-build-journal.md#s22--lan-default-settings-before-change), [S30](07-verification.md) | Installer screen shows 192.168.1.1; boot console confirms final 10.10.10.1. | Verify final DHCP scope and a client lease. |
| Host cannot directly manage Private switches | [Architecture](02-architecture.md#isolation-and-management-considerations) | MED-UBUNTU-01 is installed on MED-CORP-SW as the CORP management endpoint. | Check guest IP/route, gateway reachability and pfSense HTTPS access. |

| Current VM name differs from historical screenshots | [Ubuntu deployment](10-ubuntu-endpoint-deployment.md) | Hyper-V VM was renamed from CORP-WS01 to MED-UBUNTU-01 after installation. Historical captions and VHDX filename remain evidence of the original setup. | Run hostnamectl to check the Linux guest hostname; do not assume the disk filename changed. |

## Documentation summary
I retained symptoms, observed outcomes and unresolved checks so the troubleshooting record can support a reproducible rebuild without overstating corrective actions.
