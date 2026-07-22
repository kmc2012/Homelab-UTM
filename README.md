# SOC L1 Homelab Using UTM on Apple Silicon

## Overview

This project documents a lightweight SOC L1 homelab built on a MacBook Air M1 using UTM. The lab simulates common day-to-day SOC analyst tasks, including alert triage, endpoint monitoring, brute-force investigation, file integrity monitoring, firewall response, vulnerability review, and incident documentation.

## Hardware

| Component | Specification |
|---|---|
| Host | MacBook Air M1 |
| RAM | 8 GB |
| Internal storage | 512 GB |
| External lab partition | 200 GB |
| Hypervisor | UTM |

## Lab Architecture

| VM | Purpose |
|---|---|
| SOC-SIEM | Wazuh manager and dashboard |
| Linux-Endpoint | Monitored Linux endpoint |
| Windows-Endpoint | Monitored Windows endpoint with Sysmon |
| Attacker-Box | Attack simulation machine |

See [architecture/lab-design.md](architecture/lab-design.md) and [architecture/network-diagram.md](architecture/network-diagram.md) for full diagrams.

## Skills Demonstrated

- SIEM deployment and agent onboarding
- Linux endpoint monitoring
- Windows endpoint monitoring with Sysmon
- SSH brute-force triage
- RDP brute-force triage
- Port scan investigation
- File integrity monitoring
- Suspicious PowerShell analysis
- Windows Defender alert handling
- Linux account monitoring
- Firewall containment with UFW
- Vulnerability review
- Phishing analysis
- Incident report writing

## Lab Network

All VMs use UTM Shared Network on 192.168.64.0/24.

## Projects

### Setup Guides

| Guide | Description |
|---|---|
| [01-utm-setup](setup-guides/01-utm-setup.md) | UTM install and VM creation |
| [02-soc-siem-wazuh](setup-guides/02-soc-siem-wazuh.md) | Wazuh SIEM deployment |
| [03-linux-endpoint](setup-guides/03-linux-endpoint.md) | Linux endpoint and agent |
| [04-attacker-box](setup-guides/04-attacker-box.md) | Attacker simulation VM |
| [05-windows-endpoint](setup-guides/05-windows-endpoint.md) | Windows endpoint with Sysmon |

### Detections

| Detection | Source |
|---|---|
| [SSH Brute-Force](detections/ssh-bruteforce.md) | Linux auth logs |
| [Port Scan](detections/port-scan.md) | Network activity |
| [File Integrity Monitoring](detections/file-integrity-monitoring.md) | Wazuh FIM |
| [Suspicious User Creation](detections/suspicious-user-creation.md) | Linux account logs |
| [Malware Test File (EICAR)](detections/malware-test-eicar.md) | ClamAV / Defender |
| [Suspicious PowerShell](detections/powershell-suspicious.md) | PowerShell Event ID 4104 |
| [RDP Brute-Force](detections/rdp-bruteforce.md) | Windows Security Event ID 4625 |
| [Windows Defender Alerts](detections/windows-defender.md) | Defender Operational log |

### Incident Reports

| Report | Description |
|---|---|
| [IR-001](incident-reports/IR-001-ssh-bruteforce.md) | SSH brute-force investigation |
| [IR-002](incident-reports/IR-002-port-scan.md) | Port scan investigation |
| [IR-003](incident-reports/IR-003-firewall-containment.md) | UFW containment response |
| [IR-004](incident-reports/IR-004-suspicious-user.md) | Suspicious user creation |
| [IR-005](incident-reports/IR-005-file-modification.md) | File modification investigation |
| [IR-006](incident-reports/IR-006-eicar-test.md) | EICAR test on Linux |
| [IR-007](incident-reports/IR-007-rdp-bruteforce.md) | RDP brute-force investigation |
| [IR-008](incident-reports/IR-008-powershell.md) | Suspicious PowerShell investigation |
| [IR-009](incident-reports/IR-009-defender-alert.md) | Windows Defender alert response |

### Other Sections

| Section | Description |
|---|---|
| [Vulnerability Management](vulnerability-management/linux-vulnerability-review.md) | CVE review and patching |
| [Phishing Analysis](phishing-analysis/sample-001.md) | Email triage example |
| [Capstone](capstone/full-investigation.md) | Multi-stage investigation |
| [Lessons Learned](lessons-learned/troubleshooting.md) | Troubleshooting notes |

## Disclaimer

This homelab is for educational and defensive cybersecurity training only. All simulated attacks were performed in an isolated lab environment.

