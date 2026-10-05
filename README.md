<!-- ===================== HEADER ===================== -->
<div align="center">

# 🛡️ Cybersecurity Fundamentals Portfolio

### Incident Response · Network Attack Analysis · Risk Management · Access Control · Security Architecture

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=NIST+CSF+%26+Risk+Assessment+Frameworks;Packet+Analysis+%26+Network+Attack+Detection;Access+Control+%26+Privacy+Audits;Secure+Network+%26+Infrastructure+Design" alt="Typing SVG" />

<br/>

![Focus](https://img.shields.io/badge/Focus-Cybersecurity%20Fundamentals-0EA5E9?style=for-the-badge&logo=shield&logoColor=white&labelColor=0D1117)
![Frameworks](https://img.shields.io/badge/Frameworks-NIST%20%7C%20MITRE%20ATT%26CK-1E90FF?style=for-the-badge&logo=target&logoColor=white&labelColor=0D1117)
![Write-ups](https://img.shields.io/badge/Write--ups-11-38BDF8?style=for-the-badge&logo=gitbook&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Actively%20Growing-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

</div>

---

<!-- ===================== ABOUT ===================== -->
## 👋 About This Repository

This repository is a collection of my cybersecurity fundamentals work: incident response, network attack analysis, risk assessments, access control audits, and security architecture design.

My work pairs **hands-on analysis** (packet capture review, access log review, phishing and malware escalation, vulnerability assessment) with **governance frameworks** (NIST CSF, NIST SP 800-30, NIST SP 800-53, least privilege audits, risk registers) to protect organizational assets and keep operations resilient.

> 💡 **Reading tip:** each write-up follows a similar layout: case summary, scenario, findings or design, recommendations, and skills demonstrated.

---

<!-- ===================== AT A GLANCE ===================== -->
## 📌 At a Glance

| 🧪 Write-ups | 🧩 Domains | 🛡️ Frameworks Used |
| :---: | :---: | :---: |
| **11** | **5** | **NIST CSF, NIST SP 800-30, NIST SP 800-53 (AC-6), MITRE ATT&CK** |

---

<!-- ===================== PROJECT INDEX ===================== -->
## 📂 Project Index

### 🌐 Network Attack Analysis & Hardening

| Project | Category | Core Focus & Skills Demonstrated |
| :--- | :--- | :--- |
| [**Analyze Network Attacks: SYN Flood DoS**](./Analyze%20Network%20Attacks%20-%20SYN%20Flood%20DoS.md) | Network Attack Analysis | Reading a packet capture, identifying a TCP SYN flood from half-open connections, explaining how it exhausts web server resources, and containing it at the firewall. |
| [**Apply OS Hardening Techniques: Brute Force & Malware Redirect Incident**](./Apply%20OS%20Hardening%20Techniques%20-%20Brute%20Force%20%26%20Malware%20Redirect%20Incident.md) | Incident Documentation / Hardening | Documenting a brute force attack on a default admin password, tracing the DNS and HTTP redirect to a malware site with tcpdump, and recommending 2FA and password controls. |
| [**Cybersecurity Incident Report: Network Traffic Analysis**](./Cybersecurity%20Incident%20Report%20-%20Network%20Traffic%20Analysis.md) | Network Traffic Analysis | Analyzing a tcpdump log showing "udp port 53 unreachable", identifying the affected DNS, UDP, and ICMP protocols, and listing likely causes. |

### 🧯 Incident Response & SOC Operations

| Project | Category | Core Focus & Skills Demonstrated |
| :--- | :--- | :--- |
| [**SOC Level 1 Incident Report: Phishing & Malware Escalation**](./SOC%20Level%201%20Incident%20Report%20%E2%80%94%20Phishing%20%26%20Malware%20Escalation.md) | SOC Operations & Triage | Following a phishing playbook, identifying red flags in a suspicious email, verifying a malicious attachment hash, and escalating the ticket to Level 2. |
| [**NIST CSF Incident Response & ICMP Flood Mitigation Plan**](./NIST%20CSF%20Incident%20Response%20%26%20ICMP%20Flood%20Mitigation%20Plan.md) | Incident Response / Network Defense | Mapping an ICMP flood (DoS) across the 5 NIST CSF functions, with firewall rate limiting, IDS/IPS rules, and a recovery sequence. |

### 🔑 Identity, Access & Privacy

| Project | Category | Core Focus & Skills Demonstrated |
| :--- | :--- | :--- |
| [**Access Controls Investigation & Incident Analysis**](./Access%20Controls%20Investigation%20%26%20Incident%20Analysis.md) | Identity & Access Management (IAM) | Investigating an unauthorized payroll event caused by a stale contractor admin account, and recommending account expiry, limited contractor access, and MFA. |
| [**Information Privacy Audit & Least Privilege Analysis**](./Information%20Privacy%20Audit%20%26%20Least%20Privilege%20Analysis.md) | GRC & Data Privacy | Auditing a data leak through shared folder links, mapping it to NIST SP 800-53 AC-6, and enforcing least privilege. |

### 📊 Governance, Risk & Compliance (GRC)

| Project | Category | Core Focus & Skills Demonstrated |
| :--- | :--- | :--- |
| [**Risk Assessment & Risk Register**](./Risk%20Assessment%20%26%20Risk%20Register.md) | Governance, Risk & Compliance | Scoring likelihood and severity for a commercial bank, ranking risks by priority, and planning mitigations. |
| [**Vulnerability Assessment Report**](./Vulnerability%20Assessment%20Report.md) | Vulnerability Management | Assessing a publicly exposed database server using NIST SP 800-30 and defining a remediation strategy. |
| [**Home Network Asset Inventory**](./Home%20Network%20Asset%20Inventory.md) | Asset Management | Mapping and classifying network devices by owner, location, and sensitivity to focus protection. |

### 🏗️ Security Architecture

| Project | Category | Core Focus & Skills Demonstrated |
| :--- | :--- | :--- |
| [**Security Infrastructure Design Document**](./Security%20Infrastructure%20Design%20Document.md) | Security Architecture | Designing authentication, firewall rules, VPN, 802.1X wireless, VLAN segmentation, endpoint hardening, and IDS/IPS for a 50-person company. |

---

<!-- ===================== COMPETENCIES ===================== -->
## 🎯 Core Competencies

| Domain | What I Do | Evidence |
| :--- | :--- | :--- |
| 🌐 **Network Attack Analysis** | Read tcpdump and packet capture logs, identify attacks such as SYN floods, trace DNS, TCP, UDP, ICMP, and HTTP behavior, and explain how an attack disrupts a service. | SYN Flood Analysis, Network Traffic Analysis, Brute Force Incident |
| 🚨 **Incident Response & SOC Operations** | Follow playbooks, spot phishing red flags, verify malicious files against threat intelligence, document findings in tickets, and escalate. Apply the **NIST CSF** (Identify, Protect, Detect, Respond, Recover) to structure response plans. | SOC Level 1 Incident Report, ICMP Flood Plan, Brute Force Incident |
| 🔑 **Identity, Access & Privacy** | Review access logs, find stale accounts and excess privileges, and enforce **least privilege**, password controls, and MFA/2FA. | Access Controls Investigation, Information Privacy Audit, Brute Force Incident |
| 📊 **Governance, Risk & Compliance** | Build risk registers with likelihood and severity scoring, run vulnerability assessments, and keep accurate asset inventories. | Risk Register, Vulnerability Assessment, Asset Inventory |
| 🏗️ **Security Architecture & Network Defense** | Design segmented networks with perimeter firewalls, VPN, wireless security, and IDS/IPS placement, and plan defenses against flood attacks. | Security Infrastructure Design, ICMP Flood Plan, SYN Flood Analysis |

---

<!-- ===================== CONCEPTS ===================== -->
## 🧰 Concepts, Tools & Frameworks

![NIST CSF](https://img.shields.io/badge/NIST%20CSF-0284C7?style=flat-square&logo=nist&logoColor=white)
![NIST SP 800-30](https://img.shields.io/badge/NIST%20SP%20800--30-0EA5E9?style=flat-square&logo=nist&logoColor=white)
![NIST SP 800-53](https://img.shields.io/badge/NIST%20SP%20800--53-1E90FF?style=flat-square&logo=nist&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C8102E?style=flat-square&logo=target&logoColor=white)
![tcpdump](https://img.shields.io/badge/tcpdump-0F172A?style=flat-square&logo=wireshark&logoColor=00D4FF)
![TCP/IP](https://img.shields.io/badge/TCP%2FIP-334155?style=flat-square&logo=cisco&logoColor=white)
![DNS](https://img.shields.io/badge/DNS-1E40AF?style=flat-square&logo=cloudflare&logoColor=white)
![Least Privilege](https://img.shields.io/badge/Least%20Privilege-0F172A?style=flat-square&logo=keycloak&logoColor=00D4FF)
![MFA / 2FA](https://img.shields.io/badge/MFA%20%2F%202FA-394EFF?style=flat-square&logo=authy&logoColor=white)
![Firewall](https://img.shields.io/badge/Firewall-F97316?style=flat-square&logo=paloaltonetworks&logoColor=white)
![IDS/IPS](https://img.shields.io/badge/IDS%2FIPS-334155?style=flat-square&logo=snort&logoColor=white)
![VPN](https://img.shields.io/badge/VPN-EA7E20?style=flat-square&logo=openvpn&logoColor=white)
![VLANs](https://img.shields.io/badge/VLANs-1E293B?style=flat-square&logo=cisco&logoColor=white)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 🤝 Let's Connect

**Hiring for a cybersecurity role, or interested in collaborating? I'd love to connect.**

<a href="https://github.com/kentbalmoria7-oss"><img src="https://img.shields.io/badge/GitHub-kentbalmoria7--oss-00D4FF?style=for-the-badge&logo=github&logoColor=white&labelColor=0D1117" /></a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=kentbalmoria7-oss&label=Repository%20Views&color=00D4FF&style=for-the-badge&labelColor=0D1117" alt="Repository Views" />

<br/>

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
