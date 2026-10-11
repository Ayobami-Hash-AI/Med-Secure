# Objectives and Scope

## Primary objective
Build a reproducible, isolated, multi-zone enterprise and simulated healthcare SOC lab using Microsoft Hyper-V and pfSense.

## Technical outcomes
1. Establish virtual infrastructure, document resource constraints, and deploy a perimeter firewall.
2. Create CORP, SOC, CLINICAL, and ATTACK trust zones with explicit inter-zone access rules.
3. Deploy Windows Server Active Directory/DNS and managed Windows endpoints.
4. Centralize endpoint, authentication, firewall, and network telemetry in a SIEM.
5. Execute authorized attack simulations **only inside the lab**, validate alerts, and write investigation reports.
6. Demonstrate vulnerability management, hardening, backup/restore, and recovery.
7. Maintain reproducible procedures, diagrams, configuration decisions, screenshots, and test results.

## Success criteria
- Each zone has a validated gateway, addressing plan, and documented isolation policy.
- Default-deny rules prevent unauthorized inter-zone traffic; allowed services are justified.
- Log ingestion, detections, triage, and incident reporting can be demonstrated.
- A clean rebuild/restore process is tested.
- Evidence is sanitized and recruiter-readable.

## Boundaries
Training infrastructure only. No production network targeting, patient data, real credentials, or unauthorized scanning.
