# Build Journal — Phase 1

## 1. Host discovery
Collected PowerShell Get-ComputerInfo, Get-CimInstance Win32_Processor, and Get-Volume outputs. Confirmed Intel N95 (4C/4T), approximately 32 GB RAM, NVMe disk capacity, and Windows virtualization state. Initial virtualization-firmware reporting was inconsistent with Task Manager; later Task Manager confirmed firmware virtualization enabled. systeminfo reported a hypervisor detected and virtualization-based security running.

## 2. Hypervisor selection
Evaluated VMware/VirtualBox coexistence with Windows virtualization features. Chose Microsoft Hyper-V as the primary lab hypervisor. Verified Hyper-V management cmdlets and initial Default Switch. Created four private switches: MED-CORP-SW, MED-SOC-SW, MED-CLINICAL-SW, MED-ATTACK-SW.

## 3. Firewall provisioning
Created Generation 2 VM FW01, disabled Secure Boot for the installer, attached a 20 GB virtual disk and installation ISO, and added five network adapters (Default Switch + four private switches). Verified with Get-VMNetworkAdapter.

## 4. Stable MAC-to-zone identification
Used Set-VMNetworkAdapter -StaticMacAddress, selecting each adapter by SwitchName. Assigned ...01 WAN, ...02 CORP, ...03 SOC, ...04 CLINICAL, ...05 ATTACK. Re-ran Get-VMNetworkAdapter and verified all five assignments.

## 5. Installer media troubleshooting
First startup failed with Synthetic SCSI Controller/DVD attachment error: 'The file or directory is corrupted and unreadable'. The ISO path was inside iCloud Drive. Recommended copying/re-downloading to local C:\Hyper-V\ISO, validating readability, and reattaching. A subsequent screenshot confirmed successful installer boot. The exact corrective action taken was not independently recorded; do not claim a hash comparison was completed.

## 6. pfSense installation
- Booted Netgate Installer v1.2.
- Selected WAN hn0 by MAC ...01; DHCP client, VLAN tagging off, local resolver off.
- Selected LAN hn4 by MAC ...02; planned static 10.10.10.1/24 and DHCP range 10.10.10.100–199.
- Confirmed WAN/LAN assignments.
- Selected pfSense CE (no Plus subscription).
- Selected ZFS, GPT, single-disk stripe.
- Confirmed selected da0 20G Microsoft Virtual Disk and approved overwrite.
- Selected pfSense CE 2.8.1.

## 7. Initial boot validation
Console displayed 'Bootup complete', pfSense 2.8.1-RELEASE amd64, WAN hn0 with DHCP 172.21.139.31/20, and LAN hn4 with 10.10.10.1/24. This verifies installation and initial two-interface addressing; it does **not** yet verify outbound internet reachability, DHCP client leasing on CORP, or remaining zone interfaces.

## 8. Pending baseline
Detach ISO; reboot from VHDX; verify WAN DNS/internet and CORP DHCP; export configuration and create a rollback point. Assign remaining interfaces and validate policy.

## Evidence
See [Evidence register](04-evidence-register.md). Screenshots must be sanitized before publication.
