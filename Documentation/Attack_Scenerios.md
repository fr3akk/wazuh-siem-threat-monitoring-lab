# Attack Scenarios

## Scenario 1

Reconnaissance using Nmap

Command:

nmap -Pn -A 10.0.2.3

Result:

Wazuh generated discovery activity alerts.

---

## Scenario 2

Failed Login Attempts

Command:

runas /user:Administrator cmd

Result:

Authentication failure events detected by Wazuh.

---

## Scenario 3

PowerShell Activity

Executed PowerShell commands to generate Sysmon telemetry.

Result:

PowerShell activity captured and analyzed through Wazuh.