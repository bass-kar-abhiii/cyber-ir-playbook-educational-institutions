# Incident Response Plan for National Security Training Institute

Author: Abhishek Parmar, parmarabhishek921@gmail.com

Revision 1.0, Released 28 June 2026

This incident response plan is adapted from the Counteractive Security
IR framework, customized for educational and government-affiliated
institutions in India. It incorporates CERT-In coordination protocols,
MHA liaison procedures, and university governance structures.

It was last reviewed on 28 June 2026. It was last tested on 28 June 2026
via tabletop exercise (Operation Locked Campus).

---

# Assess

1. **Stay calm and professional.**
2. Gather pertinent information — alarms, events, data, assumptions, intuitions (**observe**).
3. Consider impact categories below (**orient**), and determine if there is a possible incident (**decide**).
4. Initiate a response if there is an incident (**act**). If in doubt, initiate a response.

## Assess Functional Impact

What is the direct or likely impact on institution operations, staff, students, or government partners?

- Mission/operations degradation or failure: **incident!**
- None: assess information impact.

## Assess Information Impact

What is the direct or likely impact on sensitive data — student PII, research data, government training programme data, or classified materials?

- Information accessed, taken, changed, or deleted: **incident!**
- None: handle via standard IT support channels.

**Every team member is empowered to start this process. If you see something, say something.**

---

# Initiate Response

## Name the Incident

Assign a simple two-word codename to the incident for use in files and communication channels.
Example: *Locked Campus*, *Silent Hawk*, *Dark Archive*

## Assemble the Response Team

1. Page the on-duty Incident Commander — IT Security Head
2. Do not discuss the incident outside the response team until cleared by the Incident Commander
3. Launch response chat on Microsoft Teams — IR Channel
4. Launch response call via Internal IR Hotline
5. Prefer voice call and secure file exchange over all other methods
6. Do not use primary institutional email if possible. Use ap118303@gmail.com as alternate.
   Encrypt emails for any participant outside nsti.gov.in domain
7. Do not use SMS/WhatsApp to discuss the incident unless directing someone to a secure channel
8. Invite the following to the response call:
   - Cybersecurity Team and Forensics Analyst
   - Faculty IT Leads and Academic Department Heads as SMEs
   - Vice Chancellor, Registrar, and MHA Liaison at earliest opportunity

### Response Team Structure

- **Command Team:** Incident Commander, Deputy IC, Scribe
- **Liaison Team:** Internal Liaison, MHA Government Liaison
- **Operations Team:** IT Security SMEs, Faculty SMEs, Legal and Compliance

### Response Team Contacts

| Role | Contact |
|---|---|
| Incident Commander | IT Security Head — Direct Line |
| Deputy IC | Network Administrator |
| Security Team | Cybersecurity Team, Forensics Analyst |
| Faculty SMEs | Faculty IT Leads, Department Heads |
| Executive | Vice Chancellor, Registrar |
| Government | MHA Liaison |

## Establish Battle Rhythm

### Initial Response Call Structure

- **IC:** My name is [NAME], I am the Incident Commander. [NAME] is Deputy, [NAME] is Scribe. Who is on the call?
- **Scribe:** Takes attendance
- **IC:** [If missing key personnel] Deputy, please page [NAME]
- **IC:** [Asks questions to understand situation, scope, vector, impact, timeline]
- **SMEs:** Brief answers
- **IC:** [If incident confirmed] Investigation led by [NAME], Remediation by [NAME], Communications by [NAME]. We reconvene every 2 hours.
- **IC:** [If not an incident] Facts do not rise to incident level. I will coordinate directly with the reporter.

### Call Etiquette

- Join both call and chat
- Keep microphone muted until speaking
- Identify yourself and your role when joining
- Be direct and factual — no speculation
- Use plain language, avoid unnecessary acronyms

### Update Calls

- Conduct update calls every **2 hours** on the active bridge
- Adjust frequency based on severity
- Coordinate separate updates for MHA liaison and executive team as needed

---

# Investigate

**Investigate, remediate, and communicate in parallel using separate teams where possible.**

## Create Incident File

1. Create incident file on Secure SharePoint / Encrypted Network Drive using the incident codename
2. Document functional and information impact
3. Document the attack vector — web, email, removable media, insider, etc.
4. Document incident summary — vector, impact, investigation status, remediation status
5. Document timeline — attacker activity and responder activity
6. Track the following throughout:
   - **Evidence** — time of collection, source, chain of custody
   - **Affected systems** — how identified, summary of effect
   - **Files of interest** — malware or sensitive data files
   - **Accessed or exfiltrated data** — filenames, metadata, time of exposure
   - **Significant attacker activity** — logins, malware execution, lateral movement
   - **Network IOCs** — IP addresses, domains, PCAP patterns
   - **Host IOCs** — filenames, hashes, registry keys
   - **Compromised accounts** — scope of access, time of compromise

## Response Resources

| Resource | Location |
|---|---|
| Critical information list | Classified — CISO Office |
| Critical asset list | IT Asset Management System |
| Asset management database | Internal CMDB — IT Department |
| Network map | IT Infrastructure Team — Secure Drive |
| SIEM console | Internal SIEM Dashboard |
| Log aggregator | Centralized Log Management System |

