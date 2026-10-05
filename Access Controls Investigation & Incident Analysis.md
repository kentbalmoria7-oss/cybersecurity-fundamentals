<!-- ===================== HEADER ===================== -->
<div align="center">

# 🛡️ Access Controls Investigation & Incident Analysis

### Unauthorized Payroll Event · Access Log Review & Mitigation Plan

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=Access+Log+Analysis;Authentication+%26+Authorization+Review;Identifying+Access+Control+Weaknesses;Mitigation+%26+Hardening+Recommendations" alt="Typing SVG" />

<br/>

![Category](https://img.shields.io/badge/Category-Access%20Control-0EA5E9?style=for-the-badge&logo=auth0&logoColor=white&labelColor=0D1117)
![Focus](https://img.shields.io/badge/Focus-Incident%20Analysis-1E90FF?style=for-the-badge&logo=shield&logoColor=white&labelColor=0D1117)
![Finding](https://img.shields.io/badge/Finding-Stale%20Admin%20Account-DC2626?style=for-the-badge&logo=target&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![Access Logs](https://img.shields.io/badge/Access%20Logs-0F172A?style=flat-square&logo=files&logoColor=00D4FF)
![Authentication](https://img.shields.io/badge/Authentication-334155?style=flat-square&logo=auth0&logoColor=white)
![Authorization](https://img.shields.io/badge/Authorization-1E90FF?style=flat-square&logo=keycloak&logoColor=white)
![MFA](https://img.shields.io/badge/MFA-394EFF?style=flat-square&logo=authy&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C8102E?style=flat-square&logo=target&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Scenario](#-scenario)
3. [Investigation Approach](#-investigation-approach)
4. [Access Log Details](#-access-log-details)
5. [Access Controls Worksheet](#-access-controls-worksheet)
6. [Analysis of the Incident](#-analysis-of-the-incident)
7. [Recommendations](#-recommendations)
8. [MITRE ATT&CK Mapping](#-mitre-attck-mapping)
9. [Response Actions](#-response-actions)
10. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | Access Controls Investigation & Incident Analysis |
| 🏢 **Environment** | Growing business with its first cybersecurity hire |
| 💸 **Incident** | A deposit was made to an unknown bank account (payment was stopped) |
| 📅 **Date of Event** | 10/03/2023, 8:29:57 AM |
| 👤 **Account Used** | `Legal\Administrator` |
| 🌐 **Source IP** | `152.207.255.255` |
| 💻 **Computer** | `Up2-NoGud` |
| 🎯 **Root Cause** | A former contractor's admin account was still active and had payroll access |
| 🧰 **Method** | Access log review and access controls worksheet |

---

<!-- ===================== SCENARIO ===================== -->
## 📖 Scenario

You're the first cybersecurity professional hired by a growing business. Recently, a deposit was made from the business to an unknown bank account. The finance manager says they didn't make a mistake. Fortunately, they were able to stop the payment. The owner asked for an investigation into what happened so it can be prevented in the future.

---

<!-- ===================== APPROACH ===================== -->
## 🔍 Investigation Approach

| # | Phase | Description |
| :-: | :--- | :--- |
| 1️⃣ | **Review the access log** | Examine the log of the incident to understand what happened. |
| 2️⃣ | **Take notes** | Record details that help identify a possible threat actor. |
| 3️⃣ | **Spot access control issues** | Find the weaknesses in access controls that the user exploited. |
| 4️⃣ | **Recommend mitigations** | Suggest improvements to reduce the likelihood of a repeat incident. |

---

<!-- ===================== ACCESS LOG ===================== -->
## 📄 Access Log Details

| Field | Value |
| :--- | :--- |
| 🧩 **Event Source** | AdsmEmployeeService |
| 🗂️ **Event Category** | None |
| 🆔 **Event ID** | 1227 |
| 📅 **Date** | 10/03/2023 |
| 🕒 **Time** | 8:29:57 AM |
| 👤 **User** | `Legal\Administrator` |
| 💻 **Computer** | `Up2-NoGud` |
| 🌐 **IP** | `152.207.255.255` |
| 📝 **Description** | Payroll event added. FAUX_BANK |

> 🔎 **Key observation:** An administrator account added a payroll event pointing to an outside bank, which matches the unauthorized deposit the finance manager reported.

---

<!-- ===================== WORKSHEET ===================== -->
## 📊 Access Controls Worksheet

| Category | Note(s) | Issue(s) | Recommendation(s) |
| :--- | :--- | :--- | :--- |
| **Authorization / authentication** | - The event took place on 10/03/23.<br>- The user is Legal/Administrator.<br>- The IP address of the computer used to login is 152.207.255.255. | - Robert Taylor Jr is an admin.<br>- His contract ended in 2019, but his account accessed payroll systems in 2023. | - User accounts should expire after 30 days.<br>- Contractors should have limited access to business resources.<br>- Enable MFA. |

---

<!-- ===================== ANALYSIS ===================== -->
## 🧠 Analysis of the Incident

| Finding | Why It Matters |
| :--- | :--- |
| 🕰️ **Account outlived the contract** | The contract ended in 2019, yet the account was still able to log in and reach payroll systems in 2023, about four years later. |
| 👑 **Excessive privileges** | A contractor held administrator rights, far more access than a temporary role requires. |
| 🔓 **No additional verification** | Nothing in the notes shows a second factor of authentication, so a valid username and password was enough to act. |
| 💸 **Sensitive function exposed** | The account could add payroll events, a direct path to moving company money. |

> 💡 **Conclusion:** The incident was made possible by weak access controls, specifically an active administrator account for a former contractor with no expiry and no multi-factor authentication. The stopped payment limited the damage, but the control gaps remain open until they are fixed.

---

<!-- ===================== RECOMMENDATIONS ===================== -->
## ✅ Recommendations

| Recommendation | What It Prevents |
| :--- | :--- |
| ⏳ **Expire user accounts after 30 days** | Old or unused accounts staying active after someone's contract ends. |
| 🧱 **Limit contractor access to business resources** | Contractors holding admin rights or reaching sensitive systems like payroll. |
| 🔐 **Enable multi-factor authentication (MFA)** | Stolen or reused credentials being enough to sign in. |

---

<!-- ===================== MITRE ===================== -->
## 🗺️ MITRE ATT&CK Mapping

| Tactic | Technique | ID | Relevance |
| :--- | :--- | :--- | :--- |
| Defense Evasion / Persistence / Privilege Escalation / Initial Access | Valid Accounts | [T1078](https://attack.mitre.org/techniques/T1078/) | A legitimate administrator account was used to access payroll systems. |

---

<!-- ===================== RESPONSE ===================== -->
## 🛡️ Response Actions

- [x] Reviewed the access log for the incident.
- [x] Recorded notes on the date, user, and source IP.
- [x] Identified the access control issues that were exploited.
- [x] Documented recommendations in the access controls worksheet.
- [ ] Recommended follow-up: disable the former contractor's account and review its recent activity.
- [ ] Recommended follow-up: audit all accounts for stale users and excess privileges.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![Access Log Analysis](https://img.shields.io/badge/Access%20Log%20Analysis-0EA5E9?style=for-the-badge&labelColor=0D1117)
![Authentication and Authorization](https://img.shields.io/badge/Authentication%20and%20Authorization-1E90FF?style=for-the-badge&labelColor=0D1117)
![Least Privilege](https://img.shields.io/badge/Least%20Privilege-38BDF8?style=for-the-badge&labelColor=0D1117)
![Incident Analysis](https://img.shields.io/badge/Incident%20Analysis-0284C7?style=for-the-badge&labelColor=0D1117)
![Risk Mitigation](https://img.shields.io/badge/Risk%20Mitigation-334155?style=for-the-badge&labelColor=0D1117)
![Security Documentation](https://img.shields.io/badge/Security%20Documentation-475569?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More Labs

**[⬅️ Back to the LetsDefend SOC Analyst Learning Path](https://github.com/kentbalmoria7-oss/LetsDefend-SOCAnalystLearningPath)** · **[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
