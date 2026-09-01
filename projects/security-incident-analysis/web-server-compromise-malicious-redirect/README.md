# Security Incident Analysis: Web Server Compromise and Malicious Redirect

## Overview

I investigated a simulated web-server compromise involving unauthorized administrative access, malicious source-code modification, a harmful executable, and redirection of website visitors to a second domain.

The investigation combined network traffic, source-code review, and downloaded-file analysis to reconstruct how a weak privileged account led to a broader application and end-user security incident.

## Incident Findings

A former employee gained administrative access through repeated password attempts against an account that still used a default credential.

After obtaining access, the attacker:

- Modified the website's source code
- Added JavaScript that prompted visitors to download an executable
- Changed the administrative password
- Caused affected users to be redirected to a second domain

Customers who ran the file reported slower computer performance, while the legitimate site owner lost access to the administrative panel.

## Technical Analysis

The network capture showed normal DNS, TCP, and HTTP communication with `yummyrecipesforme.com`, followed later by DNS resolution and a separate HTTP connection to `greatrecipesforme.com`.

Source-code review identified the JavaScript responsible for prompting the download, and analysis of the executable identified the redirect behavior.

Together, the evidence connected the privileged-account compromise to the malicious website changes and redirect activity.

## Root Cause and Impact

The primary security failure was weak privileged authentication.

A default administrative password remained in use, and protections against repeated authentication attempts were insufficient. Once the attacker obtained administrative access, the account's privileges allowed high-impact changes to the production website.

The incident resulted in:

- Unauthorized source-code modification
- Loss of legitimate administrative access
- Exposure of visitors to a malicious executable
- Redirection to a malicious domain
- Reported performance degradation on affected systems

## Security Recommendations

Priority improvements include:

- Require MFA for privileged accounts
- Eliminate default and weak credentials
- Apply authentication rate limiting, delays, or carefully configured temporary lockouts
- Monitor successful and failed administrative login attempts
- Apply least privilege
- Restrict administrative interfaces where practical
- Use HTTPS/TLS as part of broader web hardening

## Skills Demonstrated

- Security incident analysis
- Web-server compromise analysis
- Authentication security
- Brute-force attack analysis
- DNS, TCP, and HTTP traffic analysis
- tcpdump interpretation
- Evidence correlation
- Root-cause analysis
- Security remediation planning
- Technical documentation

## Completed Analysis

[View the completed incident analysis](./web-server-compromise-malicious-redirect-analysis.pdf)

## Project Context

This work was completed in a simulated educational environment. Network traffic, source-code evidence, and file-analysis evidence were provided for investigation; the technical interpretation, root-cause assessment, recommendations, and portfolio report reflect my work.
