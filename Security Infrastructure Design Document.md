<!-- ===================== HEADER ===================== -->
<div align="center">

# 🛡️ Security Infrastructure Design Document

### Artisanal Widget Co. · Secure Network, Endpoint, and Policy Design

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=Security+Infrastructure+Design;Authentication%2C+VPN%2C+Firewall+%26+VLANs;Endpoint+Hardening+%26+Data+Privacy+Policies;IDS%2FIPS+for+Critical+Systems" alt="Typing SVG" />

<br/>

![Role](https://img.shields.io/badge/Role-Security%20Consultant-0EA5E9?style=for-the-badge&logo=shield&logoColor=white&labelColor=0D1117)
![Client](https://img.shields.io/badge/Client-E--commerce%20Retailer-1E90FF?style=for-the-badge&logo=shopify&logoColor=white&labelColor=0D1117)
![Focus](https://img.shields.io/badge/Focus-Defense%20in%20Depth-38BDF8?style=for-the-badge&logo=target&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![LDAP](https://img.shields.io/badge/LDAP%20%2B%20OTP-0F172A?style=flat-square&logo=openldap&logoColor=00D4FF)
![OpenVPN](https://img.shields.io/badge/OpenVPN-EA7E20?style=flat-square&logo=openvpn&logoColor=white)
![Firewall](https://img.shields.io/badge/Firewall-F97316?style=flat-square&logo=paloaltonetworks&logoColor=white)
![802.1X](https://img.shields.io/badge/802.1X%20EAP--TLS-334155?style=flat-square&logo=wifi&logoColor=white)
![VLANs](https://img.shields.io/badge/VLANs-1E90FF?style=flat-square&logo=cisco&logoColor=white)
![IDS/IPS](https://img.shields.io/badge/IDS%2FIPS-0284C7?style=flat-square&logo=snort&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Scenario and Assignment Overview](#-scenario--assignment-overview)
3. [Assignment Requirements](#-assignment-requirements)
4. [Network Architecture Overview](#-network-architecture-overview)
5. [Authentication System](#1-authentication-system)
6. [External System Security](#2-external-system-security)
7. [Internal System Security](#3-internal-system-security)
8. [Remote Access Solution](#4-remote-access-solution)
9. [Firewall Configuration and Basic Rules](#5-firewall-configuration--basic-rules)
10. [Wireless Security](#6-wireless-security)
11. [Network Segmentation (VLAN Configuration)](#7-network-segmentation-vlan-configuration)
12. [Endpoint and Laptop Security](#8-endpoint--laptop-security-configuration)
13. [Application and Patch Management Policy](#9-application--patch-management-policy)
14. [User Data Privacy and Handling Policy](#10-user-data-privacy--handling-policy)
15. [Corporate Password and Security Policy](#11-corporate-password--security-policy)
16. [Intrusion Detection and Prevention](#12-intrusion-detection--prevention-systems-idsips)
17. [Defense in Depth Summary](#-defense-in-depth-summary)
18. [Recommended Follow-Ups](#-recommended-follow-ups)
19. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | Security Infrastructure Design Document |
| 🧑‍💼 **Role** | Security Consultant |
| 🏢 **Client** | Artisanal Widget Co. (online retailer) |
| 👥 **Company Size** | 50 employees in a single office location |
| 🛍️ **Business** | E-commerce business selling hand-crafted widgets to external customers |
| ⚠️ **Primary Risks** | Customer payment and personal data, malware infections, data loss from stolen devices, and securing internal engineering workflows |
| 🧱 **Design Areas** | Authentication, web infrastructure, remote access, firewall, wireless, VLANs, endpoints, policies, IDS/IPS |

---

<!-- ===================== SCENARIO ===================== -->
## 📖 Scenario & Assignment Overview

| Item | Details |
| :--- | :--- |
| 🧑‍💼 **Role** | Security Consultant |
| 🏢 **Client Organization** | Artisanal Widget Co. (online retailer) |
| 👥 **Company Size** | 50 employees in a single office location |
| 🛍️ **Business Profile** | E-commerce business selling hand-crafted widgets to external customers |
| ⚠️ **Primary Risk Focus** | Handling customer payment and personal data, protecting against malware infections, preventing data loss from stolen devices, and securing internal engineering workflows |

---

<!-- ===================== REQUIREMENTS ===================== -->
## 🎯 Assignment Requirements

As the Security Consultant hired by Artisanal Widget Co., the task is to design a complete security infrastructure document covering the following:

| # | Requirement | Description |
| :-: | :--- | :--- |
| 1️⃣ | **Authentication System** | Centralized authentication and identity management. |
| 2️⃣ | **External Web Infrastructure** | Secure customer-facing e-commerce platform. |
| 3️⃣ | **Internal Web Infrastructure** | Secure intranet access for employees. |
| 4️⃣ | **Remote Access** | Command-line and network access for engineering staff. |
| 5️⃣ | **Firewall Architecture** | Basic rules and network protection mechanisms. |
| 6️⃣ | **Wireless Coverage** | Secure office Wi-Fi implementation. |
| 7️⃣ | **Network Segmentation** | VLAN recommendations for departmental isolation. |
| 8️⃣ | **Endpoint Security** | Laptop hardening against theft and malware. |
| 9️⃣ | **Application & Patch Policies** | Restrictions on unapproved software and patch timelines. |
| 🔟 | **Data Privacy & Security Policies** | Controls for accessing, storing, and handling customer payment data. |
| 1️⃣1️⃣ | **Intrusion Detection/Prevention (IDS/IPS)** | Monitoring and prevention solutions for critical database systems. |

---

<!-- ===================== ARCHITECTURE ===================== -->
## 🗺️ Network Architecture Overview

```text
                         🌐 INTERNET
                              │
                    ┌─────────▼─────────┐
                    │  Network Firewall │  ← implicit deny, selective allow
                    └─────────┬─────────┘
          ┌───────────────────┼────────────────────┐
          │                   │                    │
   🛍️ Public Web App    🔐 VPN Server        🔁 Reverse Proxy
     (HTTPS, public)     (OpenVPN)           (internal resources)
                              │                    │
                    ┌─────────▼────────────────────▼─────────┐
                    │        🔑 LDAP + One-Time Password      │
                    └─────────┬──────────────────────────────┘
                              │
     ┌──────────────┬─────────┴────────┬──────────────┐
     │              │                  │              │
 🧱 Infrastructure  🛠️ Engineering   💼 Sales        🚧 Guest
     VLAN             VLAN             VLAN           VLAN
```

> 💡 The diagram summarizes the design below: a firewall at the edge, centralized authentication, and VLANs that isolate each group of systems.

---

<!-- ===================== 1 ===================== -->
## 1. Authentication System

| Control | Design |
| :--- | :--- |
| 🔑 **Central identity** | Authentication is handled centrally by an **LDAP server**. |
| 📲 **Second factor** | **One-Time Password (OTP) generators** are used as a second factor for authentication. |

---

<!-- ===================== 2 ===================== -->
## 2. External System Security

| Control | Design |
| :--- | :--- |
| 🔒 **Encryption** | The customer-facing application is served via **HTTPS**. |
| 🛒 **Purpose** | It is an e-commerce platform where visitors browse and purchase products and create and log into accounts. |
| 🌍 **Exposure** | The application is **publicly accessible**. |

---

<!-- ===================== 3 ===================== -->
## 3. Internal System Security

| Control | Design |
| :--- | :--- |
| 🔒 **Encryption** | Internal employee resources are also served over **HTTPS**. |
| 🔑 **Authentication** | Employees must authenticate to access them. |
| 🏢 **Access scope** | Accessible **only from the internal company network** and only with an authenticated account. |

---

<!-- ===================== 4 ===================== -->
## 4. Remote Access Solution

Engineers need remote access to internal resources and remote command-line access to workstations.

| Component | Design |
| :--- | :--- |
| 🔐 **Network-level VPN** | A VPN solution such as **OpenVPN** gives engineers remote network access. |
| 🔁 **Reverse proxy** | Recommended in addition to the VPN to make internal resource access easier. |
| 🔑 **Authentication** | Both rely on the **LDAP server** for authentication and authorization. |

---

<!-- ===================== 5 ===================== -->
## 5. Firewall Configuration & Basic Rules

A **network-based firewall appliance** is required.

| Order | Rule | Purpose |
| :-: | :--- | :--- |
| 1️⃣ | **Implicit deny** | Start by denying all traffic that is not explicitly allowed. |
| 2️⃣ | **Allow public access to the external application** | Lets customers reach the e-commerce platform. |
| 3️⃣ | **Allow traffic to the reverse proxy server** | Supports access to internal resources. |
| 4️⃣ | **Allow traffic to the VPN server** | Supports remote engineer access. |

---

<!-- ===================== 6 ===================== -->
## 6. Wireless Security

| Control | Design |
| :--- | :--- |
| 📶 **Standard** | **802.1X with EAP-TLS** |
| 📜 **Client certificates** | Required, and can also authenticate other services such as the VPN, reverse proxy, and internal authentication. |
| ✅ **Why not standard WPA2** | 802.1X is more secure and easier to manage as the company grows. |

---

<!-- ===================== 7 ===================== -->
## 7. Network Segmentation (VLAN Configuration)

VLANs make access control easier to manage through network segmentation.

| VLAN | Purpose |
| :--- | :--- |
| 🛠️ **Engineering VLAN** | All engineering workstations and engineering services. |
| 🧱 **Infrastructure VLAN** | Infrastructure devices, including wireless APs, network hardware, and critical servers like authentication. |
| 💼 **Sales VLAN** | Non-engineering corporate machines. |
| 🚧 **Guest VLAN** | Strictly isolated for third-party devices and visitors that do not fit standard assignments. |

---

<!-- ===================== 8 ===================== -->
## 8. Endpoint & Laptop Security Configuration

Because the company handles payment information and user data, privacy is a primary requirement.

| Control | Design | Protects Against |
| :--- | :--- | :--- |
| 💽 **Full Disk Encryption (FDE)** | Required on all laptops. | Unauthorized data access if a device is lost or stolen. |
| 🦠 **Antivirus software** | Required on laptops. | Infections from common malware. |
| 📋 **Binary whitelisting** | Recommended in addition to antivirus. | Uncommon attacks and unknown threats. |

---

<!-- ===================== 9 ===================== -->
## 9. Application & Patch Management Policy

| Policy | Details |
| :--- | :--- |
| 🧩 **Approved software only** | Third-party software is limited to applications directly related to work functions. |
| 🚫 **Banned categories** | Pirated software, license key generators, and cracked software are explicitly banned. |
| ⏱️ **Patch timeline** | Patches must be installed within **30 days** of wide availability. |

---

<!-- ===================== 10 ===================== -->
## 10. User Data Privacy & Handling Policy

| Policy | Details |
| :--- | :--- |
| 🎯 **Purpose-based access** | User data may only be accessed for specific work purposes tied to a particular task or project. |
| 🔎 **Specific requests** | Requests must name specific pieces of data, not broad or exploratory ones. |
| ✅ **Approval with expiry** | Access requests are reviewed and approved with a defined expiration date before access is granted. |
| 🚫 **No portable storage** | User data is prohibited on USB keys and external hard drives. |
| 🔐 **Exception handling** | If an exception is necessary, an encrypted portable drive must be used. |
| 💽 **Encryption at rest** | All user data at rest must be stored on encrypted media. |

---

<!-- ===================== 11 ===================== -->
## 11. Corporate Password & Security Policy

| Requirement | Details |
| :--- | :--- |
| 🔤 **Minimum length** | 8 characters |
| ✳️ **Special character** | At least one special character or punctuation mark |
| 🔄 **Password change** | Mandatory every 12 months |
| 🎓 **Security training** | Every employee completes training once per year, covering phishing detection, physical device security, and emerging security threats. |

---

<!-- ===================== 12 ===================== -->
## 12. Intrusion Detection & Prevention Systems (IDS/IPS)

| Solution | Where | Purpose |
| :--- | :--- | :--- |
| 👁️ **NIDS** (Network IDS) | Across the network | Monitors network activity for signs of attack or malware infection without interrupting users. |
| 🛑 **NIPS** (Network IPS) | Server segment holding customer data | Actively blocks attacks, since this high-value data is a primary target. |
| 🗂️ **HIDS** (Host-based IDS) | Servers holding customer data | Improves file integrity and access monitoring. |

---

<!-- ===================== SUMMARY ===================== -->
## 🧱 Defense in Depth Summary

| Layer | Controls | Addresses |
| :--- | :--- | :--- |
| 🌐 **Perimeter** | Network firewall with implicit deny, HTTPS | Unwanted inbound traffic and data in transit |
| 🔑 **Identity** | LDAP with OTP second factor, 802.1X with client certificates | Stolen or weak credentials |
| 🔐 **Remote access** | OpenVPN and reverse proxy, both tied to LDAP | Unauthorized remote entry |
| 🧱 **Network** | VLAN segmentation, isolated Guest VLAN | Lateral movement between groups |
| 💻 **Endpoint** | FDE, antivirus, binary whitelisting | Device theft and malware |
| 📜 **Policy** | Software restrictions, 30-day patching, data handling rules, training | Human error and unapproved software |
| 👁️ **Monitoring** | NIDS, NIPS, HIDS | Attacks on customer data servers |

---

<!-- ===================== FOLLOW-UPS ===================== -->
## ✅ Recommended Follow-Ups

- [x] Designed all required security areas for Artisanal Widget Co.
- [x] Documented policies for software, patching, data handling, passwords, and training.
- [ ] Recommended follow-up: revisit the password policy and consider a longer minimum length, since 8 characters is short by current guidance.
- [ ] Recommended follow-up: test the firewall rules and VLAN access in a controlled setting before rollout.
- [ ] Recommended follow-up: schedule regular reviews of IDS/IPS alerts and access approvals.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![Security Architecture](https://img.shields.io/badge/Security%20Architecture-0EA5E9?style=for-the-badge&labelColor=0D1117)
![Network Segmentation](https://img.shields.io/badge/Network%20Segmentation-1E90FF?style=for-the-badge&labelColor=0D1117)
![Identity and Access Management](https://img.shields.io/badge/Identity%20and%20Access%20Management-38BDF8?style=for-the-badge&labelColor=0D1117)
![Firewall and VPN Design](https://img.shields.io/badge/Firewall%20and%20VPN%20Design-0284C7?style=for-the-badge&labelColor=0D1117)
![Endpoint Hardening](https://img.shields.io/badge/Endpoint%20Hardening-334155?style=for-the-badge&labelColor=0D1117)
![Security Policy Writing](https://img.shields.io/badge/Security%20Policy%20Writing-475569?style=for-the-badge&labelColor=0D1117)
![IDS/IPS Planning](https://img.shields.io/badge/IDS%2FIPS%20Planning-1E293B?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More Labs

**[⬅️ Back to the LetsDefend SOC Analyst Learning Path](https://github.com/kentbalmoria7-oss/LetsDefend-SOCAnalystLearningPath)** · **[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
