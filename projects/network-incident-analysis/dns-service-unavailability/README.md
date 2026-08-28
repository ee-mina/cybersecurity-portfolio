# Network Incident Analysis: DNS Service Unavailability

## Overview

This project demonstrates the investigation of a simulated website-access incident using captured network traffic.

I analyzed DNS, UDP, and ICMP activity to determine where the connection process failed, identify what the available evidence established, and develop a working hypothesis without overstating the root cause.

## Incident Summary

Users were unable to access a website and received a destination port unreachable error.

Network traffic captured during the incident showed that DNS queries sent over UDP port 53 were unsuccessful. Instead of receiving the requested IP address, the client received an ICMP Destination Unreachable response indicating that UDP port 53 was unreachable.

Because DNS resolution could not be completed, the client could not obtain the website's IP address and therefore could not proceed with an HTTPS connection.

## Technical Analysis

The packet capture showed:

- DNS A-record queries sent over UDP
- Client IP: `192.51.100.15`
- DNS server IP: `203.0.113.2`
- UDP source port: `52444`
- DNS destination port: `53`
- ICMP Destination Unreachable responses
- Three repeated DNS query attempts with the same result

The traffic established that the failure occurred during DNS resolution, before an HTTPS connection to the website could be initiated.

## Evidence and Interpretation

### Observed

The client repeatedly sent DNS queries to UDP port 53 and received ICMP responses indicating that the destination port was unreachable.

### Confirmed Meaning

The DNS service was unavailable through UDP port 53 during the captured connection attempts.

### Operational Impact

The client could not resolve the domain name to an IP address, preventing the connection process from progressing to HTTPS.

### Working Hypothesis

Possible causes included:

- The DNS service had stopped or crashed
- The DNS service was misconfigured
- The service was not listening on UDP port 53
- Firewall rules were blocking or rejecting DNS traffic

The available packet capture did not confirm the underlying root cause.

## Recommended Verification

Further investigation should include:

- Verifying that the DNS service is running
- Confirming that the service is listening on UDP port 53
- Reviewing DNS server logs
- Reviewing DNS configuration
- Checking firewall rules affecting DNS traffic
- Collecting additional traffic or system evidence if necessary

## Skills Demonstrated

- Network traffic analysis
- DNS troubleshooting
- UDP analysis
- ICMP interpretation
- tcpdump analysis
- Incident investigation
- Failure-point identification
- Evidence-versus-inference reasoning
- Root-cause hypothesis development
- Technical documentation

## Completed Analysis

[View the completed incident analysis](./network-incident-analysis-dns-service-unavailability.pdf)

## Project Context

This project was completed in a simulated educational environment. The scenario and packet-capture information were provided for analysis; the investigation, technical interpretation, working hypothesis, and portfolio report presented here reflect my work.
