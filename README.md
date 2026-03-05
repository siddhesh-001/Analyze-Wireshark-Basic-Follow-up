#  Key Things to Identify in Wireshark

When analyzing traffic in **Wireshark**, focus on identifying a few core elements that explain **who is communicating, what is happening, and how it is happening**.

---

## 1️. Source and Destination
Identify **which devices are communicating**.

| Field | Meaning |
|------|--------|
| Source | Sender of the packet |
| Destination | Receiver of the packet |

Questions to ask:
- Is the communication internal or external?
- Is the destination expected?

---

## 2️. Protocol
The **protocol column** shows how devices are communicating.

Common protocols:

| Protocol | Purpose |
|--------|---------|
| DNS | Domain resolution |
| TCP | Reliable communication |
| UDP | Fast connectionless communication |
| HTTP | Web traffic |
| TLS | Encrypted web traffic |
| ICMP | Network diagnostics |

---

## 3️. Ports
Ports indicate **which service or application is being used**.

| Port | Service |
|-----|---------|
| 80 | HTTP |
| 443 | HTTPS |
| 53 | DNS |
| 22 | SSH |
| 21 | FTP |

Look for unusual or unexpected ports.

---

## 4️. Traffic Patterns
Observe communication behavior such as:

- repeated connections
- bursts of traffic
- frequent DNS queries

These patterns may indicate abnormal activity.

---

## 5️. Domain Requests
DNS packets reveal **which domains a system is contacting**.

Check for:
- unknown domains
- suspicious domain names
- unexpected external connections

---

## 6️. Data Transfers
Watch for:

- file downloads
- large data transfers
- repeated data exchanges

This can reveal possible **data exfiltration or downloads**.

---

##  Quick Analysis Checklist

When reviewing packets, ask:

- Who is communicating?
- What protocol is used?
- Which ports are involved?
- Is the communication normal?
- Are suspicious domains present?
- Is the traffic encrypted?

Start by examining:

```
Source
Destination
Protocol
```

These fields provide the **fastest overview of network activity**.
