# Cyber Incident Response Playbook
### Adapted for Educational & Government-Affiliated Institutions

**Author:** Abhishek Parmar  
**Background:** Cybersecurity & Digital Forensics, India

---

## Why I Built This

Most IR frameworks assume a corporate environment — dedicated 
SOC teams, cyber insurance, and commercial SIEM tools. 
Universities and government training institutions are different. 
They handle sensitive research, national security programme data, 
and student PII, but often with leaner IT teams and less mature 
incident response processes.

During my postgraduate studies in Cybersecurity & Digital Forensics 
at an MHA-affiliated institution, I noticed this gap firsthand. 
This playbook adapts the Counteractive Security IR framework 
for that specific context — replacing corporate assumptions with 
references relevant to Indian academic and government institutions, 
including CERT-In coordination, MHA liaison protocols, and 
university governance structures.

---

## What's Inside

| File/Folder | Purpose |
|---|---|
| `during.md` | Core IR lifecycle — Assess, Investigate, Remediate, Communicate |
| `after.md` | Post-incident review and lessons learned |
| `playbooks/` | Threat-specific playbooks (ransomware, phishing, unauthorized access) |
| `roles/` | Role definitions — Incident Commander, Scribe, SME |
| `tabletop-exercise/` | University ransomware scenario for training exercises |

---

## Tabletop Exercise Included

**"Operation Locked Campus"** — a ransomware tabletop scenario 
built around a fictional national security training university. 
Includes timed injects, discussion questions by response phase, 
and an after-action review template.

Designed to be run with non-technical stakeholders including 
administrative staff, faculty leads, and government liaisons — 
not just IT teams.

See [`tabletop-exercise/university-ransomware-scenario.md`](./tabletop-exercise/university-ransomware-scenario.md)

---

## Tools Referenced

- Volatility Framework — Memory Forensics
- Wireshark — Packet Analysis  
- FTK Imager — Disk Imaging
- CERT-In — India's national IR coordination body
- NCIIPC — Critical infrastructure protection

## Frameworks Referenced

- NIST SP 800-61r2 — Incident Handling Guide
- MITRE ATT&CK — Adversary tactics and techniques
- ISO 27001 — Information security awareness
- CERT-In Guidelines — India-specific IR coordination

---

*Based on the open-source template by Counteractive Security  
(Apache License 2.0). Customized for educational institution context.*
