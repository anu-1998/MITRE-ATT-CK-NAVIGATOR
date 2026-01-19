# MITRE ATT&CK – SOC Attack Scenario Mapping

## 📌 Project Overview

This project demonstrates a practical attack scenario mapped to the MITRE ATT&CK framework using the MITRE ATT&CK Navigator. The objective is to model realistic attacker behavior and visualize how a Security Operations Center (SOC) analyst would track an intrusion from initial access to data exfiltration.

This is a learning and portfolio project designed to strengthen understanding of attacker tradecraft, ATT&CK tactics and techniques, and SOC-style documentation.

---

## 🎯 Project Goals

* Practice mapping real-world attack behavior to MITRE ATT&CK
* Visualize attacker progression using ATT&CK Navigator layers
* Understand tactic-to-technique relationships
* Create SOC-focused documentation suitable for incident analysis
* Demonstrate ATT&CK framework proficiency for portfolio purposes

---

## 🧨 Attack Scenario Summary

The simulated intrusion follows this attack path:

1. **Initial Access**
   Phishing email with a malicious Excel attachment

2. **Execution**
   User enables macros, triggering PowerShell execution

3. **Command and Control**
   PowerShell downloads and executes a payload in memory

4. **Persistence**
   Registry Run keys are created to maintain access

5. **Credential Access**
   Credentials are dumped from LSASS memory

6. **Lateral Movement**
   Attacker moves laterally using Remote Desktop Protocol (RDP)

7. **Exfiltration**
   Sensitive data is exfiltrated over HTTPS to a C2 server

---

## 🧩 MITRE ATT&CK Mapping

| Tactic              | Technique                                     | ID        |
| ------------------- | --------------------------------------------- | --------- |
| Initial Access      | Phishing: Attachment                          | T1566.001 |
| Execution           | Command and Scripting Interpreter: PowerShell | T1059.001 |
| Command and Control | Ingress Tool Transfer                         | T1105     |
| Persistence         | Registry Run Keys / Startup Folder            | T1547.001 |
| Credential Access   | OS Credential Dumping: LSASS Memory           | T1003.001 |
| Lateral Movement    | Remote Services: RDP                          | T1021.001 |
| Exfiltration        | Exfiltration Over C2 Channel                  | T1041     |

---

## 🧠 About Missing MITRE ATT&CK Tactics

Some MITRE ATT&CK tactics such as:

* Discovery
* Defense Evasion
* Privilege Escalation

are not included in this scenario.

This is intentional.

* Not every attack uses every tactic
* Only observed behavior should be mapped
* Adding unused techniques would reduce accuracy

This approach reflects real SOC investigations where analysts map only confirmed attacker activity.

---

## 📊 MITRE ATT&CK Navigator

This repository includes a custom MITRE ATT&CK Navigator layer that visually represents the techniques used in this scenario.

You can import the layer directly into the MITRE ATT&CK Navigator to review and analyze the attack flow.

---

## 🚀 Skills Demonstrated

* MITRE ATT&CK framework understanding
* SOC attack flow analysis
* Threat modeling
* Incident documentation
* ATT&CK Navigator usage
* Analytical thinking

---

## ⚠ Disclaimer

This project is created strictly for educational and demonstration purposes.
It does not represent a real incident or threat actor.

---

## 📬 Feedback

Feedback and suggestions are welcome.
This project is part of continuous learning in cybersecurity and SOC analysis.
