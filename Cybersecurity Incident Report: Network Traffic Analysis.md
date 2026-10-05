<!-- ===================== HEADER ===================== -->
<div align="center">

# 🔌 Cybersecurity Incident Report: Network Traffic Analysis

### DNS Failure Investigation · "udp port 53 unreachable"

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=tcpdump+Log+Analysis;DNS+%2B+UDP+%2B+ICMP+Troubleshooting;Port+53+Unreachable+Investigation;Root+Cause+%26+Next+Steps" alt="Typing SVG" />

<br/>

![Category](https://img.shields.io/badge/Category-Network%20Traffic%20Analysis-0EA5E9?style=for-the-badge&logo=wireshark&logoColor=white&labelColor=0D1117)
![Protocols](https://img.shields.io/badge/Protocols-DNS%20%7C%20UDP%20%7C%20ICMP-1E90FF?style=for-the-badge&logo=cisco&logoColor=white&labelColor=0D1117)
![Error](https://img.shields.io/badge/Error-udp%20port%2053%20unreachable-DC2626?style=for-the-badge&logo=target&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Report%20Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![tcpdump](https://img.shields.io/badge/tcpdump-0F172A?style=flat-square&logo=wireshark&logoColor=00D4FF)
![DNS](https://img.shields.io/badge/DNS-1E40AF?style=flat-square&logo=cloudflare&logoColor=white)
![UDP](https://img.shields.io/badge/UDP-334155?style=flat-square&logo=cisco&logoColor=white)
![ICMP](https://img.shields.io/badge/ICMP-0284C7?style=flat-square&logo=cisco&logoColor=white)
![Firewall](https://img.shields.io/badge/Firewall-F97316?style=flat-square&logo=paloaltonetworks&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Scenario](#-scenario)
3. [How the Website Loads](#-how-the-website-loads)
4. [Reading the tcpdump Log](#-reading-the-tcpdump-log)
5. [Part 1: Summary of the Problem](#-part-1-provide-a-summary-of-the-problem-found-in-the-tcpdump-log)
6. [Part 2: Analysis and Cause](#-part-2-explain-your-analysis-of-the-data-and-provide-at-least-one-cause-of-the-incident)
7. [Possible Causes](#-possible-causes)
8. [MITRE ATT&CK Mapping](#-mitre-attck-mapping)
9. [Response Actions](#-response-actions)
10. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | Cybersecurity Incident Report: Network Traffic Analysis |
| 🏢 **Organization** | IT services company supporting a client website |
| 🌐 **Affected Website** | www.yummyrecipesforme.com |
| 💥 **Symptom** | Customers saw "destination port unreachable" after waiting for the page to load |
| 🕒 **Incident Time** | 1:24 p.m. (log timestamp `13:24:32.192571`) |
| 💻 **Source (Analyst Computer)** | `192.51.100.15` |
| 🖥️ **Destination (DNS Server)** | `203.0.113.2` on port `53` |
| 🧩 **Protocols Involved** | DNS over UDP, with ICMP error responses |
| ❌ **Error Message** | `udp port 53 unreachable` |
| 🔁 **Repeat Count** | Same error returned on the first attempt and two more times |
| 🧰 **Tool** | tcpdump (network protocol analyzer) |
| 🔎 **Likely Cause** | DNS server not responding, due to a Denial of Service attack or misconfiguration, or traffic blocked at the firewall |

---

<!-- ===================== SCENARIO ===================== -->
## 📖 Scenario

You are a cybersecurity analyst at a company that provides IT services for clients. Several customers of a client reported that they could not access the client's website, `www.yummyrecipesforme.com`, and saw the error **"destination port unreachable"** after waiting for the page to load.

The task is to analyze the situation and determine which network protocol was affected. To start, you visit the website yourself and get the same error. You then load the network analyzer **tcpdump** and try to load the webpage again.

---

<!-- ===================== HOW IT LOADS ===================== -->
## 🔄 How the Website Loads

To load the webpage, the browser first looks up the website's IP address, then sends the request to the web server.

| Step | What Happens | Protocol |
| :-: | :--- | :---: |
| 1️⃣ | The browser sends a query to a DNS server to retrieve the IP address for the website's domain name. | **DNS over UDP** |
| 2️⃣ | The browser uses the returned IP address as the destination for sending an HTTPS request to the web server. | **HTTPS** |
| 3️⃣ | The web server returns the page, and the browser displays it. | **HTTPS** |

> ⚠️ **Where it failed:** in this incident the process stopped at step 1. When the UDP packets were sent to the DNS server, the response was an **ICMP error: "udp port 53 unreachable"**, so the browser never received an IP address.

```text
 Browser ──UDP (DNS query, port 53)──▶ DNS server 203.0.113.2
    ▲                                       │
    └──────── ICMP "udp port 53 unreachable" ◀──┘
```

---

<!-- ===================== LOG BREAKDOWN ===================== -->
## 🔎 Reading the tcpdump Log

| # | Log Element | What It Shows |
| :-: | :--- | :--- |
| 1️⃣ | **First two lines** | The initial outgoing request from the analyst's computer to the DNS server, asking for the IP address of yummyrecipesforme.com. It is sent in a **UDP** packet. |
| 2️⃣ | **Third and fourth lines** | The response to the UDP packet. The `ICMP 203.0.113.2` line starts the error message that the UDP packet was undeliverable to port 53 of the DNS server. |
| 3️⃣ | **Timestamps** | The first set of numbers on each line, such as `13:24:32.192571`, which means 1:24 p.m. and 32.192571 seconds. |
| 4️⃣ | **Source and destination** | In the first line the packet travels `192.51.100.15 > 203.0.113.2.domain`. The address left of `>` is the source (the analyst's computer), and the address on the right is the destination (the DNS server). For the ICMP error, the source is `203.0.113.2` and the destination is `192.51.100.15`. |
| 5️⃣ | **Query ID and flags** | The query identification number is `35084`. The `+` after it indicates flags on the UDP message, and `A?` marks a DNS request for an **A record**, which maps a domain name to an IP address. The third line shows the response protocol, **ICMP**, followed by an ICMP error message. |
| 6️⃣ | **Error message** | `udp port 53 unreachable` appears in the last line. Port 53 is the DNS service port, and "unreachable" means the request did not reach the DNS server because no service was listening on that port. |
| 7️⃣ | **Remaining lines** | ICMP packets were sent two more times, and the same delivery error was received both times. |

---

<!-- ===================== PART 1 ===================== -->
## 📝 Part 1: Provide a Summary of the Problem Found in the tcpdump Log

As part of the DNS protocol, the UDP protocol was used to contact the DNS server to retrieve the IP address for the domain name of yummyrecipesforme.com. The ICMP protocol was used to respond with an error message, indicating issues contacting the DNS server. The UDP message going from your browser to the DNS server is shown in the first two lines of every log event. The ICMP error response from the DNS server to your browser is displayed in the third and fourth lines of every log event with the error message, "udp port 53 unreachable." Since port 53 is associated with DNS protocol traffic, we know this is an issue with the DNS server. Issues with performing the DNS protocol are further evident because the plus sign after the query identification number 35084 indicates flags with the UDP message and the "A?" symbol indicates flags with performing DNS protocol operations. Due to the ICMP error response message about port 53, it is highly likely that the DNS server is not responding. This assumption is further supported by the flags associated with the outgoing UDP message and domain name retrieval.

---

<!-- ===================== PART 2 ===================== -->
## 🔬 Part 2: Explain Your Analysis of the Data and Provide at Least One Cause of the Incident

The incident occurred today at 1:24 p.m. Customers notified the organization that they received the message "destination port unreachable" when they attempted to visit the website yummyrecipesforme.com. The cybersecurity team providing IT services to their client organization is currently investigating the issue so customers can access the website again. In our investigation into the issue, we conducted packet sniffing tests using tcpdump. In the resulting log file, we found that DNS port 53 was unreachable. The next step is to identify whether the DNS server is down or whether traffic to port 53 is blocked by the firewall. The DNS server might be down due to a successful Denial of Service attack or a misconfiguration.

---

<!-- ===================== POSSIBLE CAUSES ===================== -->
## 🧩 Possible Causes

| Possible Cause | What It Means | How to Check |
| :--- | :--- | :--- |
| 💥 **DNS server down (DoS attack)** | A successful Denial of Service attack could have overwhelmed the DNS server so it no longer answers on port 53. | Review DNS server and network logs for a spike in traffic or unusual sources. |
| ⚙️ **DNS server misconfiguration** | The DNS service may not be running or listening on port 53 because of a configuration error. | Confirm the DNS service is running and listening on UDP port 53. |
| 🧱 **Firewall blocking port 53** | A firewall rule may be blocking traffic to port 53 on the DNS server. | Review firewall rules for UDP port 53 traffic to and from the DNS server. |

---

<!-- ===================== MITRE ===================== -->
## 🗺️ MITRE ATT&CK Mapping

> ⚠️ **Not confirmed:** the cause is not yet known, so this mapping applies only if the investigation shows an attack.

| Tactic | Technique | ID | Relevance |
| :--- | :--- | :--- | :--- |
| Impact | Network Denial of Service | [T1498](https://attack.mitre.org/techniques/T1498/) | A successful DoS attack on the DNS server is one possible cause of port 53 becoming unreachable. |

---

<!-- ===================== RESPONSE ===================== -->
## 🛡️ Response Actions

- [x] Reproduced the "destination port unreachable" error from the analyst's computer.
- [x] Captured the traffic with tcpdump and identified the failing protocol (DNS over UDP) and the ICMP error.
- [x] Identified the affected service as the DNS server on port 53.
- [x] Documented the incident and listed likely causes in the report.
- [ ] Next step: determine whether the DNS server is down or whether the firewall is blocking traffic to port 53.
- [ ] Recommended follow-up: check DNS server and firewall logs for signs of a Denial of Service attack.
- [ ] Recommended follow-up: restore the DNS service or correct the firewall or configuration issue, then confirm with a new tcpdump capture.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![tcpdump Log Analysis](https://img.shields.io/badge/tcpdump%20Log%20Analysis-0EA5E9?style=for-the-badge&labelColor=0D1117)
![DNS Troubleshooting](https://img.shields.io/badge/DNS%20Troubleshooting-1E90FF?style=for-the-badge&labelColor=0D1117)
![UDP and ICMP Analysis](https://img.shields.io/badge/UDP%20and%20ICMP%20Analysis-38BDF8?style=for-the-badge&labelColor=0D1117)
![Root Cause Analysis](https://img.shields.io/badge/Root%20Cause%20Analysis-0284C7?style=for-the-badge&labelColor=0D1117)
![Incident Reporting](https://img.shields.io/badge/Incident%20Reporting-334155?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More

**[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
