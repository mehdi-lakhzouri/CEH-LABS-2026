# Part 2 - WHOIS

## Goal
Use WHOIS to retrieve domain registration and IP allocation information.

## Domains Queried
- cisco.com
- skillsforall.com

## IP Investigated
72.163.5.201

## DNS Result
ns1.cisco.com resolved to:
- IPv4: 72.163.5.201
- IPv6: 2001:420:1101:6::a

## WHOIS IP Result
The IPv4 address belongs to a Cisco network allocation.

Expected network information:
- NetRange: 72.163.0.0 - 72.163.255.255
- CIDR: 72.163.0.0/16
- Organization: Cisco Systems, Inc.

## Key Lesson
WHOIS complements DNS reconnaissance by providing registration and network-allocation information.

## Evidence
- outputs/whois-cisco.txt
- outputs/whois-skillsforall.txt
- outputs/nslookup-ns1-cisco.txt
- outputs/whois-ns1-cisco-ip.txt
- evidence/screenshots/04-whois-cisco.png
- evidence/screenshots/05-whois-cisco-ip-range.png
