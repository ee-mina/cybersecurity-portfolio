# Network Incident Analysis: DNS Service Unavailability

## Overview

I investigated a simulated website-access failure using captured DNS, UDP, and ICMP traffic to determine where the connection process broke down and what should be checked next.

The evidence showed that the failure occurred during DNS resolution, before the client could establish an HTTPS connection to the website.

## Incident Findings

The client at `192.51.100.15` repeatedly sent DNS A-record queries to the DNS server at `203.0.113.2` over UDP port 53.

Instead of receiving the requested IP address, the client received ICMP Destination Unreachable responses indicating that UDP port 53 was unreachable.

The DNS request was attempted three times with the same result.

## Impact

Because the domain name could not be resolved to an IP address, the client could not continue to the HTTPS stage of the connection.

For the user, the result was simple: the website could not be reached.

## Working Hypothesis

The packet capture established that DNS service over UDP port 53 was unavailable during the connection attempts.

Possible causes included:

- The DNS service had stopped or crashed
- The service was misconfigured
- The service was not listening on UDP port 53
- A firewall was blocking or rejecting DNS traffic

The next step would be to verify the DNS service directly rather than infer the underlying cause from packet traffic alone.

## Recommended Verification

- Confirm the DNS service is running
- Confirm it is listening on UDP port 53
- Review DNS server logs
- Review DNS configuration
- Check firewall rules affecting DNS traffic
- Collect additional system or network evidence if needed

## Skills Demonstrated

- Network traffic analysis
- DNS troubleshooting
- UDP analysis
- ICMP interpretation
- tcpdump analysis
- Failure-point identification
- Incident investigation
- Evidence-based troubleshooting
- Technical documentation

## Completed Analysis

[View the completed incident analysis](./network-incident-analysis-dns-service-unavailability.pdf)

## Project Context

This work was completed in a simulated educational environment. The scenario and packet-capture data were provided; the technical interpretation, troubleshooting approach, and portfolio report reflect my work.
