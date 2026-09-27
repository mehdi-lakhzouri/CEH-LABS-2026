# Lab 2 - DNS Lookups

## Objective
Use DNS and WHOIS tools to perform passive reconnaissance and understand public DNS infrastructure.

## Completed Parts
1. nslookup
2. WHOIS
3. dig vs nslookup
4. Reverse DNS

## Main Tools
- nslookup
- whois
- dig
- host

## Main Results
- Resolved cisco.com IPv4 and IPv6 addresses.
- Identified Cisco authoritative DNS servers.
- Queried skillsforall.com using Google DNS 8.8.8.8.
- Observed A, NS, SOA, MX and TXT records.
- ns1.cisco.com resolved to 72.163.5.201 and 2001:420:1101:6::a.
- WHOIS identified the Cisco IPv4 allocation.
- dig and nslookup outputs were compared.
- Reverse DNS mapped 72.163.5.201 to ns1.cisco.com.
- Reverse DNS mapped 72.163.1.1 to hsrp-72-163-1-1.cisco.com.
- host revealed the www.cisco.com alias chain toward Akamai infrastructure.

## Key Takeaway
DNS reconnaissance can reveal public addressing, name servers, mail infrastructure, metadata, aliases and network ownership information without requiring direct exploitation of the target.

## Status
Completed.
