# Overview

This project is a hands-on Security Operations Center (SOC) homelab built using **Security Onion** to simulate real-world intrusion detection, log analysis, and incident response workflows.

The goal of this lab is to develop practical experience with network security monitoring tools and demonstrate the ability to detect, analyze, and document security events in an environment similar to what is used in MSP and enterprise settings.

## Technologies Used

* Security Onion
* Suricata (Network-based intrusion detection)
* Zeek (Traffic analysis & metadata logging)
* Wazuh (Host-based monitoring & alerting)
* Elasticsearch (Log storage & indexing)
* Kibana (Dashboards & investigation)

## Lab Architecture

```text
[Attacker VM] → [Virtual Network] → [Security Onion Sensor] → [Client VM]
```

## Components:

* **Security Onion VM** (Monitoring + SIEM)
* **Attacker Machine** (Kali Linux / testing tools)
* **Client Machine** (Ubuntu / Windows endpoint)

This setup simulates a monitored network where traffic is inspected and analyzed for malicious behavior.

## Deployment Summary

1. Downloaded and installed Security Onion ISO
2. Deployed as a virtual machine (VMware / VirtualBox)
3. Configured using `so-setup` in **Standalone Mode**
4. Assigned monitoring interface to capture network traffic
5. Accessed web interface via HTTPS for dashboards and alerts

## Detection Capabilities

### Network-Based Detection

* Signature-based threat detection via Suricata
* Detection of known attack patterns (e.g., scans, exploits)

### Behavioral Analysis

* Traffic metadata collection using Zeek
* Identification of unusual communication patterns

### Host-Based Monitoring

* File integrity monitoring
* Log analysis via Wazuh agents

## Simulated Attack Scenarios

### 1. Port Scan Detection

* **Tool Used:** Nmap
* **Description:** Simulated reconnaissance scan from attacker machine
* **Detection:**

  * Suricata generated alert for scan activity
  * Zeek logged connection attempts
* **Outcome:** Successfully identified source IP and scan behavior

### 2. Brute Force Login Attempt

* **Description:** Multiple failed authentication attempts
* **Detection:**

  * Alerts triggered for repeated login failures
  * Log correlation in dashboard
* **Outcome:** Identified suspicious login pattern and source

### 3. Suspicious Network Traffic

* **Description:** Simulated abnormal outbound traffic
* **Detection:**

  * Suricata signature alerts
  * Zeek logs for traffic analysis
* **Outcome:** Investigated traffic patterns and flagged anomalies

### 4. File Integrity Monitoring

* **Tool Used:** Wazuh
* **Description:** Modified system file on endpoint
* **Detection:**

  * Alert triggered for file change
* **Outcome:** Demonstrated host-based intrusion detection capability
  
## Incident Response Workflow

For each detected event:

1. Identify alert in dashboard (Kibana)
2. Analyze source/destination IP and behavior
3. Correlate logs across Suricata and Zeek
4. Determine severity and potential impact
5. Document findings and remediation steps


## Key Skills Demonstrated

* Network traffic analysis
* Intrusion detection (IDS/IPS concepts)
* Log analysis and correlation
* Incident investigation and documentation
* Security monitoring in a SOC-like environment

## Key Learnings

* Difference between **signature-based detection** and **behavioral analysis**
* Importance of **log correlation across multiple tools**
* How to identify and investigate suspicious network activity
* Real-world workflow of security monitoring and escalation

## Future Improvements

* Integrate pfSense for network segmentation
* Implement VLANs for multi-network simulation
* Forward logs to centralized SIEM pipeline
* Automate alert responses with scripts
* Expand attack scenarios (malware simulation, lateral movement)

## Screenshots

*(Add screenshots here of dashboards, alerts, and logs)*

## Purpose

This lab was built to strengthen my skills in:

* Security monitoring
* Network troubleshooting
* Incident response

and to prepare for real-world technical support and SOC responsibilities in MSP and enterprise environments.

