# 🛡️ Wazuh SIEM Threat Monitoring Lab

A hands-on cybersecurity lab designed to simulate real-world attack activity and investigate security events using Wazuh SIEM, Sysmon, Windows 10, and Kali Linux.

This project demonstrates how security analysts can monitor endpoint activity, detect suspicious behavior, investigate alerts, and perform threat hunting within a controlled environment.

---

## 📖 Project Overview

Security Information and Event Management (SIEM) platforms are widely used by Security Operations Centers (SOCs) to collect logs, detect threats, and investigate incidents.

In this project, a complete SIEM lab was built from scratch using virtual machines. A Windows 10 endpoint was monitored using Sysmon and the Wazuh Agent, while a Kali Linux machine simulated attacker activity. The generated security events were collected and analyzed through a centralized Wazuh server.

The objective was to gain practical experience with:

- SIEM deployment and administration
- Endpoint monitoring
- Security event analysis
- Threat hunting
- Alert investigation
- Attack simulation

---

# 🎯 Objectives

- Deploy and configure a Wazuh SIEM environment
- Configure Sysmon for enhanced endpoint visibility
- Generate realistic attack activity from Kali Linux
- Collect and analyze security logs
- Investigate alerts using Wazuh dashboards
- Understand the detection lifecycle used in SOC environments

---

# 🏗️ Lab Architecture

```text
┌─────────────────┐
│ Kali Linux VM   │
│ Attacker        │
│ IP: 10.0.2.4    │
└────────┬────────┘
         │
         │ Nmap Scan
         │ SYN Scan
         │ Reconnaissance
         ▼
┌─────────────────┐
│ Windows 10 VM   │
│ Victim Endpoint │
│ IP: 10.0.2.3    │
│ Wazuh Agent     │
│ Sysmon          │
└────────┬────────┘
         │
         │ Security Logs
         │ Sysmon Events
         │ Authentication Logs
         ▼
┌─────────────────┐
│ Wazuh Server    │
│ Ubuntu 24.04    │
│ IP: 10.0.2.15   │
│ Wazuh Manager   │
│ Threat Hunting  │
│ Vulnerability   │
│ Detection       │
└─────────────────┘

Network: VirtualBox NAT Network (10.0.2.0/24)
```

---

# ⚙️ Technologies Used

| Technology | Purpose |
|------------|----------|
| Wazuh | SIEM Platform |
| Sysmon | Endpoint Monitoring |
| Windows 10 | Monitored Endpoint |
| Kali Linux | Attack Simulation |
| Ubuntu Server 24.04 | Wazuh Manager |
| Nmap | Reconnaissance Testing |
| PowerShell | Discovery Commands |
| VirtualBox | Virtual Lab Environment |

---

# 🔍 Attack Scenarios

## 1. Reconnaissance Activity

Network reconnaissance was performed from the Kali Linux machine against the Windows endpoint using Nmap.

### Commands Used

```bash
nmap -Pn 10.0.2.3

nmap -Pn -sS 10.0.2.3

nmap -Pn -A 10.0.2.3
```

### Observations

- Host discovery detected
- Reconnaissance activity generated
- Discovery-related security events observed in Wazuh

### Screenshots

- Kali IP Verification
- Nmap SYN Scan
- Nmap Aggressive Scan
- Wazuh Detection Dashboard

---

## 2. PowerShell Discovery Activity

Several PowerShell commands commonly used during system enumeration were executed.

### Commands Used

```powershell
whoami

hostname

ipconfig

net user
```

### Observations

- PowerShell execution logged
- Discovery activity detected
- Security events correlated through Wazuh

### Screenshots

- Discovery Commands
- PowerShell Activity Detection

---

## 3. Failed Authentication Attempts

Multiple failed login attempts were generated to simulate authentication-related security events.

### Command Used

```cmd
runas /user:Administrator cmd
```

### Observations

- Failed authentication events detected
- Unknown user or bad password alerts generated
- Security logs successfully forwarded to Wazuh

### Screenshots

