# 📡 Log Sources Summary

## 🧭 Overview
This document provides an overview of the log sources ingested into the SIEM environment for monitoring and threat detection.  
The logs are collected from a simulated enterprise network that includes **user authentication systems, endpoint security tools, and network infrastructure**.  
Each log type contributes unique insights that, when correlated, support real-time threat detection and incident investigation.

---

## 🔍 1. Windows Security Event Logs
**Purpose:** Capture user login events, privilege escalations, and policy changes.  
**Source:** Domain Controllers, Workstations, and Servers.  

| Event ID | Description | Field Examples |
|-----------|--------------|----------------|
| 4624 | Successful Logon | `user`, `src_ip`, `logon_type`, `workstation_name` |
| 4625 | Failed Logon | `user`, `src_ip`, `failure_reason`, `attempt_count` |
| 4720 | User Account Created | `target_user`, `creator_user`, `timestamp` |
| 4672 | Special Privileges Assigned | `privilege_list`, `user`, `host` |

**Use Case Example:**  
Detect brute-force attempts by correlating multiple `4625` events from the same IP within a short time window.

---

## 🌐 2. Firewall Logs
**Purpose:** Record inbound and outbound network traffic to detect scanning, data exfiltration, and lateral movement attempts.  
**Source:** Perimeter firewall (e.g., pfSense, Cisco ASA).  

| Field | Description |
|--------|--------------|
| `src_ip` | Source IP Address |
| `dest_ip` | Destination IP Address |
| `dest_port` | Destination Port |
| `action` | Allowed / Denied |
| `bytes_out`, `bytes_in` | Traffic Volume |

**Use Case Example:**  
Identify port scanning activity by tracking sequential port connection attempts from the same source IP.

---

## 💻 3. Endpoint Detection Logs
**Purpose:** Provide visibility into endpoint processes, malware detections, and suspicious file executions.  
**Source:** EDR Platform (e.g., CrowdStrike, Microsoft Defender for Endpoint).  

| Field | Description |
|--------|--------------|
| `device_name` | Endpoint hostname |
| `process_name` | Executed process |
| `file_hash` | SHA256 hash of file |
| `alert_severity` | Low, Medium, High |
| `event_action` | Detected / Quarantined / Blocked |

**Use Case Example:**  
Correlate process creation logs with hash reputation to flag potential malware execution.

---

## 🌍 4. VPN & Authentication Logs
**Purpose:** Monitor remote access activity and detect login anomalies.  
**Source:** VPN Gateway, RADIUS, or SSO provider.  

| Field | Description |
|--------|--------------|
| `user` | Username |
| `src_ip` | Source IP (geolocation used for anomaly detection) |
| `auth_result` | Success / Failure |
| `country` | Geolocation of connection |
| `device_id` | Endpoint ID used to connect |

**Use Case Example:**  
Detect logins from unexpected countries or concurrent sessions from distant geolocations.

---

## 🕸️ 5. Web Server Access Logs
**Purpose:** Capture HTTP requests to identify unusual patterns, brute-force attempts, or injection attacks.  
**Source:** Apache / Nginx Web Servers.  

| Field | Description |
|--------|--------------|
| `client_ip` | Requesting IP |
| `http_method` | GET / POST / PUT |
| `url` | Requested URL |
| `response_code` | 200 / 404 / 500 |
| `user_agent` | Browser or bot signature |

**Use Case Example:**  
Correlate spikes in 404 or 403 responses to identify web scanning or unauthorized probing attempts.

---

## 🧠 Summary
Each log source contributes critical context to the SIEM:  
- **Windows Logs:** User behavior and authentication activity.  
- **Firewall Logs:** Network-level access and anomalies.  
- **Endpoint Logs:** Process-level visibility.  
- **VPN Logs:** Remote access and geolocation monitoring.  
- **Web Logs:** External attack surface visibility.  

By correlating across these sources, analysts can detect and investigate threats like:  
- Brute-force login attempts  
- Port scanning or lateral movement  
- Suspicious logins from foreign IPs  
- Web-based reconnaissance and exploitation  

---

📌 *This foundation enables the creation of accurate, high-fidelity correlation rules and dashboards for real-time network monitoring.*
