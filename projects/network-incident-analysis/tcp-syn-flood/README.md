# Network Incident Analysis: TCP SYN Flood

## Overview

This project demonstrates the analysis of a simulated denial-of-service incident affecting a web server.

I reviewed TCP packet activity to identify abnormal connection behavior, determine the attack type, and explain how the attack disrupted legitimate access to the website.

## Incident Summary

The web server experienced slow response times and connection timeout errors while receiving an unusually large volume of TCP SYN requests.

The packet activity showed repeated SYN requests from an unfamiliar source IP address. The server responded with SYN-ACK packets, but the connections were not completed normally.

This pattern is consistent with a **TCP SYN flood**, a denial-of-service attack that consumes server resources by creating large numbers of incomplete TCP connections.

## Technical Analysis

A normal TCP connection uses a three-way handshake:

1. The client sends a SYN request.
2. The server responds with SYN-ACK.
3. The client sends a final ACK to establish the connection.

During the incident, large numbers of SYN requests were sent without the connection process being completed normally.

As incomplete connections accumulated, server resources that would normally be available to legitimate users were consumed.

## Evidence and Interpretation

### Observed

The packet capture showed:

- Repeated TCP SYN requests
- SYN-ACK responses from the server
- Incomplete connection attempts
- A high volume of connection requests from an unfamiliar source IP address
- Website connection timeouts and degraded availability

### Confirmed Meaning

The server was receiving abnormal TCP connection requests that were not completing the normal three-way handshake.

### Operational Impact

The buildup of incomplete connections reduced the server's ability to establish legitimate TCP sessions, resulting in slow response times and connection timeout errors.

### Attack Classification

The observed behavior is consistent with a **denial-of-service (DoS) attack, specifically a TCP SYN flood**.

## Recommended Mitigation

Potential mitigation measures include:

- Implementing SYN flood protections
- Configuring SYN cookies where appropriate
- Applying connection-rate limits
- Monitoring abnormal SYN traffic
- Using firewall or intrusion-prevention rules to identify and restrict malicious connection attempts
- Establishing alert thresholds for abnormal TCP connection activity

## Skills Demonstrated

- TCP/IP analysis
- TCP three-way handshake analysis
- SYN flood identification
- Denial-of-service analysis
- Packet-traffic interpretation
- Incident investigation
- Network availability analysis
- Technical documentation

## Completed Analysis

[View the completed incident analysis](./network-incident-analysis-tcp-syn-flood.pdf)

## Project Context

This project was completed in a simulated educational environment. The scenario and packet-capture information were provided for analysis; the attack identification, technical interpretation, and portfolio report presented here reflect my work.
