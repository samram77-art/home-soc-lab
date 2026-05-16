# Home SOC Lab

This project documents my beginner Security Operations Center (SOC) home lab built with Windows 10, Sysmon, and Wazuh in a virtual environment. The goal is to practice endpoint visibility, alert monitoring, detection engineering, and basic incident investigation in a safe lab environment.

## Project Goals

- Build a simple SOC-style monitoring environment at home
- Collect endpoint telemetry from a Windows machine
- Forward logs to a central monitoring platform
- Investigate common security events
- Document detections and incident response workflows

## Lab Stack

- VirtualBox
- Windows 10 VM
- Ubuntu Server VM
- Wazuh Manager
- Wazuh Agent
- Sysmon

## Architecture

The lab uses one Windows 10 endpoint and one Ubuntu server running Wazuh.

- Windows 10 VM generates endpoint and security logs
- Sysmon provides process creation and other useful telemetry
- Wazuh Agent forwards logs from the Windows endpoint
- Wazuh Manager centralizes logs and displays alerts

## Detection Scenarios

This lab currently includes three beginner-friendly detection scenarios:

1. Multiple failed login attempts
2. Suspicious PowerShell execution
3. New local user account creation

## Why These Scenarios

These events are useful because they are common, easy to reproduce in a lab, and relevant to entry-level SOC work.

- Failed login attempts can indicate brute-force activity, password guessing, or service misconfiguration
- Suspicious PowerShell activity is often relevant in attacker tradecraft and admin abuse investigations
- New account creation events may indicate unauthorized persistence or risky changes

## Event References

The following Windows and Sysmon events were used in this lab:

- Event ID 4625: Failed logon
- Event ID 4720: User account created
- Sysmon Event ID 1: Process creation

## Repository Structure

```text
home-soc-lab/
├── README.md
├── architecture/
├── setup/
├── detections/
├── writeups/
└── notes/
```

## Setup Summary

1. Create a Windows 10 VM
2. Create an Ubuntu Server VM
3. Install Wazuh on Ubuntu
4. Install Sysmon on Windows
5. Install the Wazuh agent on Windows
6. Confirm logs are flowing into the Wazuh dashboard
7. Trigger and investigate the three detection scenarios

## Screenshots To Add

Add screenshots after building the lab:

- Wazuh dashboard overview
- Wazuh agent connected
- Sysmon logs present on Windows
- Failed login event alert
- Suspicious PowerShell event
- Account creation event
- Event drill-down view

## Key Skills Demonstrated

- Endpoint monitoring
- Log analysis
- Windows event investigation
- Detection engineering basics
- Security documentation
- SOC workflow practice

## Notes

This project was built for educational and defensive purposes only. All activity was performed in a controlled local lab environment that I owned and configured myself.
