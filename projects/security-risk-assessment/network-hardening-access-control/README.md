# Security Risk Assessment: Network Hardening and Access Control

## Overview

I completed a simulated post-breach security assessment focused on authentication, privileged access, firewall configuration, and network access control.

The goal was not to reconstruct the original breach, but to identify weaknesses that could make another unauthorized-access incident more likely or more damaging.

## Key Risks

The assessment identified four significant weaknesses:

- Employees shared passwords
- A privileged database account retained a default password
- Firewall traffic-filtering rules were not configured
- Multi-factor authentication was not enforced

Together, these weaknesses increased exposure across identity security, privileged access, and network control.

## Recommended Controls

### Identity and Authentication

- Replace default privileged credentials
- Eliminate shared accounts and assign individual credentials
- Require long, unique passwords
- Use an approved password manager where appropriate
- Require MFA for administrative, privileged, and remote access

### Firewall and Network Access

- Establish a documented firewall baseline
- Use deny-by-default filtering where appropriate
- Permit only required business traffic
- Restrict unnecessary ports, protocols, sources, and destinations
- Give additional protection to systems containing sensitive customer data

### Privileged Access

- Apply least privilege
- Use role-based access control
- Use access-control lists where appropriate
- Separate privileged administration from routine user activity

## Implementation Priorities

Immediate remediation should focus on:

- Replacing the default database administrator credential
- Rotating shared credentials
- Moving employees to individual accounts
- Enabling MFA for privileged access
- Establishing baseline firewall rules

## Ongoing Maintenance

The controls should remain actively maintained through:

- Access reviews
- Permission changes when employees change roles or leave
- Firewall-rule reviews
- Authentication and firewall logging
- Password changes after suspected compromise
- Periodic verification that access is still required

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
- Technical documentation

## Completed Assessment

[View the completed risk assessment](./network-hardening-security-risk-assessment.pdf)

## Project Context

This work was completed in a simulated educational environment. The scenario and identified security weaknesses were provided; the risk analysis, control recommendations, prioritization, and portfolio report reflect my work.
