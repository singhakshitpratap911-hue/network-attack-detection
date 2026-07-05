# Network Traffic Analysis for Cyber Attack Detection

🚀 **A Research & Simulation Framework for Proactive Network Threat Mitigation**

This repository contains the core documentation, methodology, and architectural setup for our network anomaly detection project conducted during the Summer 2026 Training term at **United College of Engineering & Research (UCER), Prayagraj** (affiliated with **Dr. A.P.J. Abdul Kalam Technical University**).

---

## 👥 Authors & Collaborators
* **Akshit Pratap Singh** (Aspiring AI & ML Engineer)
* **Rishabh Seth** (Collaborator)
* **Supervised by:** Dr. Snehlata (Assistant Professor, Department of CSE)

---

## 🎯 Executive Summary
Traditional perimeter defenses often fail against attackers who blend malicious activity into legitimate network traffic. This project successfully engineered an isolated virtual lab environment to identify, log, and analyze the specific "digital fingerprints" left behind by high-risk network threat vectors. 

### 🔧 Technology Stack & Infrastructure
* **Virtualization:** Oracle VirtualBox / VMware (Isolated Host-Only Network Adapter)
* **Attacker Machine:** Kali Linux (Debian Architecture)
* **Target Host:** Windows OS Virtual Machine
* **Telemetry & Deep Packet Inspection:** Wireshark
* **Simulation Frameworks:** Nmap, Hping3, Hydra

---

## 🔍 Key Findings & Threat Matrices

By generating an operational baseline of regular traffic (DNS, TCP, ICMP), we created highly targeted filters to successfully isolate and document the signatures of three distinct attack phases:

| Attack Vector | Simulation Mechanism | Network Fingerprint & Indicator of Compromise (IoC) | Detection Method | Status |
| :--- | :--- | :--- | :--- | :--- |
| **Port Reconnaissance** | `Nmap -sS` (Stealth Scan) | High frequency of inbound half-open TCP SYN packets targeting non-sequential ports. | Signature-based rule validation | ✅ Verified |
| **Volumetric DoS** | `Hping3 --flood` | Unprecedented spike in network volume; massive influx of SYN packets with missing final ACKs (Half-Open connection memory depletion). | Wireshark I/O Graph Anomaly Spike | ✅ Verified |
| **Brute Force Exploits** | `Hydra (SMB Module)` | Authentication flooding targeting Port 445 over compressed intervals yielding repetitive `STATUS_LOGON_FAILURE` patterns. | Rule-based port tracking | ✅ Verified |

---

## 📂 Repository Structure
* `/docs`: Project abstract, certification documents, and the formal comprehensive report.
* `/captures`: Saved PCAP files for evaluating simulated threat data packets.

## 🔮 Future Enhancements
1. **Automated Incident Response:** Developing Python script wrappers using `Scapy` to automatically parse real-time capture logs.
2. **Machine Learning Integration:** Injecting LightGBM / behavioral models to optimize anomaly detection engine accuracy and scale out false positives.
3. **Adaptive Firewalls:** Synchronizing real-time alert triggers to update firewall blocklists instantly.