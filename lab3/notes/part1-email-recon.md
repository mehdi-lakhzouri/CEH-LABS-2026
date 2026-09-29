# Part 1 - Email and Organization Reconnaissance

## Goal
Collect publicly available information related to an organization and its email infrastructure.

## Tools Used
- EmailHarvester
- SpiderFoot
- Public breach-checking services

## EmailHarvester
EmailHarvester was used to perform domain-oriented email reconnaissance.

The -d option is used to specify the target domain.

Targets tested:
- h4cker.org
- hackxor.net

Commands used:

```bash
emailharvester -h
emailharvester -d h4cker.org
emailharvester -d hackxor.net
```

Command outputs were saved for later review and comparison.

## SpiderFoot
SpiderFoot was used as an additional OSINT platform for organization and email reconnaissance.

The scan was configured using the By Module mode so that only modules relevant to email, account, archive, search-engine, and breach-related reconnaissance could be selected.

Example modules considered included:
- Account Finder
- Ahmia
- Archive.org
- Bing
- CommonCrawl
- DuckDuckGo
- EmailCrawlr
- Leak-Lookup
- Dehashed

Some modules may require API keys and therefore may not be available in every execution.

## Key Lesson
Email reconnaissance can reveal public information about employees, accounts, exposed addresses, and organizational infrastructure.

Results from public OSINT sources are not always complete or consistent and should be validated using multiple sources.

## Evidence and Outputs
- outputs/emailharvester-help.txt
- outputs/emailharvester-h4cker.txt
- outputs/emailharvester-hackxor.txt

## Security Note
No passwords, leaked credentials, API keys, or sensitive breach data should be stored in this repository.
