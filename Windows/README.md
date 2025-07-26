# 📂 log-analys

A **professional SOC log repository** for Blue Team analysts, threat hunters, and cybersecurity learners.

This repo contains **realistic Windows event logs**, organized to help you:
- Understand Windows Security Event IDs
- Build detection rules in SIEM tools (Splunk, Sentinel, ELK)
- Practice threat hunting
- Study real-world attacker tactics mapped to MITRE ATT&CK

---

## 📚 What I Learned

✅ **Windows Event ID Mastery**
- Deep understanding of common Windows Security Event IDs: 4624, 4625, 4768, 4769, 4771, 4720, 4722, 4723, 4724, 4728, 4688, 4672, 4673, 4674, 4698, 7045, 4657, 5140, 5156.
- Analyzed how each log’s fields (Logon Type, Authentication Package, Source IP, Process, Command Line) reveal attacker behavior.

✅ **Attack Chains & Detection**
- Mapped event chains: brute force (4625 → 4624), Kerberos abuse (4768/4769/4771), lateral movement (RDP, PsExec, WMI), persistence (scheduled tasks, services, registry keys), privilege escalation (4672 → 4673 → 4674).
- Learned how attackers link events to pivot deeper into a network.
- Built example detections: repeated failed logons, unusual admin logins, suspicious PowerShell encoded commands.

✅ **Real Attacker Tactics**
- Studied Golden Ticket, Silver Ticket, Pass-the-Ticket, Kerberoasting.
- Learned edge cases (forged TGT/TGS) and why basic IP checks fail.
- Learned practical SOC defense strategies: detection, correlation, blocking, automation logic.

✅ **Defensive Playbooks**
- Designed sample Python logic to auto-detect brute force by tracking multiple 4625 events from same IP.
- Planned blocking suspicious admin logons by cross-checking usernames, IP ranges, and logon types.
- Combined manual SOC investigation with automation (firewall block + account disable).

✅ **Professional Logging Repo**
- Structured logs in folders by tactic: authentication, privilege escalation, persistence, lateral movement, network access, process execution, account manipulation, kerberos-attacks.
- Wrote clear, realistic JSON examples to help any SOC analyst understand and practice detection.

---

## 🗂️ Folders

| Folder | Purpose |
|--------|---------|
| **account-management/** | New user creation, account enable, password resets, admin group changes |
| **authentication/** | Logon success, failures, Kerberos TGT/TGS activity |
| **kerberos-attacks/** | Golden Ticket, Silver Ticket, Pass-the-Ticket, Kerberoasting |
| **lateral-movement/** | RDP, PsExec, WMI execution — attacker pivot techniques |
| **network-access/** | File share access, allowed network connections, file exfiltration |
| **persistence/** | Scheduled tasks, services, registry autorun keys |
| **privilege-escalation/** | Sensitive privilege assignments and use |
| **process-execution/** | Suspicious PowerShell, Mimikatz, malicious services |

---

## ⚙️ How To Use

1. Study the logs to understand each attack.
2. Simulate scenarios in a lab SIEM (Splunk, Sentinel, ELK).
3. Build detection queries and automation playbooks.
4. Share with teammates to practice SOC workflows.

---

**🛡️ This repo is my proof of practical Blue Team knowledge — ready for real-world defense.**

**Stay sharp — happy hunting!**
