# Security Incident Response and Debian Server Hardering

End-to-end cybersecurity project focused on the forensic investigation of an unauthorised SSH intrusion, vulnerability assessment of a Debian web server, post-incident hardening, and the design of an incident response plan aligned with recognised security frameworks.

> Note: The project reports are currently available in Spanish.

## Overview

This repository documents a practical cybersecurity case study covering three main areas:

- **Digital forensics and incident investigation**
- **Grey-box pentesting and vulnerability validation**
- **Incident response planning and security improvement**

The project was developed as a final cybersecurity bootcamp deliverable and simulates the work of a security analyst investigating a compromised Debian-based web environment running services such as **SSH, Apache, WordPress, MariaDB, and FTP**.

## Objectives

- Investigate an unauthorised SSH access incident on a Debian server
- Analyse forensic evidence while preserving integrity and traceability
- Identify exposed services, insecure configurations, and exploitable weaknesses
- Apply hardening measures to reduce the attack surface
- Validate remediation actions through security testing
- Propose a structured incident response approach based on industry standards

## Project Scope

The assessment focuses on a Debian web server environment including:

- **Operating System:** Debian Linux
- **Web Services:** Apache HTTP Server, WordPress
- **Database:** MariaDB
- **Remote Access:** SSH
- **File Transfer Service:** vsftpd / FTP

## Methodology

This project combines forensic analysis, offensive security testing, and defensive remediation.

### 1. Forensic Investigation
The incident analysis followed principles from:

- **NIST SP 800-86**
- **ISO/IEC 27037**

Main activities included:

- Forensic image acquisition
- Hash verification for evidence integrity
- Log analysis with `journalctl`
- Review of shell history and system artefacts
- Rootkit and integrity checks using:
  - `chkrootkit`
  - `rkhunter`

### 2. Pentesting Assessment
The vulnerability assessment followed a structured grey-box approach inspired by:

- **PTES** (Penetration Testing Execution Standard)
- **OWASP Testing Guide**

Main activities included:

- Service discovery and enumeration
- Web directory and resource enumeration
- Vulnerability scanning
- Configuration review
- Controlled validation of findings
- Post-hardening verification

### 3. Security Improvement and Incident Response
The defensive phase included:

- SSH hardening
- Firewall configuration with UFW
- Permission correction on sensitive files
- Reduction of information disclosure
- Restriction of risky services and endpoints
- Development of an incident response plan aligned with:
  - **NIST SP 800-61**
  - **ISO/IEC 27001**

## Tools Used

### Forensics
- FTK Imager / ewfacquire
- Autopsy
- journalctl
- chkrootkit
- rkhunter

### Pentesting / Validation
- Nmap
- Gobuster
- Nikto
- WPScan
- Curl
- MySQL client
- SSH / ssh-keygen
- ss / iproute2

### Hardening / System Administration
- UFW
- Apache configuration
- SSH configuration
- Linux file permission controls

## Key Findings

The project identified critical weaknesses affecting authentication, configuration security, and web exposure. The investigation linked the incident to insecure SSH settings that allowed privileged remote access by password authentication.

The security assessment also revealed additional weaknesses related to:

- Weak credentials
- Insecure file permissions
- Anonymous FTP exposure
- Server information disclosure
- Directory listing exposure
- XML-RPC abuse risk in WordPress

After remediation, the environment was re-tested to confirm that the attack surface had been significantly reduced.

## Remediation Highlights

Implemented controls included:

- Disabling `PermitRootLogin`
- Disabling SSH password authentication
- Enforcing key-based SSH access
- Changing privileged credentials
- Restricting inbound access with UFW
- Correcting insecure file permissions
- Disabling anonymous FTP access
- Hiding Apache version information
- Blocking XML-RPC access
- Preventing public directory listing

## Repository Structure

```text
cybersecurity-incident-analysis/
│
├── Informe_Incidente_JoseM.pdf        # Forensic incident report
├── Informe_Pentesting_JoseM.pdf       # Pentesting and vulnerability assessment report
├── Plan_Respuesta_JoseM.pdf           # Incident response plan and SGSI proposal
├── Presentacion_Ejecutiva_JoseM.pdf   # Executive summary presentation
└── README.md
