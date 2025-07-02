# 🛠️ Analysis with Wireshark – Hands-On!

Wireshark is a free tool that lets you **capture and analyze real-time network traffic**. Great for beginners and pros alike.

### 🖥️ GUI Breakdown

#### 📌 Startup Screen

* **Start Capture**: Blue fin icon – begins live capture
* **Open Saved Files**: `.cap`, `.pcap`, or `.pcapng`
* **Capture Filter**: Capture only specific traffic (e.g., `tcp port 80`)
* **Interface Selection**: Choose the network adapter (WiFi, Ethernet, etc.)

> **Tip**: Enable **Promiscuous Mode** to capture all packets on the interface, not just those addressed to your machine.

#### 📊 Main Window Layout

1. **Menu Bar**: Start/stop/save/manage captures
2. **Display Filter**: Show only specific packets (e.g., `http.request`)
3. **Three Panes**:

   * **Packet List**: Shows summary (source, destination, protocol, length)
   * **Packet Details**: Expands layers (Ethernet, IP, TCP/UDP, etc.)
   * **Hex Dump**: Raw data + ASCII view (great for deep dive)

---

## 🎯 Capturing Live Traffic

* Start capture from the **startup screen**
* **Capture Filter** syntax (used before capture starts):

  * ✅ `tcp port 80` (for HTTP)
  * ❌ Not: `tcp.port == 80` (that's for display filter **after** capture)

#### Filtering by Protocol or Port:

* `host 192.168.1.10` – only packets from/to this IP
* `port 443` – only HTTPS
* `udp` – all UDP traffic

---

## 💾 Saving & Exporting Captures

* Click the **Red Square** to stop the capture
* Apply a **Display Filter** → `File > Export Specified Packets` → Save only what’s relevant

---

## 🔍 Analyzing PCAP Files (Post-Capture)

### Display Filters (Live or Loaded PCAPs)

| Filter                              | What It Shows                      |
| ----------------------------------- | ---------------------------------- |
| `udp`                               | Only UDP packets                   |
| `http.request`                      | Only HTTP requests                 |
| `tcp.port == 80`                    | HTTP traffic                       |
| `ip.dst_host == 192.168.1.7 && tcp` | TCP traffic going to a specific IP |
| `ntp or udp.port == 20000`          | Show NTP or specific UDP traffic   |
| `not ftp`                           | Exclude FTP packets                |

> Use **AND (`&&`)**, **OR (`||`)**, **NOT (`!`)**, and **brackets `()`** for complex filters.

#### Add Column for Any Field

* Right-click a field in **Packet Details** → **Apply as Column**

---

## 📈 Viewing Capture Statistics

Wireshark gives **summary views** to spot patterns and threats:

### 1. **Protocol Hierarchy**

* Shows how much of the traffic is HTTP, DNS, TCP, etc.
* Great to detect **unusual protocol activity** (e.g., high SMB traffic outside a Windows network)

### 2. **Conversations**

* Shows **talking pairs** (IP to IP, port to port)
* Can spot suspicious one-way data exfiltration

### 3. **Endpoints**

* Lists all IPs/devices involved
* Shows total data **sent vs received**
