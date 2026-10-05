<!-- ===================== HEADER ===================== -->
<div align="center">

# 🛡️ Home Network Asset Inventory

### Asset Management & Data Classification Exercise

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=Network+Asset+Inventory;Device+Ownership+%26+Location+Tracking;Data+Sensitivity+Classification;Protecting+Sensitive+Assets" alt="Typing SVG" />

<br/>

![Category](https://img.shields.io/badge/Category-Asset%20Management-0EA5E9?style=for-the-badge&logo=databricks&logoColor=white&labelColor=0D1117)
![Focus](https://img.shields.io/badge/Focus-Data%20Classification-1E90FF?style=for-the-badge&logo=shield&logoColor=white&labelColor=0D1117)
![Assets](https://img.shields.io/badge/Assets%20Inventoried-6-38BDF8?style=for-the-badge&logo=homeassistant&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![Asset Inventory](https://img.shields.io/badge/Asset%20Inventory-0F172A?style=flat-square&logo=files&logoColor=00D4FF)
![Data Classification](https://img.shields.io/badge/Data%20Classification-334155?style=flat-square&logo=shield&logoColor=white)
![Home Network](https://img.shields.io/badge/Home%20Network-1E90FF?style=flat-square&logo=ubiquiti&logoColor=white)
![Risk Assessment](https://img.shields.io/badge/Risk%20Assessment-DC2626?style=flat-square&logo=target&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Overview](#-overview)
3. [Scenario](#-scenario)
4. [Asset Inventory Table](#-asset-inventory-table)
5. [Sensitivity and Access Designations](#-sensitivity-and-access-designations)
6. [Analysis of the Inventory](#-analysis-of-the-inventory)
7. [Recommended Actions](#-recommended-actions)
8. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | Home Network Asset Inventory |
| 🏠 **Environment** | Small business operated from a home network |
| 🔢 **Assets Inventoried** | 6 devices |
| 🔴 **Highest Sensitivity** | Desktop (**Restricted**) |
| 🟠 **Confidential Assets** | Network router, external hard drive |
| 🟡 **Internal-only Assets** | Guest smartphone, streaming media player, portable game console |
| 🧰 **Method** | Identify devices, record their characteristics, assign a sensitivity level |

---

<!-- ===================== OVERVIEW ===================== -->
## 📖 Overview

One of the most valuable assets in the world today is information, and most information is accessed over a network. A variety of devices connect to a network, and each is a potential entry point to other assets.

An inventory of network devices is a useful asset management tool. It highlights the sensitive assets that need extra protection.

---

<!-- ===================== SCENARIO ===================== -->
## 🕵️ Scenario

You're operating a small business from your home and must create an inventory of your network devices. This helps determine which ones contain sensitive information that requires extra protection.

The inventory starts by identifying devices that have access to the home network, such as:

- 💻 Desktop or laptop computers
- 📱 Smartphones
- 🏠 Smart home devices
- 🎮 Game consoles
- 💾 Storage devices or servers
- 📺 Video streaming devices

Then each device's important characteristics are listed, such as its owner, location, and type. Finally, each device is assigned a level of sensitivity based on how important it is to protect.

---

<!-- ===================== INVENTORY ===================== -->
## 📊 Asset Inventory Table

| Asset | Network Access | Owner | Location | Notes | Sensitivity |
| :--- | :--- | :--- | :--- | :--- | :---: |
| **Network router** | Continuous | Internet service provider (ISP) | On-premises | Has a 2.4 GHz and 5 GHz connection. All devices on the home network connect to the 5 GHz frequency. | **Confidential** |
| **Desktop** | Continuous | Homeowner | On-premises | Contains private information, like photos. | **Restricted** |
| **Guest smartphone** | Occasional | Friend | On and off-premises | Connects to my home network. | **Internal-only** |
| **External hard drive** | Occasional | Homeowner | On-premises | Contains music and movies. | **Confidential** |
| **Streaming media player** | Continuous | Homeowner | On-premises | Payment card information is stored for movie rentals. | **Internal-only** |
| **Portable game console** | Occasional | Friend | On and off-premises | Has a camera and microphone. | **Internal-only** |

---

<!-- ===================== SENSITIVITY ===================== -->
## 🏷️ Sensitivity and Access Designations

| Category | Access Designation | Description |
| :--- | :--- | :--- |
| ⚪ **None** | No relationship | No direct access granted or established. |
| 🟢 **Public** | Anyone | Information or devices accessible by the general public without restrictions. |
| 🟡 **Internal-only** | Internal users | Access limited to trusted home users or guests connected locally. |
| 🟠 **Confidential** | Limited to specific users | Restricted to authorized individuals handling sensitive operational hardware or personal media. |
| 🔴 **Restricted** | Need-to-know | Highly critical personal or private data requiring explicit permission and elevated security controls. |

---

<!-- ===================== ANALYSIS ===================== -->
## 🧠 Analysis of the Inventory

| Observation | Why It Matters |
| :--- | :--- |
| 🔴 **The desktop holds private information** | It has continuous network access and stores private data like photos, so it received the highest sensitivity level. |
| 🟠 **The router connects everything** | All devices connect to its 5 GHz network, so a compromise here would expose every device behind it. It is owned by the ISP. |
| 👥 **Guest devices share the network** | The friend's smartphone and game console join the home network from on and off-premises, which brings outside devices onto the same network as the business assets. |
| 💳 **The streaming player stores payment card data** | Card information is stored for movie rentals and the device is continuously connected, so it deserves a closer look at its sensitivity level. |
| 🎥 **The game console has a camera and microphone** | Any device with a camera or microphone is a privacy concern if it is misused. |
| 🔁 **Continuous vs. occasional access** | Devices that stay connected all the time (router, desktop, streaming player) have a larger exposure window than occasional devices. |

---

<!-- ===================== ACTIONS ===================== -->
## ✅ Recommended Actions

- [x] Identified the devices that connect to the home network.
- [x] Recorded each device's owner, location, network access, and notes.
- [x] Assigned each device a sensitivity level.
- [ ] Recommended follow-up: put guest devices on a separate guest network, away from the business assets.
- [ ] Recommended follow-up: review whether the streaming media player's sensitivity level should be raised, since it stores payment card information.
- [ ] Recommended follow-up: back up the desktop's private data and keep the external hard drive in a secure place.
- [ ] Recommended follow-up: keep the router firmware updated and change its default credentials.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![Asset Management](https://img.shields.io/badge/Asset%20Management-0EA5E9?style=for-the-badge&labelColor=0D1117)
![Data Classification](https://img.shields.io/badge/Data%20Classification-1E90FF?style=for-the-badge&labelColor=0D1117)
![Risk Identification](https://img.shields.io/badge/Risk%20Identification-38BDF8?style=for-the-badge&labelColor=0D1117)
![Network Awareness](https://img.shields.io/badge/Network%20Awareness-0284C7?style=for-the-badge&labelColor=0D1117)
![Security Documentation](https://img.shields.io/badge/Security%20Documentation-475569?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More Labs

**[⬅️ Back to the LetsDefend SOC Analyst Learning Path](https://github.com/kentbalmoria7-oss/LetsDefend-SOCAnalystLearningPath)** · **[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
