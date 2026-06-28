# Tabletop Exercise: Operation Locked Campus

**Scenario Type:** Discussion-Based Tabletop Exercise  
**Target Organisation:** National Security Training Institute (Fictional)  
**Author:** Abhishek Parmar  
**Duration:** 2–3 hours  
**Threat Simulated:** Ransomware + Data Exfiltration

---

## Background

At 9:15 AM on a Monday, IT staff at a fictional national security 
training university begin receiving reports that files across faculty 
shared drives are inaccessible. A ransom note appears on workstations 
in the Cyber Research Lab demanding payment within 48 hours. The 
university's training programme database — containing participant 
data from government-affiliated courses — may be compromised.

This scenario was developed to address the specific threat landscape 
faced by academic institutions handling sensitive government training 
data, where IR procedures often need to involve non-technical 
stakeholders and government liaison protocols.

---

## Exercise Objectives

1. Test detection and escalation procedures
2. Evaluate communication between IT, administration, and government liaison
3. Assess backup and recovery readiness
4. Identify stakeholder notification gaps
5. Practice after-action documentation

---

## Participants

| Role | Department |
|---|---|
| Incident Commander | IT Security Head |
| Scribe | Administrative Officer |
| SME – Technical | Network/Systems Admin |
| SME – Academic | Registrar's Office |
| Government Liaison | MHA Point of Contact |
| Communications | Public Affairs Officer |

---

## Timed Injects

| Time | Event |
|---|---|
| T+0 | Ransom note found on Cyber Research Lab systems |
| T+30 min | Local reporter calls asking about a university cyberattack |
| T+60 min | IT confirms backups from last 72 hours are also encrypted |
| T+90 min | Attacker emails proof: 2GB of training participant data exfiltrated |
| T+2 hrs | Government liaison requests written situation report within 60 minutes |
| T+2.5 hrs | Faculty member admits clicking a suspicious email 4 days ago |
| T+3 hrs | CERT-In requests IOC sharing for national threat intelligence |

---

## Discussion Questions

**Detection**
- Who is the first point of escalation when ransomware is detected?
- What monitoring should have caught this earlier?
- How do we confirm it is ransomware and not a storage failure?

**Communication**
- At what point do we formally notify the government liaison?
- How do we respond to media before facts are confirmed?
- Who approves external communications?

**Containment**
- Which systems do we isolate first and why?
- How do we keep critical academic operations running during lockdown?
- Do we pay the ransom? Who makes that decision?

**Recovery**
- What is our recovery time objective for core academic systems?
- How do we verify backup integrity before restoring?
- How do we confirm the attacker is fully out before going back online?

---

## After-Action Review Template

**Date of Exercise:**  
**Facilitator:**  
**Participants:**  

| Category | Notes |
|---|---|
| What went well | |
| What did not work | |
| Gaps identified | |
| Recommended fixes | |
| Owner and deadline | |

---

## Key Lessons This Scenario Is Designed to Surface

- Most universities lack a clear government notification threshold
- Backup integrity is rarely tested until it is too late
- Non-technical stakeholders (registrar, legal, comms) are often 
  excluded from IR planning despite being critical during an incident
- Media response protocols are frequently absent in academic IR plans

---

*This scenario is fictional and created for training purposes only.  
Developed during postgraduate studies in Cybersecurity & Digital  
Forensics at an MHA-affiliated institution in India.*
