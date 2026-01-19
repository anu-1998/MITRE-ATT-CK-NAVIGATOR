# SOC Incident Report – MITRE ATT&CK Attack Scenario Mapping

## Incident Overview

This report documents a simulated cyber intrusion mapped to the MITRE ATT&CK framework. The purpose of this exercise is to demonstrate how a SOC analyst investigates attacker behavior, correlates activity with ATT&CK techniques, and understands the full intrusion lifecycle.

This is a learning and portfolio project.

---

## Attack Timeline

| Phase             | Description                                    |
| ----------------- | ---------------------------------------------- |
| Initial Access    | Phishing email with malicious Excel attachment |
| Execution         | User enables macros, triggering PowerShell     |
| Command & Control | Payload downloaded and executed in memory      |
| Persistence       | Registry Run keys created                      |
| Credential Access | LSASS memory credential dumping                |
| Lateral Movement  | RDP used to access another system              |
| Exfiltration      | Data exfiltrated over HTTPS                    |

---

## MITRE ATT&CK Mapping and Justification

| Tactic            | Technique             | ID        | Reason                                 |
| ----------------- | --------------------- | --------- | -------------------------------------- |
| Initial Access    | Phishing: Attachment  | T1566.001 | User opened malicious Excel attachment |
| Execution         | PowerShell            | T1059.001 | Macro executed PowerShell commands     |
| Command & Control | Ingress Tool Transfer | T1105     | Payload retrieved from remote server   |
| Persistence       | Registry Run Keys     | T1547.001 | Registry used to maintain persistence  |
| Credential Access | LSASS Memory          | T1003.001 | Credentials extracted from LSASS       |
| Lateral Movement  | RDP                   | T1021.001 | Attacker accessed another system       |
| Exfiltration      | Exfiltration Over C2  | T1041     | Data sent over HTTPS                   |

---

## Detection Opportunities

| Phase             | Log Source       | Detection Idea                      |
| ----------------- | ---------------- | ----------------------------------- |
| Phishing          | Email Gateway    | Attachment with macro-enabled Excel |
| Execution         | Endpoint Logs    | PowerShell spawned by Excel         |
| C2                | Proxy / Firewall | Outbound HTTPS to unknown domain    |
| Persistence       | Registry Logs    | Run key modification                |
| Credential Access | Sysmon / EDR     | LSASS access by non-system process  |
| Lateral Movement  | Windows Logs     | RDP login from abnormal host        |
| Exfiltration      | Network Logs     | Large HTTPS data transfer           |

---

## SOC Response Actions

1. Isolate infected endpoint
2. Reset compromised credentials
3. Block C2 domain/IP
4. Remove persistence mechanisms
5. Review lateral movement scope
6. Perform endpoint forensic analysis
7. Notify incident response team

---

## Lessons Learned

* Phishing remains a primary initial access vector.
* Macro execution combined with PowerShell is highly dangerous.
* Credential dumping leads directly to lateral movement.
* Encrypted exfiltration hides data theft effectively.
* Early detection significantly reduces impact.

---

## MITRE ATT&CK Navigator

A custom ATT&CK Navigator layer was created to visualize the techniques used in this scenario. This visual mapping supports SOC analysis and reporting.

---

## Disclaimer

This scenario is fictional and created strictly for educational and portfolio purposes.

---

## Author Notes

This project was created through self-study, documentation review, and hands-on experimentation to improve SOC and MITRE ATT&CK understanding.
