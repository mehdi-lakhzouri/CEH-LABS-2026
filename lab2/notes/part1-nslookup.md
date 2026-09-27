# Part 1 - nslookup

## Goal
Use nslookup to collect DNS information about public domains and understand common DNS record types.

## Targets
- cisco.com
- skillsforall.com

## DNS Resolution
nslookup returned IPv4 and IPv6 information for cisco.com.

## Name Servers
Using set type=ns allowed the authoritative DNS servers for cisco.com to be identified.

## Google DNS
Google DNS 8.8.8.8 was used to query skillsforall.com.

## ANY Query
The ANY query returned several DNS record types:
- A
- NS
- SOA
- MX
- TXT

The TXT records included domain-verification information and an SPF policy.

## Key Lesson
DNS reconnaissance can expose public infrastructure information including IP addresses, name servers, mail infrastructure and domain metadata.

## Evidence
- evidence/screenshots/01-nslookup-cisco-a-aaaa.png
- evidence/screenshots/02-nslookup-cisco-ns.png
- evidence/screenshots/03-nslookup-skillsforall-any.png
- outputs/nslookup-cisco.txt
- outputs/nslookup-cisco-ns.txt
- outputs/nslookup-cisco-mx.txt
- outputs/nslookup-skillsforall-google.txt
