# 🔍 Introduction to Network Analysis

Network Analysis is like putting on X-ray glasses to see how computers, servers, and devices talk to each other behind the scenes. It helps professionals detect attacks, uncover misconfigurations, and understand network behavior.

---

## 👤 Who Needs Network Analysis?

### 🛡️ Threat Hunters

* Dig deep into **packet captures** to hunt threats and stealthy attacks (APTs).
* Must understand **custom and unusual protocols** that might hide malicious behavior.

### 👁️ SOC Analysts (Security Operations Center)

* Detect what’s *normal* vs *suspicious* on a network.
* Monitor unexpected behavior on **unusual ports** and respond fast to threats.

### 🚨 Incident Responders

* Quickly **identify, triage, and respond** to security incidents.
* Network knowledge is crucial to trace the **“how”** of an attack.

### 🧪 Threat Simulation Specialists / Penetration Testers

* Scan for **open ports** and **exploit network vulnerabilities**.
* Provide suggestions for tightening network security.

---

## 🧱 Common Network Devices (In Plain English)

| Device       | What It Does                                                              | Good To Know                 |
| ------------ | ------------------------------------------------------------------------- | ---------------------------- |
| **Router**   | Sends data to the right place using IP addresses                          | Think of it as a postman     |
| **Hub**      | Broadcasts data to **every device** on the network                        | Causes traffic & is insecure |
| **Switch**   | Smarter hub – sends data **only to the right device** using MAC addresses | Uses ARP                     |
| **Bridge**   | Combines two networks into one bigger network                             | Like joining two roads       |
| **Firewall** | Filters what comes in and out                                             | Can be hardware or software  |

---

## 🧩 Ports and Services – What’s Running Where?

| Port      | Protocol | What It Does                    | Security Tip                     |
| --------- | -------- | ------------------------------- | -------------------------------- |
| **20,21** | FTP      | Transfers files                 | No encryption by default         |
| **22**    | SSH      | Secure remote login             | Use instead of Telnet            |
| **23**    | Telnet   | Remote login (Old method)       | Avoid – no encryption            |
| **25**    | SMTP     | Sends emails between servers    | Requires POP/IMAP to read        |
| **53**    | DNS      | Converts domain names to IPs    | Often targeted in attacks        |
| **67,68** | DHCP     | Assigns IP addresses to devices | Essential for dynamic networking |
| **80**    | HTTP     | Loads websites (non-secure)     | Traffic is **not encrypted**     |
| **443**   | HTTPS    | Secure version of HTTP          | Uses TLS (previously SSL)        |