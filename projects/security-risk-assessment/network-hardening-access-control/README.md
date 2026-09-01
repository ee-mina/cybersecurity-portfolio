# Security Risk Assessment: Network Hardening and Access Control

## Overview

This project demonstrates a simulated post-breach security risk assessment focused on identity security, access control, and network hardening.

I reviewed the organization's known security weaknesses, assessed how they could increase the likelihood or impact of future unauthorized access, and developed prioritized controls for reducing exposure.

The available information did not establish which weakness caused the original breach, so the assessment focuses on future risk reduction rather than assigning an unsupported root cause.

## Risk Assessment Summary

The organization had previously experienced a breach involving customer personal information.

The assessment identified four significant weaknesses:

- Shared employee passwords
- A default database administrator password
- Missing firewall traffic-filtering rules
- No enforced multi-factor authentication

Together, these weaknesses created unnecessary exposure across authentication, privileged access, and network security.

## Identified Vulnerabilities

### Shared Employee Passwords

Credential sharing reduces individual accountability and increases the risk that unauthorized users could gain access through another person's credentials.

### Default Database Administrator Password

A privileged database account still used a default password, creating unnecessary exposure to unauthorized access if the credential were known or guessed.

### Missing Firewall Filtering Rules

Without an established firewall filtering policy, the organization lacked adequate control over which inbound and outbound network connections should be permitted or denied.

### No Multi-Factor Authentication

Password-only authentication meant that a stolen, shared, or successfully guessed password could be sufficient to access an account.

## Recommended Hardening Controls

### Identity and Authentication

- Replace the default database administrator password
- Replace shared credentials with individual user accounts
- Require long, unique passwords
- Use an approved password manager where appropriate
- Require MFA, beginning with administrative, privileged, and remote-access accounts

### Firewall Policy and Traffic Filtering

Configure firewall rules using a deny-by-default approach, permitting only traffic required for approved business services.

Inbound and outbound rules should restrict unnecessary:

- Ports
- Protocols
- Sources
- Destinations

Additional attention should be given to systems that store or process sensitive customer information.

### Least Privilege and Network Access Control

Access to databases, administrative interfaces, and other sensitive resources should be limited to users, roles, and systems with a legitimate business need.

Controls should include:

- Least privilege
- Role-based access control
- Access-control lists
- Separation of privileged access from ordinary user activity

## Implementation Priorities

Immediate actions should include:

- Replace the default database administrator credential
- Rotate credentials known to have been shared
- Assign individual user accounts
- Enable MFA for privileged access
- Establish baseline firewall rules permitting only required traffic

## Ongoing Maintenance

Security controls should remain actively maintained after initial implementation.

Recommended ongoing practices include:

- Continuously enforce MFA and access restrictions
- Review firewall rules after major network or service changes
- Review firewall rules after relevant security events
- Perform scheduled firewall-rule reviews
- Review permissions when employees change roles or leave
- Periodically verify continued access requirements
- Change passwords when compromise is known or suspected
- Log and monitor authentication activity
- Log and monitor firewall activity

## Skills Demonstrated

- Security risk assessment
- Network hardening
- Access-control analysis
- Identity and authentication security
- Multi-factor authentication
- Firewall policy development
- Traffic-filtering analysis
- Least privilege
- Role-based access control
- Access-control lists
- Remediation prioritization
- Security control maintenance
- Technical documentation

## Completed Assessment

[View the completed risk assessment](./network-hardening-security-risk-assessment.pdf)

## Project Context

This project was completed in a simulated educational environment. The scenario and identified organizational weaknesses were provided for assessment; the risk analysis, control recommendations, implementation priorities, and portfolio report presented here reflect my work.
