
# 🦈 Wireshark Workflow (Network Traffic Analysis)

This workflow outlines the **typical process used to capture and analyze network traffic using Wireshark**.  
It is designed as a **practical step-by-step guide** for beginners learning packet analysis.

The goal of this workflow is to help you answer three important questions:

- **What** traffic is occurring?
- **Where** it is occurring (source and destination)
- **How** the communication is happening (protocols and data)

---

# 1️. Start Wireshark and Select a Network Interface

### What
Choose the network interface that is currently sending or receiving traffic.

### Where
Wireshark Home Screen → **Interface List**

### How
1. Launch Wireshark.
2. Look for interfaces showing network activity.
3. Double-click the interface you want to monitor.

Common interfaces include:

| Interface | Description |
|----------|-------------|
| `wifi` | Wireless interface |
| `eth0` | Ethernet connection |
| `wlan0` | Wireless network |
| `lo` | Loopback interface |

![Screenshot 2026-03-05 182431](https://github.com/user-attachments/assets/f37e654a-f268-4218-8028-6b86e9510a4b)


Once selected, Wireshark will begin **capturing packets in real time**.

---

# 2️. Generate Network Traffic

### What
Create network activity so Wireshark has packets to capture.

### How

Open a website:

```
https://example.com
```

Or generate traffic using terminal commands:

```bash
ping google.com
```
![Screenshot 2026-03-05 182734](https://github.com/user-attachments/assets/1c3518dc-c7c3-446e-b461-28f458c74e35)


This generates packets such as:

- DNS requests
- TCP connections
- HTTP or HTTPS traffic
- ICMP packets

---

# 3️. Stop Packet Capture

### What
Stop capturing packets so the data can be analyzed.

### Where
Top toolbar → **Stop Capture Button**
![Screenshot 2026-03-05 182859](https://github.com/user-attachments/assets/29532a6e-d8e0-478a-8581-9236ebacade6)


You now have a **packet capture file ready for analysis**.

---

# 4️. Review Captured Packets

Wireshark displays packets in a structured interface with three panels.

## Packet List
Shows a summary of captured packets.

| Field | Meaning |
|------|--------|
| No. | Packet number |
| Time | Time captured |
| Source | Sending host |
| Destination | Receiving host |
| Protocol | Network protocol |
| Length | Packet size |
| Info | Summary of packet |

Use this panel to quickly identify:

- active hosts
- common protocols
- communication patterns
  <img width="1324" height="766" alt="image" src="https://github.com/user-attachments/assets/982bb603-ab33-4b0d-bb81-8a7fba4a371f" />


---

## Packet Details
Shows the **protocol layers inside the selected packet**.

Example protocol structure:

```
Frame
Ethernet
Internet Protocol (IP)
Transport Protocol (TCP/UDP)
Application Protocol
```

This section helps identify:

- source and destination IP addresses
- port numbers
- protocol metadata
<img width="1419" height="537" alt="image" src="https://github.com/user-attachments/assets/cf947142-5fa4-4554-9eb4-534e29ca584e" />


---

## Packet Bytes
Displays the **raw hexadecimal packet data**.

This is useful for:

- deep protocol analysis
- malware investigation
- forensic analysis

---

# 5️. Apply Display Filters

Large packet captures can contain thousands of packets.

Display filters help focus on specific traffic.

### Where
Top filter bar labeled:

```
Apply a display filter
```
![Screenshot 2026-03-05 181343](https://github.com/user-attachments/assets/833d3eab-3f58-4956-96d9-80872e3396a9)



### Example Filters

| Filter | Purpose |
|------|---------|
| `dns` | Show DNS traffic |
| `http` | Show HTTP traffic |
| `tcp` | Show TCP packets |
| `icmp` | Show ping traffic |
| `ip.addr == <IP>` | Filter by IP address |

Example:

```
ip.addr == 192.168.1.10
```

Press **Enter** to apply the filter.

---

# 6️. Analyze Protocol Activity

### What
Identify which protocols are used in the capture.

### How
Look at the **Protocol column** in the packet list.

Common protocols include:

| Protocol | Purpose |
|---------|---------|
| DNS | Domain name resolution |
| TCP | Reliable communication |
| UDP | Fast connectionless communication |
| HTTP | Web traffic |
| TLS | Encrypted web traffic |
| ICMP | Network diagnostics |

![Screenshot 2026-03-05 233051](https://github.com/user-attachments/assets/ce73f885-a19e-4b9d-b6d9-b7f8071c2e63)


Understanding protocols helps determine **how systems communicate**.

---

# 7️. Follow Communication Streams

### What
Reconstruct the full communication between two hosts.

### Where
Right-click a packet →

```
Follow → TCP Stream
```

This shows the **complete conversation between the client and server**.

It can reveal:

- web requests
- data transfers
- login attempts
- application responses

---

# 8️. Analyze Network Conversations

### What
Identify which hosts communicate the most.

### Where

```
Statistics → Conversations
```

This shows:

- communicating IP pairs
- number of packets exchanged
- data transferred

Useful for detecting:

- suspicious connections
- abnormal communication patterns

---

# 9️. Review Protocol Statistics

### What
Understand which protocols dominate the capture.

### Where

```
Statistics → Protocol Hierarchy
```

This provides a breakdown of:

- protocol usage
- network behavior patterns

---

# . Extract Files from Captured Traffic

Wireshark can recover files transferred across the network.

### Where

```
File → Export Objects
```

Possible extracted items:

- images
- documents
- downloads
- executable files

This feature is commonly used in **forensic investigations**.

---

# 1️1️. Save the Capture File

### What
Save the packet capture for later analysis.

### Where

```
File → Save As
```

### File Format

```
capture.pcap
```

PCAP files can be analyzed later or shared with other network analysis tools.

---
- unauthorized communications
- data leaks
- malware activity
