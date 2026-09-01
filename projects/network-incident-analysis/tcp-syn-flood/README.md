# Network Incident Analysis: TCP SYN Flood

## Overview

I analyzed a simulated denial-of-service incident in which a web server received an unusually high volume of TCP SYN requests and legitimate users began experiencing slow responses and connection timeouts.

The traffic pattern was consistent with a TCP SYN flood.

## Incident Findings

The packet capture showed repeated SYN requests from `203.0.113.0` to the web server at `192.0.2.1`.

The server responded with SYN-ACK packets, but many connection attempts did not receive the expected final ACK.

As those incomplete connections accumulated, server resources remained tied up waiting for sessions that were never completed.

## Impact

The growing number of half-open connections reduced the resources available for legitimate clients.

This resulted in degraded response times, connection timeouts, and the potential for the website or sales page to become unavailable if the traffic continued.

## Attack Classification

The combination of:

- High-volume SYN traffic
- SYN-ACK responses
- Unfinished TCP connections
- Resource exhaustion
- Availability problems

is consistent with a **TCP SYN flood denial-of-service attack**.

## Recommended Mitigation

Appropriate protections include:

- SYN flood protection
- SYN cookies where appropriate
- Connection-rate limiting
- Monitoring for abnormal SYN traffic
- Firewall or intrusion-prevention rules targeting malicious connection patterns
- Alert thresholds for unusual TCP connection activity

## Skills Demonstrated

- TCP/IP analysis
- TCP connection analysis
- SYN flood identification
- Denial-of-service analysis
- Packet-traffic interpretation
- Network availability analysis
- Incident investigation
- Technical documentation

## Completed Analysis

[View the completed incident analysis](./network-incident-analysis-tcp-syn-flood.pdf)

## Project Context

This work was completed in a simulated educational environment. The scenario and packet-capture data were provided; the attack identification, technical interpretation, and portfolio report reflect my work.
