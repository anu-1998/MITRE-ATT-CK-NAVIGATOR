# MITRE-ATT-CK-NAVIGATOR

MITRE ATT&CK – SOC Attack Scenario Mapping
---

This repository demonstrates a practical attack scenario mapped to the MITRE ATT&CK framework using the MITRE ATT&CK Navigator.
The project is designed to showcase how a SOC analyst can model and understand real-world attacker behavior from initial access to data exfiltration.



---
📌 Project Overview
---

The goal of this project is to:

Practice mapping attack techniques to MITRE ATT&CK

Visualize attack flow using ATT&CK Navigator

Understand how attackers move through different tactics during an intrusion

Build SOC-focused documentation suitable for learning and portfolio purposes

This is a practice / learning project, not a full APT simulation.


---

🧨 Attack Scenario Summary
---

The simulated attack follows this flow:

Phishing email with a malicious Excel attachment

User enables macros, triggering PowerShell execution

PowerShell downloads and executes a payload in memory

Persistence established using Registry Run keys

Credentials dumped from LSASS

Lateral movement using RDP

---

Sensitive data exfiltrated over HTTPS to a C2 server
---

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

🧠 About Missing MITRE ATT&CK Tactics
---

Some MITRE ATT&CK tactics such as Discovery, Defense Evasion, or Privilege Escalation are not included in this scenario.

This is intentional.

Not every attack uses all tactics

The scenario focuses on a specific attack path

Adding unused techniques would be inaccurate

This approach reflects real SOC investigations, where only observed behavior is mapped.

---

📊 MITRE ATT&CK Navigator
---

The project includes a custom ATT&CK Navigator layer (JSON) that visually represents the techniques used in this scenario.
The layer can be imported directly into the MITRE ATT&CK Navigator for review and analysis.

---

🎯 Disclaimer
--

This project is created for educational and demonstration purposes only.
It does not represent a real incident or threat actor.
---

🚀 Skills Demonstrated
---

MITRE ATT&CK framework understanding

SOC attack flow analysis

Threat modeling

Documentation and visualization

ATT&CK Navigator usage

---

📬 Feedback
---

Feedback and suggestions are welcome.
This project is part of continuous learning in cybersecurity and SOC analysis.




