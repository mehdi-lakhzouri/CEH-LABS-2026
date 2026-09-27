# Part 3 - dig vs nslookup

## Goal
Compare DNS reconnaissance using dig and nslookup.

## Commands Used
- dig cisco.com
- dig cisco.com AAAA
- dig @8.8.8.8 cisco.com NS
- dig skillsforall.com ANY

## Main Observation
By default, dig queries the A record unless another type is specified.

For IPv6, the AAAA record must be explicitly requested.

## Cisco NS Query
Using Google DNS 8.8.8.8 returned the following name servers:
- a3-64.akam.net
- ns1.cisco.com
- ns3.cisco.com
- ns2.cisco.com
- a28-64.akam.net

## Comparison
dig provides structured sections such as QUESTION, ANSWER, AUTHORITY and ADDITIONAL.
nslookup is simpler for quick interactive queries.

## Key Lesson
dig provides more detailed DNS response information while nslookup is convenient for quick and interactive DNS lookups.

## Evidence
- outputs/dig-cisco.txt
- outputs/dig-cisco-aaaa.txt
- outputs/dig-cisco-ns-google.txt
- outputs/dig-skillsforall-any.txt
- evidence/screenshots/06-dig-cisco-ns.png
