# CEH Labs 2026

Practical cybersecurity laboratory repository documenting hands-on CEH-oriented work performed primarily on Kali Linux.

The objective is not only to complete exercises, but to understand the methodology behind each technique, execute it correctly, analyze the results, preserve useful evidence, and maintain a reproducible technical knowledge base.

## Repository Objectives

- Build practical ethical hacking and cybersecurity skills.
- Understand reconnaissance, enumeration, networking, vulnerability assessment, and security testing techniques.
- Practice common offensive-security tools in authorized environments.
- Preserve concise notes, command outputs, and relevant evidence.
- Maintain a clean Git workflow with one branch per lab.
- Apply secure repository practices and avoid committing secrets or sensitive credentials.

## Repository Structure

```text
CEH/
├── README.md
├── CONTRIBUTING.md
├── SECURITY.md
├── LICENSE
├── .gitignore
├── lab1/
│   ├── README.md
│   ├── notes/
│   ├── outputs/
│   ├── evidence/screenshots/
│   └── tools/
├── lab2/
│   └── ...
└── labN/
```

Each lab contains its own documentation, selected outputs, screenshots, and technical notes.

## Lab Progress

| Lab | Topic | Main Tools | Status |
| --- | --- | --- | --- |
| Lab 1 | Using OSINT Tools | OSINT Framework, WhatsMyName, SpiderFoot, Recon-ng | Completed |
| Lab 2 | DNS Lookups | nslookup, whois, dig, host | Completed |

## Lab 1 - Using OSINT Tools

### Objective

Understand how publicly available information can be collected, correlated, and used during reconnaissance.

### Work Performed

- Explored OSINT Framework, WhatsMyName, and SMART.
- Used SpiderFoot for automated OSINT reconnaissance.
- Created an isolated Recon-ng workspace.
- Used HackerTarget and Bing reconnaissance modules.
- Enumerated hosts associated with hackxor.net.
- Used the Interesting File Finder module.
- Discovered and analyzed a publicly accessible robots.txt file.

### Key Results

- HackerTarget discovered 9 hosts associated with hackxor.net.
- Most discovered hosts resolved to 138.68.117.124.
- robots.txt disclosed the paths /settings and /pleasebanme.

### Main Lessons

- OSINT requires collection, validation, pivoting, and correlation.
- Different sources can return different results for the same target.
- SpiderFoot automates information gathering while Recon-ng provides a structured modular workflow.
- robots.txt is public information and is not an access-control mechanism.

## Lab 2 - DNS Lookups

### Objective

Use DNS and WHOIS tools for passive reconnaissance and understand publicly exposed DNS and network-registration information.

### Work Performed

- Resolved IPv4 and IPv6 addresses with nslookup.
- Queried A, AAAA, NS, MX, SOA, and TXT records.
- Used Google DNS 8.8.8.8 as an alternative resolver.
- Performed domain and IP WHOIS lookups.
- Compared dig and nslookup output.
- Performed reverse DNS lookups using dig, host, and nslookup.
- Investigated DNS alias chains.

### Key Results

- ns1.cisco.com resolved to 72.163.5.201 and 2001:420:1101:6::a.
- Reverse DNS mapped 72.163.5.201 back to ns1.cisco.com.
- 72.163.1.1 resolved to hsrp-72-163-1-1.cisco.com.
- host revealed the www.cisco.com alias chain toward Akamai infrastructure.

### Main Lessons

- DNS reconnaissance can expose addressing, DNS infrastructure, mail infrastructure, aliases, and metadata.
- WHOIS complements DNS with registration and network-allocation data.
- dig provides detailed structured responses while nslookup is useful for quick interactive lookups.
- Reverse DNS relies on PTR records and not every IP address has one.

## Lab Workflow

```text
Understand objective
      ↓
Execute and analyze
      ↓
Collect useful evidence
      ↓
Write concise notes
      ↓
Validate lab
      ↓
Create dedicated Git branch
      ↓
Commit and push
      ↓
Merge into master
```

## Evidence Policy

Only useful technical evidence is retained. Terminal logs, secrets, credentials, private keys, API keys, environment files, and unnecessary sensitive data must not be committed.

## Responsible Use

All techniques documented in this repository are intended for authorized cybersecurity laboratories, controlled environments, training systems, and systems for which explicit testing permission exists.

## GitHub Repository

`mehdi-lakhzouri/CEH-LABS-2026`

## Maintenance

This root README is updated whenever a lab is completed.
