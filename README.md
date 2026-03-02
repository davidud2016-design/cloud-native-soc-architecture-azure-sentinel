# cloud-native-soc-architecture-azure-sentinel
Monitoring Active Directory with Microsoft Sentinel: Detecting Identity Attacks in Real Time,Building a Cloud-Native SOC with Microsoft Sentinel: From Log Ingestion to Automated Response,Correlating Vulnerability Management with Live Threat Detection in Microsoft Sentinel
## Overview

This repository documents the design and implementation of a cloud-native Security Operations Center (SOC) architecture built using:

- Microsoft Sentinel (SIEM & SOAR)
- Active Directory (Hybrid Identity)
- Azure Log Analytics
- Azure Monitor Agent
- Vulnerability Telemetry (Defender TVM / OpenVAS)
- Custom KQL Detection Engineering
- Automated Response Playbooks

The objective of this project was to simulate a realistic enterprise security operations environment that integrates identity monitoring, detection engineering, vulnerability correlation, and automated incident response.

---

## Architecture Components

- Active Directory Domain Controller
- Domain-Joined Windows Endpoints
- Azure Monitor Agent (AMA)
- Log Analytics Workspace
- Microsoft Sentinel
- Vulnerability Scanner
- SOAR Playbooks

---

## Project Sections

### 1. Identity Monitoring
Advanced Active Directory auditing and real-time detection of:
- Brute force attacks
- Privilege escalation
- Suspicious PowerShell execution

### 2. Detection Engineering
Custom KQL queries for:
- Correlated authentication failures
- Risky Azure AD sign-ins
- Behavioral detection use cases

### 3. Vulnerability Correlation
Correlation of:
- High-severity Sentinel alerts
- Critical unpatched vulnerabilities

Enabling risk-based prioritization.

### 4. Automated Response
SOAR playbooks for:
- Disabling compromised users
- Blocking malicious IP addresses
- Escalating high-risk vulnerable assets

---

## Architecture Diagram

```mermaid
flowchart TD
    Users --> Endpoint
    Endpoint --> DomainController
    DomainController --> AMA
    Endpoint --> AMA
    AMA --> LogAnalytics
    LogAnalytics --> Sentinel
    Sentinel --> Analytics
    Analytics --> Incidents
    Incidents --> Playbooks
    Playbooks --> Response

    Endpoint --> VulnerabilityScanner
    VulnerabilityScanner --> Sentinel
