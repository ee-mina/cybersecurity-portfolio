# Incident Response & Investigation Journal

## Overview

This project is a reusable incident-response journal built to document investigations in a consistent way.

Each entry records the incident context, evidence reviewed, tools and data sources used, findings, analyst decisions, and any follow-up or escalation needed. The goal is to make investigative work easy to understand, continue, and review later.

The journal currently contains four simulated investigations covering ransomware, malware analysis, phishing triage, and IDS alert analysis.

## Journal Entries

### 1. Ransomware Incident at a Health Care Clinic

Reviewed a ransomware incident that began with a phishing email containing a malicious attachment.

The investigation documented the initial access method, operational impact, available evidence, and next response steps, including containment, evidence preservation, and recovery planning.

### 2. Suspicious File Hash Investigation

Investigated a suspicious file hash using VirusTotal.

Vendor detections, behavioral information, network indicators, and related threat intelligence were correlated to classify the file as malicious and document associated indicators for further investigation or threat hunting.

### 3. Phishing Alert Triage and Escalation

Reviewed a phishing alert involving a suspicious email and executable attachment.

The decision to escalate was based on multiple indicators, including sender inconsistencies, message content, attachment type, and a known malicious file hash.

### 4. Suricata IDS Alert and Log Analysis

Analyzed packet-capture data with Suricata using a custom detection rule.

Generated alerts were reviewed in `fast.log` and `eve.json`, and `jq` was used to filter JSON event data and isolate useful fields such as timestamps, flow IDs, signatures, protocols, and destination addresses.

## Investigation Approach

The journal uses a consistent structure for each case:

- Incident or case identification
- Severity and status
- Incident description
- NIST incident response phase
- Tools and data sources
- The 5 W's
- Evidence and findings
- Actions and decisions
- Next steps or escalation
- Additional analyst notes

Using the same structure across different incident types makes it easier to preserve investigative context and clearly document why a decision was made.

## Skills Demonstrated

- Incident documentation
- Incident investigation
- Phishing alert triage
- Security alert escalation
- Malware and file-hash analysis
- Indicator-of-compromise analysis
- VirusTotal analysis
- Suricata IDS analysis
- Security log analysis
- JSON log filtering with `jq`
- Evidence correlation
- NIST incident response concepts
- Technical documentation

## Completed Journal

[View the completed incident response journal](./incident-response-investigation-journal.pdf)

## Project Context

This journal contains simulated educational investigations. The scenarios and activity materials were provided; the evidence review, interpretation, documentation, investigative decisions, and follow-up recommendations presented in the journal reflect my work.
