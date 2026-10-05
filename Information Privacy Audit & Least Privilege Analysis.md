<!-- ===================== HEADER ===================== -->
<div align="center">

# 🛡️ Information Privacy Audit & Least Privilege Analysis

### Data Leak Investigation · Security Control Review

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=Data+Leak+Incident+Analysis;Principle+of+Least+Privilege+Review;NIST+SP+800-53+AC-6+Control+Mapping;Access+Audit+%26+Mitigation+Recommendations" alt="Typing SVG" />

<br/>

![Category](https://img.shields.io/badge/Category-Information%20Privacy-0EA5E9?style=for-the-badge&logo=shield&logoColor=white&labelColor=0D1117)
![Control](https://img.shields.io/badge/Control-Least%20Privilege-1E90FF?style=for-the-badge&logo=auth0&logoColor=white&labelColor=0D1117)
![Framework](https://img.shields.io/badge/Framework-NIST%20SP%20800--53-38BDF8?style=for-the-badge&logo=nist&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![Least Privilege](https://img.shields.io/badge/Least%20Privilege-0F172A?style=flat-square&logo=keycloak&logoColor=00D4FF)
![Access Control](https://img.shields.io/badge/Access%20Control-334155?style=flat-square&logo=auth0&logoColor=white)
![Data Privacy](https://img.shields.io/badge/Data%20Privacy-1E90FF?style=flat-square&logo=protonmail&logoColor=white)
![NIST CSF](https://img.shields.io/badge/NIST%20CSF-0284C7?style=flat-square&logo=nist&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Scenario](#-scenario)
3. [Audit Approach](#-audit-approach)
4. [Incident Summary](#-incident-summary)
5. [Incident Timeline](#-incident-timeline)
6. [Security Control Analysis Matrix](#-security-control-analysis-matrix)
7. [Security Plan Snapshot](#-security-plan-snapshot)
8. [Analysis of the Incident](#-analysis-of-the-incident)
9. [Recommended Actions](#-recommended-actions)
10. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | Information Privacy Audit & Least Privilege Analysis |
| 🏢 **Organization** | Educational technology company with an automated grading application |
| 💥 **Incident** | Internal business plans leaked on social media |
| 🔑 **Root Cause** | A link to an internal folder was shared by mistake, and access was never revoked or limited |
| 🛑 **Control at Fault** | Principle of least privilege |
| 📚 **Reference** | NIST SP 800-53: AC-6 |
| 🧰 **Method** | Incident evaluation, control review, recommendations, and justification |

---

<!-- ===================== SCENARIO ===================== -->
## 📖 Scenario

You work for an educational technology company that developed an application to help teachers automatically grade assignments. The application handles a wide range of data collected from academic institutions, instructors, parents, and students.

Your team was alerted to a data leak of internal business plans on social media. An investigation found that an employee accidentally shared the confidential documents with an external business partner. An audit is underway to determine how similar incidents can be avoided.

A supervisor shared information about the leak, which suggests that the principle of least privilege was not observed during a sales meeting. The task is to analyze the situation and find ways to prevent it from happening again.

---

<!-- ===================== APPROACH ===================== -->
## 🔍 Audit Approach

| # | Phase | Description |
| :-: | :--- | :--- |
| 1️⃣ | **Evaluate the incident** | Review the details of what happened. |
| 2️⃣ | **Review existing controls** | Examine the controls in place to prevent data leaks. |
| 3️⃣ | **Identify improvements** | Find ways to improve information privacy at the company. |
| 4️⃣ | **Justify recommendations** | Explain why the recommendations make data handling more secure. |

---

<!-- ===================== INCIDENT SUMMARY ===================== -->
## 📝 Incident Summary

A sales manager shared access to a folder of internal-only documents with their team during a meeting. The folder contained files associated with a new product that has not been publicly announced. It also included customer analytics and promotional materials. After the meeting, the manager did not revoke access to the internal folder, but warned the team to wait for approval before sharing the promotional materials with others.

During a video call with a business partner, a member of the sales team forgot the warning from their manager. The sales representative intended to share a link to the promotional materials so that the business partner could circulate the materials to their customers. However, the sales representative accidentally shared a link to the internal folder instead. Later, the business partner posted the link on their company's social media page, assuming it was the promotional materials.

---

<!-- ===================== TIMELINE ===================== -->
## ⏱️ Incident Timeline

| Step | Event | Control Gap |
| :-: | :--- | :--- |
| 1️⃣ | The sales manager shares an internal-only folder with the team during a meeting. | The folder mixed unreleased product files and customer analytics with promotional materials. |
| 2️⃣ | After the meeting, access is **not revoked**, and the team is only warned verbally to wait for approval. | Access stayed open and relied on a reminder instead of a technical restriction. |
| 3️⃣ | During a video call, a sales representative shares the **wrong link** with the business partner. | The link to the internal folder could be opened by someone outside the company. |
| 4️⃣ | The business partner **posts the link** on the company's social media page. | The partner could publish the content, which they should not have been allowed to do. |
| 5️⃣ | Internal business plans are exposed publicly. | Confidential data was leaked. |

---

<!-- ===================== MATRIX ===================== -->
## 📊 Security Control Analysis Matrix

| Section | Analysis & Review |
| :--- | :--- |
| **Control** | Least privilege |
| **Issue(s)** | *Access to the internal folder was not limited to the sales team and the manager. The business partner should not have been given permission to share promotional information to social media.* |
| **Review** | *NIST SP 800-53: AC-6 addresses how an organization can protect their data privacy by implementing least privilege. It also suggests control enhancements to improve the effectiveness of least privilege.* |
| **Recommendation(s)** | - Restrict access to sensitive resources based on user role.<br>- Regularly audit user privileges. |
| **Justification** | *Data leaks can be prevented if shared links to internal files are restricted to employees only. Also, requiring managers and security teams to regularly audit access to team files would help limit the exposure of sensitive information.* |

---

<!-- ===================== SNAPSHOT ===================== -->
## 📌 Security Plan Snapshot

The NIST Cybersecurity Framework (CSF) uses a hierarchical, tree-like structure to organize information. From left to right, it describes a broad security function, then becomes more specific as it branches out to a category, subcategory, and individual security controls.

```text
Function  ──▶  Category  ──▶  Subcategory  ──▶  Security Controls
(broad)                                          (specific)
```

---

<!-- ===================== ANALYSIS ===================== -->
## 🧠 Analysis of the Incident

| Finding | Why It Matters |
| :--- | :--- |
| 👥 **Access was broader than needed** | The folder was not limited to the sales team and the manager, which goes against least privilege. |
| 🔗 **Links worked outside the company** | A shared link to internal files could be opened and passed along by an external partner. |
| 🗣️ **Protection relied on a verbal warning** | Telling the team to wait for approval is a policy reminder, not a technical control. |
| 📢 **The partner could publish content** | The business partner should never have had permission to share promotional information to social media. |
| 🗂️ **Mixed sensitivity in one folder** | Unreleased product files, customer analytics, and promotional materials sat together, so one wrong link exposed all of them. |

> 💡 **Conclusion:** The leak was caused by a gap in access control, not just human error. Least privilege and regular access reviews would have limited how far a single mistake could spread.

---

<!-- ===================== ACTIONS ===================== -->
## ✅ Recommended Actions

| Recommendation | What It Prevents |
| :--- | :--- |
| 🎭 **Restrict access to sensitive resources based on user role** | Internal files being reachable by people who don't need them. |
| 🔍 **Regularly audit user privileges** | Access staying open after a meeting or project ends. |
| 🔒 **Restrict shared links to employees only** | A leaked or mis-shared link being usable by outsiders. |

- [x] Evaluated the incident details.
- [x] Reviewed the least privilege control and NIST SP 800-53: AC-6.
- [x] Documented issues, recommendations, and justification in the control matrix.
- [ ] Recommended follow-up: keep promotional materials in a separate folder from internal and unreleased files.
- [ ] Recommended follow-up: have managers revoke temporary access at the end of every meeting.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![Least Privilege](https://img.shields.io/badge/Least%20Privilege-0EA5E9?style=for-the-badge&labelColor=0D1117)
![Access Control Review](https://img.shields.io/badge/Access%20Control%20Review-1E90FF?style=for-the-badge&labelColor=0D1117)
![Data Leak Analysis](https://img.shields.io/badge/Data%20Leak%20Analysis-38BDF8?style=for-the-badge&labelColor=0D1117)
![NIST Framework Mapping](https://img.shields.io/badge/NIST%20Framework%20Mapping-0284C7?style=for-the-badge&labelColor=0D1117)
![Risk Mitigation](https://img.shields.io/badge/Risk%20Mitigation-334155?style=for-the-badge&labelColor=0D1117)
![Security Documentation](https://img.shields.io/badge/Security%20Documentation-475569?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More Labs

**[⬅️ Back to the LetsDefend SOC Analyst Learning Path](https://github.com/kentbalmoria7-oss/LetsDefend-SOCAnalystLearningPath)** · **[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
