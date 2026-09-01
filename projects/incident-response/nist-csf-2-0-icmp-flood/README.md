# NIST CSF 2.0 Incident Response Analysis: ICMP Flood Denial-of-Service

## Overview

I applied the NIST Cybersecurity Framework 2.0 to a simulated denial-of-service incident in which an ICMP flood disrupted an organization's internal network for approximately two hours.

The analysis connects the incident to the six CSF functions — Govern, Identify, Protect, Detect, Respond, and Recover — and translates each function into practical improvements for firewall configuration, monitoring, incident response, and service recovery.

## Incident Summary

A malicious actor flooded the organization's internal network with ICMP traffic, overwhelming network services and preventing employees from accessing normal resources.

Investigation identified inadequate firewall configuration as an important weakness.

The incident team contained the attack by blocking incoming ICMP traffic and temporarily taking non-critical services offline so critical services could be restored.

## NIST CSF 2.0 Analysis

### Govern

Establish clear ownership and standards for firewall configuration, security logging, network changes, and incident-response responsibilities.

### Identify

Maintain an accurate understanding of critical network services, their dependencies, and expected traffic patterns so unusual conditions can be recognized more quickly.

### Protect

Strengthen firewall configuration, rate-limit excessive ICMP traffic, permit only required communication, and use secure network baselines and segmentation to reduce unnecessary exposure.

### Detect

Use network monitoring, firewall logs, and IDS/IPS alerts to identify abnormal traffic before it develops into a major outage.

### Respond

Maintain a defined DoS response procedure covering containment, evidence preservation, service priorities, escalation, and communication.

### Recover

Restore critical services first, confirm that network performance has stabilized, validate new controls, and update response procedures based on lessons learned.

## Security Improvement Priorities

Three improvements deserve particular attention:

1. **Strengthen firewall configuration**  
   Maintain an approved firewall baseline, document how ICMP traffic should be handled, and review rules after significant changes or security events.

2. **Improve monitoring and alerting**  
   Establish normal traffic baselines and alert on significant deviations so abnormal ICMP activity can be investigated earlier.

3. **Prepare and test the response plan**  
   Maintain and periodically exercise a DoS response procedure covering containment, evidence collection, escalation, service priorities, and restoration.

## Skills Demonstrated

- NIST Cybersecurity Framework 2.0
- Incident response analysis
- ICMP flood analysis
- Denial-of-service response
- Firewall hardening
- Network monitoring and alerting
- IDS/IPS concepts
- Incident containment
- Business-service prioritization
- Recovery planning
- Security improvement planning
- Technical documentation

## Completed Analysis

[View the completed NIST CSF 2.0 incident analysis](./nist-csf-2-0-icmp-flood-incident-analysis.pdf)

## Project Context

This work was completed in a simulated educational environment. The incident scenario was provided; the NIST CSF 2.0 analysis, security priorities, and portfolio report reflect my work.
