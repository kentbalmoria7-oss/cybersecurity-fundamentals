<!-- ===================== HEADER ===================== -->
<div align="center">

# 🌊 NIST CSF Incident Response & ICMP Flood Mitigation Plan

### Denial of Service Incident Analysis · Network Security Improvement Plan

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=ICMP+Flood+(DoS)+Incident+Analysis;NIST+CSF+Aligned+Response+Plan;Firewall+Hardening+%26+IDS%2FIPS+Rules;Recovery+%26+Network+Resilience" alt="Typing SVG" />

<br/>

![Category](https://img.shields.io/badge/Category-Incident%20Response-0EA5E9?style=for-the-badge&logo=shield&logoColor=white&labelColor=0D1117)
![Attack](https://img.shields.io/badge/Attack-ICMP%20Flood%20DoS-DC2626?style=for-the-badge&logo=cloudflare&logoColor=white&labelColor=0D1117)
![Framework](https://img.shields.io/badge/Framework-NIST%20CSF-1E90FF?style=for-the-badge&logo=nist&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![Firewall](https://img.shields.io/badge/Firewall-F97316?style=flat-square&logo=paloaltonetworks&logoColor=white)
![IDS/IPS](https://img.shields.io/badge/IDS%2FIPS-0F172A?style=flat-square&logo=snort&logoColor=00D4FF)
![Network Monitoring](https://img.shields.io/badge/Network%20Monitoring-334155?style=flat-square&logo=wireshark&logoColor=white)
![NIST CSF](https://img.shields.io/badge/NIST%20CSF-0284C7?style=flat-square&logo=nist&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C8102E?style=flat-square&logo=target&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Executive Summary](#-executive-summary)
3. [Incident Overview](#-incident-overview)
4. [Incident Timeline](#-incident-timeline)
5. [NIST CSF Alignment](#-nist-cybersecurity-framework-alignment)
6. [Recovery Sequence](#-recovery-sequence)
7. [MITRE ATT&CK Mapping](#-mitre-attck-mapping)
8. [Response Actions](#-response-actions)
9. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | NIST CSF Incident Response & ICMP Flood Mitigation Plan |
| 🏢 **Organization** | Multimedia company (web design, graphic design, and social media marketing) |
| 💥 **Attack Type** | ICMP flood (Denial of Service) |
| 🔑 **Root Cause** | Unconfigured perimeter firewall permitting unfiltered ICMP traffic |
| ⏱️ **Impact** | 2-hour total outage of internal network resources and client service platforms |
| 🛡️ **Framework** | NIST Cybersecurity Framework (CSF) |
| 🧰 **Controls Planned** | Rate limiting, IDS/IPS rules, anti-spoofing verification, network monitoring |

---

<!-- ===================== EXECUTIVE SUMMARY ===================== -->
## 📖 Executive Summary

This write-up documents an incident response and network security improvement plan following a Denial of Service (DoS) attack against a multimedia company specializing in web design, graphic design, and social media marketing. The incident involved an incoming ICMP ping flood that left internal network resources unavailable for two hours.

The analysis and security strategy are organized according to the **National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF)**.

---

<!-- ===================== INCIDENT OVERVIEW ===================== -->
## 🔎 Incident Overview

| Item | Details |
| :--- | :--- |
| 🎯 **Target** | Multimedia company internal network |
| ⚔️ **Attack Type** | ICMP flood (Denial of Service) |
| 🔑 **Root Cause** | Unconfigured perimeter firewall permitting unfiltered ICMP traffic |
| ⏱️ **Impact** | 2-hour total outage of internal network resources and client service platforms |
| 🚑 **Initial Response** | Blocked inbound ICMP traffic, isolated non-critical services, and prioritized critical service recovery |

---

<!-- ===================== TIMELINE ===================== -->
## ⏱️ Incident Timeline

| Step | Event | Result |
| :-: | :--- | :--- |
| 1️⃣ | An external attacker sends a flood of ICMP ping packets at the company network. | The perimeter firewall allows the unfiltered ICMP traffic through. |
| 2️⃣ | The flood exhausts network bandwidth and resources. | Internal network resources and client service platforms go down for two hours. |
| 3️⃣ | The team blocks inbound ICMP traffic. | The flood is stopped at the edge. |
| 4️⃣ | Non-critical services are isolated, and critical services are prioritized. | Core services return first. |
| 5️⃣ | The remaining systems are restored once ICMP traffic levels normalize. | Normal operations resume. |

---

<!-- ===================== NIST CSF ===================== -->
## 🧩 NIST Cybersecurity Framework Alignment

### 1️⃣ Identify

| Area | Details |
| :--- | :--- |
| 🎯 **Targeted Assets** | Internal network, core servers, and employee access nodes. |
| 🕵️ **Threat Actor** | External malicious actor exploiting perimeter firewall misconfigurations. |
| ⚠️ **Vulnerability** | Unfiltered ICMP packet handling that allowed network bandwidth and resource exhaustion. |

### 2️⃣ Protect

| Control | Details |
| :--- | :--- |
| 🚦 **Firewall Rate Limiting** | Applied rules to cap incoming ICMP packet rates. |
| 🛡️ **IDS/IPS Deployment** | Configured intrusion detection and prevention rules to filter suspicious ICMP signatures. |
| 🔒 **Hardening** | Closed unneeded ports and hardened default firewall policies. |

### 3️⃣ Detect

| Control | Details |
| :--- | :--- |
| 🧭 **Anti-Spoofing Verification** | Enabled source IP address validation at the firewall edge to detect forged packet origins. |
| 📈 **Network Monitoring** | Integrated traffic monitoring tools to establish baseline behavior and flag anomalous spikes. |

### 4️⃣ Respond

| Action | Details |
| :--- | :--- |
| 🧯 **Containment** | Isolate affected segments immediately upon detection. |
| 🔬 **Triage & Analysis** | Review firewall and IDS/IPS logs to trace attack vectors and impact scope. |
| 📣 **Reporting** | Escalate incidents to executive leadership and relevant legal authorities as required. |

### 5️⃣ Recover

| Action | Details |
| :--- | :--- |
| 🔁 **Restoration Sequence** | Restore services in a defined order (see below). |

---

<!-- ===================== RECOVERY ===================== -->
## 🔁 Recovery Sequence

| Order | Step |
| :-: | :--- |
| 1️⃣ | Filter and block malicious flood traffic at the edge. |
| 2️⃣ | Suspend non-critical services to preserve bandwidth. |
| 3️⃣ | Bring core critical services back online first. |
| 4️⃣ | Restore remaining systems once ICMP traffic levels normalize. |

---

<!-- ===================== MITRE ===================== -->
## 🗺️ MITRE ATT&CK Mapping

| Tactic | Technique | ID | Relevance |
| :--- | :--- | :--- | :--- |
| Impact | Network Denial of Service: Direct Network Flood | [T1498.001](https://attack.mitre.org/techniques/T1498/001/) | A flood of ICMP packets exhausted network bandwidth and made internal resources unavailable. |

---

<!-- ===================== RESPONSE ===================== -->
## 🛡️ Response Actions

- [x] Identified the attack as an ICMP flood (DoS) caused by an unconfigured perimeter firewall.
- [x] Blocked inbound ICMP traffic and isolated non-critical services.
- [x] Prioritized recovery of critical services.
- [x] Defined a plan across all five NIST CSF functions.
- [x] Planned firewall rate limiting, IDS/IPS rules, and hardened firewall policies.
- [x] Planned anti-spoofing verification and network monitoring for detection.
- [ ] Recommended follow-up: test the new firewall rules in a controlled setting before relying on them.
- [ ] Recommended follow-up: run regular reviews of firewall and IDS/IPS logs.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![Incident Response](https://img.shields.io/badge/Incident%20Response-0EA5E9?style=for-the-badge&labelColor=0D1117)
![NIST CSF Alignment](https://img.shields.io/badge/NIST%20CSF%20Alignment-1E90FF?style=for-the-badge&labelColor=0D1117)
![DoS Mitigation](https://img.shields.io/badge/DoS%20Mitigation-38BDF8?style=for-the-badge&labelColor=0D1117)
![Firewall Hardening](https://img.shields.io/badge/Firewall%20Hardening-0284C7?style=for-the-badge&labelColor=0D1117)
![Network Monitoring](https://img.shields.io/badge/Network%20Monitoring-334155?style=for-the-badge&labelColor=0D1117)
![Security Documentation](https://img.shields.io/badge/Security%20Documentation-475569?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More Labs

**[⬅️ Back to the LetsDefend SOC Analyst Learning Path](https://github.com/kentbalmoria7-oss/LetsDefend-SOCAnalystLearningPath)** · **[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