- Failed Login Attempts
- Authentication Failure Detection

---

## 4. Sysmon-Based Endpoint Monitoring

Sysmon was configured to provide enhanced visibility into endpoint activity.

### Monitored Events

- Process Creation
- Network Connections
- File Creation
- Registry Activity
- Authentication Events
- Suspicious Process Execution

### Verification

```powershell
Get-WinEvent -LogName "Microsoft-Windows-Sysmon/Operational" -MaxEvents 10
```

### Screenshots

- Sysmon Verification
- Sysmon Security Events in Wazuh
- Threat Hunting Dashboard

---

# 📊 Key Results

### Successful Event Collection

✔ Windows Event Logs

✔ Sysmon Logs

✔ Authentication Events

✔ PowerShell Activity

✔ Discovery Commands

✔ Reconnaissance Activity

---

### Security Monitoring

✔ Real-time Event Collection

✔ Threat Hunting Dashboard

✔ Security Alert Generation

✔ Endpoint Visibility

✔ Centralized Log Management

---

# 📸 Screenshots Included

| Screenshot | Description |
|------------|-------------|
| architecture-diagram.png | Lab Architecture |
| Wazuh_Agent_Connected.png | Agent Registration |
| Wazuh_Agent_Details.png | Endpoint Details |
| kali_ip.png | Kali IP Verification |
| windows_ip.png | Windows IP Verification |
| wazuh_ip.png | Wazuh Server IP Verification |
| SYN_attack.png | SYN Scan Activity |
| Reconnaissance_Activity.png | Aggressive Nmap Scan |
| Discover_Commands.png | PowerShell Enumeration |
| Failed_Login_Attempts.png | Authentication Failures |
| Sysmon_Verification.png | Sysmon Validation |
| Wazuh_Detection_Dashboard.png | Security Event Detection |
| Threat_Hunting_Dashboard.png | Threat Hunting View |

---

# 📂 Repository Structure

```text
wazuh-siem-threat-monitoring-lab/
│
├── architecture/
│   └── architecture-diagram.png
│
├── screenshots/
│   ├── Agent_Connected.png
│   ├── Agent_Details.png
│   ├── Reconnaissance.png
│   ├── SYN_Scan.png
│   ├── Failed_Logins.png
│   ├── Sysmon_Verification.png
│   └── Threat_Hunting.png
│
├── configs/
│   └── sysmonconfig.xml
│
├── documentation/
│   ├── Setup_Guide.md
│   ├── Attack_Scenarios.md
│   └── Findings.md
│
└── README.md
```

---

# 🧠 Skills Demonstrated

### Security Operations (SOC)

- SIEM Administration
- Threat Hunting
- Alert Investigation
- Event Correlation
- Security Monitoring

### Endpoint Security

- Sysmon Configuration
- Windows Event Analysis
- Endpoint Visibility

### Networking

- Network Reconnaissance
- Port Scanning
- Network Enumeration

### Detection Engineering

- Log Collection
- Rule-Based Detection
- Security Event Analysis

### Documentation

- Security Reporting
- Architecture Design
- Technical Documentation

---

# 🚀 Future Improvements

- Integrate Suricata IDS
- Add Active Response Rules
- Create Custom Wazuh Detection Rules
- Implement Email Alerting
- Simulate Additional MITRE ATT&CK Techniques
- Expand Threat Hunting Use Cases

---

# 📚 Key Learning Outcomes

Through this project, I gained practical experience building and operating a SIEM environment from scratch. The lab provided exposure to security monitoring, attack simulation, endpoint visibility, threat hunting, and incident investigation workflows commonly used by Security Operations Center (SOC) analysts.

This project reflects hands-on experience with defensive cybersecurity technologies and demonstrates the ability to deploy, configure, monitor, and investigate security events within a controlled environment.

---

# 👨‍💻 Author

**Ayush**

Cybersecurity Enthusiast | SIEM | Threat Hunting | Blue Team Operations

GitHub: https://github.com/fr3akk

---

## ⭐ If you found this project useful, consider starring the repository.