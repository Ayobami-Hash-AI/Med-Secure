# Ubuntu Endpoint Deployment — October 11, 2026

## Milestone: installed and booted

I deployed **Ubuntu Desktop 24.04.5 LTS** in Microsoft Hyper-V as the Linux management and security-testing endpoint for MedSecure SOC. The VM was initially named `CORP-WS01` and was renamed to **`MED-UBUNTU-01`** in Hyper-V.

### Observed configuration
| Component | Evidence-based state |
|---|---|
| Hypervisor | Microsoft Hyper-V on host GHOST |
| Hyper-V VM | MED-UBUNTU-01 (formerly CORP-WS01) |
| Operating system | Ubuntu Desktop 24.04.5 LTS |
| Virtual network | MED-CORP-SW (private CORP switch) |
| Resources | 4096 MB RAM, 2 virtual processors (Hyper-V settings screenshot) |
| Installer | Default application selection; optional third-party drivers/media codecs not selected |
| Disk installation | Automatic erase/install option selected for VM virtual disk |
| Login | Local user `medsecureadmin`; password required; Active Directory option not selected |
| Installation medium | Hyper-V DVD Drive set to **None** following installation |
| Boot status | Ubuntu login screen and desktop shown; VM running |

### Verification boundaries
The screenshots verify installation completion, login-screen availability, desktop access, VM rename, and detached ISO. They **do not yet verify** the guest OS hostname, network IP, DHCP, routing, DNS, internet access, pfSense GUI reachability, hardening, or SIEM forwarding. The Hyper-V VM display name is not necessarily the Linux guest hostname.

### Next session — one step at a time
1. Open Ubuntu terminal and run `hostnamectl` to confirm the guest hostname and OS.
2. Run `ip -br a` and `ip route` to inspect CORP networking.
3. Test reachability to pfSense CORP gateway `10.10.10.1`; troubleshoot DHCP/policy if needed.
4. Apply updates after confirming network access; then plan hardening, audit logging and SOC telemetry.
5. Capture sanitized screenshots and update verification evidence.

### Portfolio summary (first person)
I installed and booted Ubuntu 24.04.5 LTS in Hyper-V, renamed the VM MED-UBUNTU-01, disconnected installation media, and verified access to the Ubuntu desktop. I am preparing the endpoint for controlled network connectivity, Linux security hardening and integration with the MedSecure SOC monitoring environment.

## Published screenshot evidence

Nine installation and boot screenshots are committed below. The VM creation, Secure Boot and VHDX setup screenshots are already published under `evidence/phase-02/03-management-workstation/`.

### P2-18 — Installer network selection (connectivity not yet verified)

![Installer network selection (connectivity not yet verified)](../evidence/phase-02/04-ubuntu-deployment/18-ubuntu-network-selection.png)

### P2-19 — Default application selection

![Default application selection](../evidence/phase-02/04-ubuntu-deployment/19-ubuntu-default-applications.png)

### P2-20 — Optional third-party software left unchecked

![Optional third-party software left unchecked](../evidence/phase-02/04-ubuntu-deployment/20-ubuntu-optional-software.png)

### P2-21 — Automatic installation on the VM virtual disk

![Automatic installation on the VM virtual disk](../evidence/phase-02/04-ubuntu-deployment/21-ubuntu-virtual-disk-installation.png)

### P2-22 — Account options before account details were entered

![Account options before account details were entered](../evidence/phase-02/04-ubuntu-deployment/22-ubuntu-account-options.png)

### P2-23 — Ubuntu 24.04.5 LTS installation complete

![Ubuntu 24.04.5 LTS installation complete](../evidence/phase-02/04-ubuntu-deployment/23-ubuntu-installation-complete.png)

### P2-24 — Installation ISO detached: DVD drive set to None

![Installation ISO detached: DVD drive set to None](../evidence/phase-02/04-ubuntu-deployment/24-ubuntu-iso-detached.png)

### P2-25 — MED-UBUNTU-01 login screen

![MED-UBUNTU-01 login screen](../evidence/phase-02/04-ubuntu-deployment/25-med-ubuntu-01-login.png)

### P2-26 — MED-UBUNTU-01 Ubuntu desktop

![MED-UBUNTU-01 Ubuntu desktop](../evidence/phase-02/04-ubuntu-deployment/26-med-ubuntu-01-desktop.png)

