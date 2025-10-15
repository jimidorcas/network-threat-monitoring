# 🔍 Network Threat Monitoring & Alert Correlation (SIEM Focus)

## 📘 Overview
This project demonstrates how a Security Operations Center (SOC) analyst monitors, detects, and investigates suspicious network activity using a **Security Information and Event Management (SIEM)** system.  
It focuses on **log correlation, rule tuning, and alert prioritization**, simulating a real-world network monitoring workflow aligned with **NIST** and **MITRE ATT&CK** frameworks.

---

## 🎯 Objectives
- Configure and test SIEM correlation rules for detecting common network threats.  
- Create dashboards to visualize user activity, failed logins, and network anomalies.  
- Perform alert analysis to distinguish false positives from genuine incidents.  
- Recommend improvements to detection logic and response workflows.  

---

## 🗂️ Repository Structure
network-threat-monitoring/
├─ README.md
├─ data-sources/
│ └─ log_summary.md
├─ detection-rules/
│ ├─ brute_force_rule.spl
│ ├─ port_scan_rule.spl
│ └─ suspicious_login_rule.spl
├─ dashboards/
│ ├─ dashboard_overview.md
│ └─ screenshot_placeholders/
│ ├─ login_alert_dashboard.png
│ └─ network_activity_summary.png
└─ reports/
├─ alert_analysis_report.md
└─ tuning_recommendations.md


---

## 🧩 Project Components

### 📡 Data Sources
[**log_summary.md**](data-sources/log_summary.md)  
Description of ingested log sources (e.g., Windows Event Logs, Firewall, Authentication, Web Server). Includes sample log formats and key fields used for correlation.

---

### ⚙️ Detection Rules
[**detection-rules/**](detection-rules/)  
Custom SIEM correlation rules written in **Splunk SPL** for:  
- Brute-force login detection  
- Port scanning activity  
- Suspicious logins outside standard hours  

---

### 📊 Dashboards
[**dashboards/**](dashboards/)  
Screenshots and descriptions of network activity dashboards used to visualize alerts, user behavior, and detection metrics.  

---

### 📑 Reports
[**reports/**](reports/)  
Contains analysis of triggered alerts, investigation notes, and tuning recommendations to improve rule precision and SOC efficiency.  

---

## 🧠 Skills Demonstrated
- SIEM Configuration & SPL Query Writing  
- Network Log Correlation & Alert Investigation  
- Incident Prioritization & Reporting  
- Dashboard Creation & Visualization  
- Detection Rule Tuning & Optimization  
- Familiarity with MITRE ATT&CK & NIST IR Frameworks  

---

