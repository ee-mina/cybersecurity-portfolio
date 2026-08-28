# Security Incident Analysis: Web Server Compromise and Malicious Redirect

## Overview

This project examines a simulated web-server compromise in which unauthorized administrative access led to malicious source-code modification, distribution of a harmful executable, and redirection of website visitors to a second domain.

I analyzed packet-capture evidence alongside source-code and downloaded-file findings to reconstruct the incident, identify the root cause, assess the impact, and recommend security improvements.

## Incident Summary

A former employee gained unauthorized administrative access to a website through a brute-force attack against an account that was still using a default password.

After gaining access, the attacker:

- Modified the website's source code
- Added malicious JavaScript prompting visitors to download an executable file
- Changed the administrative password
- Caused affected visitors to be redirected to another domain

Users who ran the downloaded file reported slower computer performance, while the website owner lost access to the administrative panel.

## Technical Analysis

The packet capture showed the client first resolving and connecting to the legitimate website.

Observed activity included:

- DNS resolution for `yummyrecipesforme.com`
- Resolution to `203.0.113.22`
- TCP connection to HTTP port 80
- Standard TCP three-way handshake
- HTTP `GET / HTTP/1.1` request

Later, the client performed a separate DNS lookup for `greatrecipesforme.com`, which resolved to `192.0.2.172`, followed by a new TCP connection to port 80.

The packet capture confirmed communication with the second domain but did not independently establish why the redirect occurred.

Source-code review identified malicious JavaScript responsible for prompting the download, while analysis of the downloaded file identified redirect functionality. Together, these findings connected the web-server compromise to the malicious redirect.

## Root Cause

The primary cause of the incident was weak privileged-account security.

The administrative account still used a known default password, and protections against repeated authentication attempts were insufficient. This allowed the attacker to successfully guess the credential and obtain administrative access.

Because the compromised account had permission to modify the website, the attacker was able to make high-impact changes after authentication.

## Impact

The compromise resulted in:

- Unauthorized modification of production source code
- Loss of administrative access for the legitimate website owner
- Exposure of visitors to a malicious executable
- Redirection of users to a malicious domain
- Reported degradation of affected users' computer performance
- Increased application and end-user security risk

## Security Recommendations

Recommended remediation includes:

- Require MFA for privileged accounts
- Eliminate default and weak credentials
- Apply authentication rate limiting or temporary lockouts
- Monitor successful and failed administrative authentication attempts
- Apply least privilege and reduce unnecessary administrative exposure
- Use HTTPS/TLS to strengthen protection of web traffic in transit

HTTPS would improve the site's overall security but would not prevent the brute-force credential attack that caused this incident.

## Skills Demonstrated

- Security incident analysis
- Web-server compromise analysis
- Authentication security
- Brute-force attack analysis
- TCP/IP analysis
- DNS analysis
- HTTP traffic analysis
- tcpdump interpretation
- Evidence correlation
- Root-cause analysis
- Security remediation planning
- Technical documentation

## Completed Analysis

[View the completed incident analysis](./web-server-compromise-malicious-redirect-analysis.pdf)

## Project Context

This project was completed in a simulated educational environment. Scenario, packet-capture, source-code, and file-analysis evidence were provided for investigation; the technical analysis, interpretation, root-cause assessment, recommendations, and portfolio report presented here reflect my work.