## Investigative Plan

1. Review and refine incident impact
2. Review and refine attack vector
3. Build timeline with facts and inferences
4. Create hypotheses — what happened, with what confidence
5. Identify key questions using MITRE ATT&CK framework:

| Attacker Tactic | What attackers do | Key Questions |
|---|---|---|
| Reconnaissance | Learn about targets | How? Since when? Which systems? |
| Initial Access | Get in | How? When? Which entry point? |
| Execution | Run hostile code | What malware? Which tools? |
| Persistence | Stay in the system | How? Since when? Where? |
| Privilege Escalation | Get higher access | How? Which accounts? |
| Defense Evasion | Dodge detection | How? Since when? |
| Credential Access | Steal accounts | Which accounts? When? |
| Lateral Movement | Move across network | How? When? Which systems? |
| Exfiltration | Take data | What data? How? When? |
| Impact | Break or encrypt | Which systems? How severe? |

See [MITRE ATT&CK](https://attack.mitre.org/) for full framework.

## Collect Evidence

- Collect live response data using **Volatility Framework and Wireshark**
- Collect logs from affected systems, SIEM, and network devices
- Collect memory image using **Volatility Framework / WinPmem**
- Collect disk image using **FTK Imager / dd**
- Maintain chain of custody for all evidence collected

### Useful Artifacts to Collect

- Running processes and services
- Executable hashes
- Installed applications
- Local and domain user accounts
- Listening ports and associated services
- DNS resolution settings and static routes
- Established and recent network connections
- Scheduled tasks and cron jobs
- Event logs
- Anti-virus detections
- Binaries in temporary storage
- Remote access activity — RDP, VPN, SSH
- Web traffic — HTTP/HTTPS
- Packet captures via Wireshark

## Analyze Evidence

- Analyze live response data
- Conduct memory forensics using Volatility Framework
- Analyze disk images using FTK Imager
- Analyze malware samples
- Document new IOCs
- Update case file

### Indicators to Watch

- Unusual authentication — frequency, time of day, remote location
- Non-standard usernames
- Unsigned binaries connecting to network
- Beaconing or large data transfers
- PowerShell with Base64-encoded commands
- Excessive compression activity — RAR, 7zip — with suspicious filenames
- Connections on previously unused ports
- Changes to routing tables or DNS settings

---

# Remediate

**Investigate, remediate, and communicate in parallel.**

## Remediation Strategy

Review incident file, applicable playbooks, and MITRE ATT&CK tactics in play.
Develop remediations across four categories:

### Protect
- Patch applications and operating systems
- Update IPS and anti-virus signatures
- Enable multi-factor authentication
- Strengthen password policy
- Reduce privileged accounts
- Block unused ports at network boundaries

### Detect
- Enhance logging on critical systems
- Enhance application logging
- Improve log aggregation
- Update IDS signatures with new IOCs

### Contain
- Implement ACLs at network segment boundaries
- Disable or remove compromised accounts
- Block malicious IPs and domains
- Remove compromised systems from network
- Contact CERT-In for coordination support

### Eradicate
- Rebuild compromised systems from known-good state
- Reset all affected account passwords
- Remove malware and hostile credentials
- Migrate to alternate services if required

## Remediation Timing

- **Immediate** — when ongoing data loss, mission failure, or active threat requires stopping attacker now
- **Delayed** — when investigation must complete first, or alerting attacker would be harmful
- **Combined** — when both apply, e.g. isolate one system immediately while investigating others

---

# Communicate

**All communication must be accurate. Do not speculate.**

## Internal Communication

- Update stakeholders every 2 hours via call and Teams chat
- Notify MHA Liaison as soon as government data is confirmed affected
- Do not notify non-response staff until cleared by Incident Commander

### Incident Report

- Distribute final incident report to: CISO, MHA Liaison, University Registrar, Vice Chancellor
- Use template at `/templates/incident-report-template.md`

## External Communication

### Notify Regulators
- Coordinate with Internal GRC Team on regulatory notification requirements
- For cyber incidents affecting government data, notify CERT-In at https://www.cert-in.org.in

### Media Response
- Do not comment to media until Incident Commander and Public Affairs Office approve messaging
- Do not use platitudes — focus on facts
- Be honest, accept responsibility, present the plan to prevent recurrence

### Law Enforcement
- Coordinate with Vice Chancellor Office and University Legal Counsel before engaging law enforcement
- Contact Local Cyber Crime Cell
- Contact CERT-In for national-level coordination

### Share Threat Intelligence
- Share IOCs with CERT-In Coordination Portal after incident closure
- Coordinate with NCIIPC if critical infrastructure is involved

---

# Recover

**Recovery is coordinated by business units and system owners in collaboration with IT.**

1. Activate business continuity plan if required
2. Verify backup integrity before restoring any system
3. Confirm attacker is fully eradicated before bringing systems back online
4. Restore systems in priority order — critical academic and government systems first
5. Document all recovery actions with timestamps
6. Integrate recovery actions with institutional continuity procedures

---

*Adapted from the Counteractive Security IR framework (Apache License 2.0).
Customized for educational and government-affiliated institution context by Abhishek Parmar.*
