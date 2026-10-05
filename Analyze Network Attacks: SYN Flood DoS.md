<!-- ===================== HEADER ===================== -->
<div align="center">

# 🌊 Analyze Network Attacks: SYN Flood DoS

### Packet Capture Analysis · Web Server Outage Investigation

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=900&color=00D4FF&center=true&vCenter=true&width=760&height=50&lines=TCP+SYN+Flood+Detection;Packet+Capture+Analysis;Three-Way+Handshake+Exploitation;Containment+%26+Mitigation+Planning" alt="Typing SVG" />

<br/>

![Category](https://img.shields.io/badge/Category-Network%20Attack%20Analysis-0EA5E9?style=for-the-badge&logo=wireshark&logoColor=white&labelColor=0D1117)
![Attack](https://img.shields.io/badge/Attack-SYN%20Flood%20(DoS)-DC2626?style=for-the-badge&logo=cloudflare&logoColor=white&labelColor=0D1117)
![Protocol](https://img.shields.io/badge/Protocol-TCP-1E90FF?style=for-the-badge&logo=cisco&logoColor=white&labelColor=0D1117)
![Status](https://img.shields.io/badge/Status-Completed-22C55E?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=0D1117)

<br/>

![Packet Analysis](https://img.shields.io/badge/Packet%20Analysis-0F172A?style=flat-square&logo=wireshark&logoColor=00D4FF)
![TCP/IP](https://img.shields.io/badge/TCP%2FIP-334155?style=flat-square&logo=cisco&logoColor=white)
![Firewall](https://img.shields.io/badge/Firewall-F97316?style=flat-square&logo=paloaltonetworks&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C8102E?style=flat-square&logo=target&logoColor=white)

</div>

---

<!-- ===================== NAVIGATION ===================== -->
## 🧭 Table of Contents

1. [Case Summary](#-case-summary)
2. [Scenario](#-scenario)
3. [Actions Taken](#-actions-taken)
4. [Packet Capture Findings](#-packet-capture-findings)
5. [Capture Timeline](#-capture-timeline)
6. [Section 1: Identify the Type of Attack](#-section-1-identify-the-type-of-attack-that-may-have-caused-this-network-interruption)
7. [Section 2: How the Attack Causes the Malfunction](#-section-2-explain-how-the-attack-is-causing-the-website-malfunction)
8. [MITRE ATT&CK Mapping](#-mitre-attck-mapping)
9. [Message for Management](#-message-for-management)
10. [Recommended Follow-Ups](#-recommended-follow-ups)
11. [Skills Demonstrated](#-skills-demonstrated)

---

<!-- ===================== CASE SUMMARY ===================== -->
## 📋 Case Summary

| Field | Details |
| :--- | :--- |
| 🧪 **Exercise** | Analyze Network Attacks |
| 🏢 **Organization** | Travel agency advertising sales and promotions on its website |
| 🖥️ **Target** | Company web server `192.0.2.1` (HTTPS, port 443) |
| 🕵️ **Suspected Source** | `203.0.113.0` (unfamiliar IP address, source port `54770`) |
| ⚔️ **Attack Type** | TCP SYN flood (a type of Denial of Service attack) |
| 💥 **Symptom** | Connection timeout error when visiting the website |
| 🚑 **Immediate Response** | Took the server offline to recover, and blocked the attacking IP at the firewall |
| ⚠️ **Known Limitation** | The IP block is temporary because an attacker can spoof other IP addresses |
| 🧰 **Method** | Packet sniffer capture and log analysis |

---

<!-- ===================== SCENARIO ===================== -->
## 📖 Scenario

You work as a security analyst for a travel agency that advertises sales and promotions on the company's website. Employees regularly access the sales webpage to search for vacation packages their customers might like.

One afternoon, you receive an automated alert from your monitoring system about a problem with the web server. You try to visit the company's website but receive a **connection timeout** error in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of **TCP SYN requests coming from an unfamiliar IP address**. The server appears overwhelmed by the volume of incoming traffic and is losing its ability to respond, so you suspect it is under attack.

---

<!-- ===================== ACTIONS TAKEN ===================== -->
## 🚑 Actions Taken

| Step | Action | Purpose |
| :-: | :--- | :--- |
| 1️⃣ | Captured traffic with a packet sniffer. | Find the cause of the timeout. |
| 2️⃣ | Took the web server offline temporarily. | Let the machine recover and return to normal operating status. |
| 3️⃣ | Configured the firewall to block the IP address sending the abnormal SYN requests. | Stop the traffic from the identified source. |
| 4️⃣ | Prepared to alert the manager. | Discuss next steps to stop the attacker and prevent a repeat. |

> ⚠️ **Why the block is not enough:** an attacker can spoof other IP addresses to get around an IP block, so this fix will not last long.

---

<!-- ===================== PACKET FINDINGS ===================== -->
## 🔎 Packet Capture Findings

| Observation | Evidence in the Log |
| :--- | :--- |
| 🎯 **Single target** | All traffic is directed at `192.0.2.1` on port `443`. |
| 🕵️ **One dominant source** | After packet 57, the log is almost entirely `203.0.113.0` sending SYN packets from the same source port, `54770`. |
| 🔁 **Handshakes never complete** | The repeated SYNs from `203.0.113.0` are not followed by final ACKs, so connections stay half-open. |
| 🧑‍💼 **Normal users at first** | `198.51.100.23` and `198.51.100.14` completed handshakes, requested `/sales.html`, and received `200 OK`. |
| ❌ **Legitimate users start failing** | The server answers `198.51.100.5` with a `504 Gateway Time-out` and sends `RST, ACK` resets to `198.51.100.16`, `198.51.100.7`, `198.51.100.22`, and `198.51.100.9`. |
| 🔇 **Server stops responding** | After the last reset at about 20.8 seconds, the rest of the capture contains only SYN packets from `203.0.113.0`, with no replies from the server. |

### 🧾 Key Log Excerpts

**Normal connection (healthy handshake and page load):**

```text
47  3.144521  198.51.100.23  192.0.2.1      TCP   42584->443 [SYN] Seq=0 Win-5792 Len=120...
48  3.195755  192.0.2.1      198.51.100.23  TCP   443->42584 [SYN, ACK] Seq=0 Win-5792 Len=120...
49  3.246989  198.51.100.23  192.0.2.1      TCP   42584->443 [ACK] Seq=1 Win-5792 Len=120...
50  3.298223  198.51.100.23  192.0.2.1      HTTP  GET  /sales.html HTTP/1.1
51  3.349457  192.0.2.1      198.51.100.23  HTTP  HTTP/1.1 200 OK (text/html)
```

**The flood begins (repeated SYNs from the same IP and port):**

```text
57  3.664863  203.0.113.0    192.0.2.1      TCP   54770->443 [SYN] Seq=0 Win=5792 Len=0...
59  3.795332  203.0.113.0    192.0.2.1      TCP   54770->443 [SYN] Seq=0 Win-5792 Len=120...
61  3.939499  203.0.113.0    192.0.2.1      TCP   54770->443 [SYN] Seq=0 Win-5792 Len=120...
```

**A legitimate user starts to fail:**

```text
71  6.228728  198.51.100.5   192.0.2.1      HTTP  GET  /sales.html HTTP/1.1
77  7.330577  192.0.2.1      198.51.100.5   TCP   HTTP/1.1 504 Gateway Time-out (text/html)
```

---

<!-- ===================== TIMELINE ===================== -->
## ⏱️ Capture Timeline

| Time (seconds) | Packets | Event |
| :--- | :---: | :--- |
| 3.14 to 3.35 | 47 to 51 | `198.51.100.23` completes a normal handshake and loads `/sales.html` (`200 OK`). |
| 3.39 to 4.02 | 52 to 62 | `203.0.113.0` completes one handshake, then starts repeating SYNs. `198.51.100.14` loads the page normally. |
| 6.23 | 73 | Server sends `RST, ACK` to `198.51.100.16`, a legitimate connection is reset. |
| 7.33 | 77 | Server returns `504 Gateway Time-out` to `198.51.100.5`. |
| 7.38 to 7.68 | 80 to 85 | Resets to `198.51.100.7` and `198.51.100.22`. |
| 19.84 | 121 | Reset to `198.51.100.9`. |
| 20.81 | 124 | Last server reply to `203.0.113.0`. |
| 21.14 to 51.82 | 125 to end | Only SYN packets from `203.0.113.0` appear, with no server responses. |

---

<!-- ===================== SECTION 1 ===================== -->
## 🧩 Section 1: Identify the Type of Attack That May Have Caused This Network Interruption

One potential explanation for the website's connection timeout error message is a **DoS attack**. The logs show that the web server stops responding after it is overloaded with SYN packet requests. This event could be a type of DoS attack called **SYN flooding**.

---

<!-- ===================== SECTION 2 ===================== -->
## ⚙️ Section 2: Explain How the Attack Is Causing the Website Malfunction

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. The handshake consists of three steps:

| Step | Packet | What Happens |
| :-: | :---: | :--- |
| 1️⃣ | **SYN** | A SYN packet is sent from the source to the destination, requesting to connect. |
| 2️⃣ | **SYN-ACK** | The destination replies to the source with a SYN-ACK packet to accept the connection request. The destination reserves resources for the source to connect. |
| 3️⃣ | **ACK** | A final ACK packet is sent from the source to the destination acknowledging the permission to connect. |

```text
  Client                              Web Server
    │ ──────────  SYN  ───────────────▶ │
    │ ◀───────  SYN-ACK  ────────────── │  ← server reserves resources
    │ ──────────  ACK  ───────────────▶ │  ← handshake complete
```

In a SYN flood attack, a malicious actor sends many SYN packets all at once, which overwhelms the server's available resources to reserve for connections. When this happens, there are no server resources left for legitimate TCP connection requests.

The logs indicate that the web server has become overwhelmed and is unable to process the visitors' SYN requests. The server is unable to open a new connection to new visitors, who receive a connection timeout message.

---

<!-- ===================== MITRE ===================== -->
## 🗺️ MITRE ATT&CK Mapping

| Tactic | Technique | ID | Relevance |
| :--- | :--- | :--- | :--- |
| Impact | Endpoint Denial of Service: Service Exhaustion Flood | [T1499.002](https://attack.mitre.org/techniques/T1499/002/) | A flood of TCP SYN packets exhausted the web server's connection resources and made the website unavailable. |

---

<!-- ===================== MANAGEMENT ===================== -->
## 📣 Message for Management

> **Summary for my manager:** The company website went down because the web server was flooded with TCP SYN requests from an unfamiliar IP address (`203.0.113.0`). This is a SYN flood, a type of denial of service attack. The server ran out of resources to accept new connections, so employees and customers got connection timeout errors when trying to reach the sales page. I took the server offline so it could recover and blocked the attacking IP at the firewall. This block is only temporary, because attackers can switch to spoofed IP addresses. I recommend we discuss longer-term protections today.

---

<!-- ===================== FOLLOW-UPS ===================== -->
## ✅ Recommended Follow-Ups

- [x] Captured and analyzed the traffic to identify the attack.
- [x] Took the server offline to recover and blocked the attacking IP at the firewall.
- [x] Explained the attack type and its impact on the web server and employees.
- [ ] Recommended follow-up: enable SYN cookies or SYN flood protection on the web server and firewall.
- [ ] Recommended follow-up: set firewall rate limits on incoming SYN packets per source.
- [ ] Recommended follow-up: deploy IDS/IPS rules and traffic monitoring to flag SYN spikes early.
- [ ] Recommended follow-up: consider upstream DDoS protection from the internet provider or a mitigation service, since a spoofed attack can bypass IP blocking.

---

<!-- ===================== SKILLS ===================== -->
## 🧠 Skills Demonstrated

![Packet Analysis](https://img.shields.io/badge/Packet%20Analysis-0EA5E9?style=for-the-badge&labelColor=0D1117)
![TCP Handshake Analysis](https://img.shields.io/badge/TCP%20Handshake%20Analysis-1E90FF?style=for-the-badge&labelColor=0D1117)
![DoS Attack Identification](https://img.shields.io/badge/DoS%20Attack%20Identification-38BDF8?style=for-the-badge&labelColor=0D1117)
![Incident Containment](https://img.shields.io/badge/Incident%20Containment-0284C7?style=for-the-badge&labelColor=0D1117)
![Firewall Configuration](https://img.shields.io/badge/Firewall%20Configuration-334155?style=for-the-badge&labelColor=0D1117)
![Technical Communication](https://img.shields.io/badge/Technical%20Communication-475569?style=for-the-badge&labelColor=0D1117)

---

<!-- ===================== FOOTER ===================== -->
<div align="center">

### 📚 Explore More

**[👤 View My GitHub Profile](https://github.com/kentbalmoria7-oss)**

<sub>🛡️ <i>Detect early. Investigate thoroughly. Document everything.</i></sub>

</div>
