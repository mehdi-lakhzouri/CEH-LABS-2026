# Part 4 - Reverse DNS

## Goal
Use dig, host and nslookup to perform reverse DNS lookups and identify aliases.

## Reverse DNS with dig

Command:
dig -x 72.163.5.201

Result:
72.163.5.201 -> ns1.cisco.com

The reverse lookup returned a PTR record.

## HSRP Address

Command:
dig -x 72.163.1.1

Result:
72.163.1.1 -> hsrp-72-163-1-1.cisco.com

The hostname suggests that this address is related to an HSRP gateway/router configuration.

## host Utility

Command:
host 72.163.10.1

Result:
NXDOMAIN - no PTR record was returned during this execution.

Command:
host www.cisco.com

Observed alias chain:
- www.cisco.com -> www.cisco.com.akadns.net
- www.cisco.com.akadns.net -> wwwds.cisco.com.edgekey.net
- wwwds.cisco.com.edgekey.net -> e2867.dsca.akamaiedge.net

The final hostname resolved to public IPv4 and IPv6 addresses.

## Reverse DNS with nslookup

Command:
nslookup 72.163.5.201

Result:
72.163.5.201 -> ns1.cisco.com

## Key Lesson
Reverse DNS uses PTR records to map IP addresses back to hostnames.
The host utility provides concise output and can also reveal CNAME/alias chains.
Not every IP address has a PTR record, and DNS information can change over time.

## Evidence
- evidence/screenshots/07-dig-reverse-ns1.png
- outputs/dig-reverse-72.163.5.201.txt
- outputs/dig-reverse-72.163.1.1.txt
- outputs/host-reverse-72.163.10.1.txt
- outputs/host-www-cisco.txt
- outputs/nslookup-reverse-72.163.5.201.txt
