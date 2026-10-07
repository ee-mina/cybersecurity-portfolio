# Vulnerability Assessment: Public Database Server

## Overview

I assessed the security risk of a remote database server used by a simulated e-commerce company. Because the server was accessible from the public internet, I focused on its access controls and the potential impact to the confidentiality, integrity, and availability of the information it stored.

The risk analysis was guided by NIST SP 800-30 Rev. 1.

## Assessment Scope

The server ran Linux and hosted a MySQL database that employees used remotely to work with prospective-customer information.

The assessment focused on:

- Database access controls
- Unauthorized access
- Information exposure
- Unauthorized data modification
- Database availability

Physical security and unrelated organizational systems were outside the scope of the assessment.

## Risk Analysis

I evaluated three threat scenarios using qualitative likelihood and severity scores from 1 to 3.

Overall risk was calculated as:

`Likelihood × Severity = Risk`

| Threat Source | Threat Event | Likelihood | Severity | Risk |
|---|---|---:|---:|---:|
| External hacker | Disrupt database availability | 2 | 2 | 4 |
| Competitor | Copy prospective-customer information for competitive advantage | 2 | 1 | 2 |
| Competitor | Alter prospective-customer information to disrupt operations and gain competitive advantage | 2 | 2 | 4 |

The database's public exposure increased the likelihood of security events, but I avoided assuming that existing authentication could easily be bypassed or that every scenario would cause severe organizational harm.

That kept the scoring tied to the information actually available rather than automatically assigning the highest possible risk.

## Remediation Priorities

The main recommendation is to remove unnecessary public exposure and restrict access to the database.

Appropriate controls include:

- Firewall restrictions
- IP allow-listing
- VPN-based remote access where appropriate
- Role-based access control
- Least privilege
- Multi-factor authentication
- Logging and monitoring of access and changes
- Periodic reviews of security controls
- TLS with securely managed certificates and keys

These controls would reduce unnecessary exposure while making unauthorized access or changes easier to prevent and detect.

## Skills Demonstrated

- Vulnerability assessment
- NIST SP 800-30 Rev. 1
- Qualitative risk analysis
- Threat-scenario analysis
- Likelihood and severity scoring
- Confidentiality, integrity, and availability analysis
- Database access-control assessment
- Risk-based remediation planning
- Technical documentation

## Completed Assessment

[View the completed vulnerability assessment](./vulnerability-assessment-public-database-server.pdf)

## Project Context

This work was completed in a simulated educational environment. The system scenario and assessment requirements were provided; the risk analysis, scoring decisions, remediation recommendations, and portfolio report reflect my work.
