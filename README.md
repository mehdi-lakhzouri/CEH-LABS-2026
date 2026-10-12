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
├── lab3/
│   ├── README.md
│   ├── notes/
│   ├── outputs/
│   ├── evidence/screenshots/
│   └── tools/
├── lab3/
│   └── ...
├── explore-the-social-engineer-toolkit/
│   ├── README.md
│   ├── notes/
│   ├── outputs/
│   └── evidence/screenshots/
└── labN/
```

Each lab contains its own documentation, selected outputs, screenshots, and technical notes.

## Lab Progress

| Lab | Topic | Main Tools | Status |
| --- | --- | --- | --- |
| [Lab 1](lab1/README.md) | Using OSINT Tools | Recon-ng, SpiderFoot, OSINT Framework | Completed |
| [Lab 2](lab2/README.md) | DNS Lookups | nslookup, whois, dig, host | Completed |
| [Lab 3](lab3/README.md) | Finding Out About the Organization | EmailHarvester, SpiderFoot, ExifTool | Completed |
| Lab 4 | Finding Information from SSL Certificates | OpenSSL, crt.sh, sslscan | Paused |
| Lab 5 | Vulnerability Scanning with Kali Tools | Nmap, Vulners, GVM | Paused |
| [TP 4.4.7](explore-the-social-engineer-toolkit/README.md) | Explore the Social-Engineer Toolkit | SET, Docker, DVWA | Documented - cleanup verification pending |
| [TP 4.4.8](using-the-browser-exploitation-framework-beef/README.md) | Using the Browser Exploitation Framework | BeEF, Firefox | Documented - final verification pending |

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

## Lab 3 - Finding Out About the Organization

### Objective

Perform passive reconnaissance on an organization using email-related OSINT techniques and file metadata analysis.

### Work Performed

- Used public breach-checking services to examine email exposure.
- Used EmailHarvester to perform domain-oriented email reconnaissance.
- Tested `h4cker.org` and `hackxor.net`.
- Reviewed SpiderFoot modules relevant to email, accounts, archives, search engines, and breach-related intelligence.
- Installed and used ExifTool for metadata analysis.
- Reviewed supported file formats with `exiftool -listf`.
- Analyzed multiple PNG files individually and as a directory.
- Exported metadata from the sample directory to CSV.

### Key Results

- EmailHarvester outputs were collected for `h4cker.org` and `hackxor.net`.
- SpiderFoot was used to explore organization and email-related OSINT sources.
- ExifTool 13.55 successfully analyzed the test files.
- The analyzed PNG files exposed mainly technical metadata such as:
  - file type;
  - MIME type;
  - timestamps;
  - image dimensions;
  - compression;
  - megapixel count.
- No author, creator, GPS, camera model, or sensitive software metadata was found in the tested screenshots.
- Metadata for the full sample directory was successfully exported to `outputs/metadata.csv`.

### Main Lessons

- Email reconnaissance can provide useful leads about employees, exposed accounts, domains, and breach history.
- OSINT results should be validated across multiple sources because public data may be incomplete or inconsistent.
- File metadata can expose technical or organizational information that may assist reconnaissance.
- Metadata exposure depends heavily on the file type and the software or device used to create the file.
- Files intended for public distribution should have their metadata reviewed before publication.

## TP 4.4.7 - Explore the Social-Engineer Toolkit

### Objective

Explore SET and demonstrate the security risks associated with deceptive login interfaces in an isolated laboratory.

### Work Performed

- Launched Social-Engineer Toolkit 8.0.3 on Kali Linux.
- Explored social-engineering and website attack modules.
- Deployed DVWA and MariaDB using Docker Compose.
- Studied SET Site Cloner using the local DVWA login page.
- Performed a controlled form submission with synthetic credentials.
- Inspected the SET HTTP listener and applied a temporary network restriction.

### Key Results

- DVWA was accessible locally on 127.0.0.1:4280.
- SET served a demonstration login interface on TCP port 80.
- SET received synthetic form parameters: username, password, Login, and user_token.
- The SET listener was observed on 0.0.0.0:80, highlighting the importance of network isolation.
- Three technical reports and a dedicated lab README were prepared.

### Documentation

- [Lab Overview](explore-the-social-engineer-toolkit/README.md)
- [Part 1 - SET Exploration](explore-the-social-engineer-toolkit/notes/part1-set-exploration.md)
- [Part 2 - Website Cloning](explore-the-social-engineer-toolkit/notes/part2-website-cloning.md)
- [Part 3 - Controlled Simulation](explore-the-social-engineer-toolkit/notes/part3-phishing-simulation.md)

### Main Lessons

- A familiar login interface does not guarantee the authenticity of a website.
- Phishing-resistant MFA and careful domain verification help mitigate credential phishing.
- Security testing tools must be restricted to authorized environments.
- Credential values, session tokens, and unredacted capture logs must not be published.

### Remaining Validation

- Confirm SET shutdown and cleanup of temporary firewall rules.
- Verify browser redirection and XML report generation where applicable.
- Review and sanitize screenshots before publication.

## TP 4.4.8 - Using the Browser Exploitation Framework (BeEF)

### Objective

Explore browser hooking, client-side security testing, and social-engineering simulations in a controlled local environment.

### Work Performed

- Launched BeEF and accessed its Web dashboard.
- Hooked the local Firefox browser using the official The Butcher demo.
- Identified the hook.js script in the HTML source.
- Inspected browser metadata and capabilities.
- Explored command modules and compatibility indicators.
- Examined Network Map, Hosts, and Services.
- Demonstrated Fake Notification Bar in Firefox.
- Executed TabNabbing and inspected browser activity logs.

### Key Results

- Firefox 140.0 appeared under Online Browsers.
- The hook.js reference was identified on line 31.
- Detect Antivirus appeared under Host with a green indicator.
- Network Map displayed the Linux host 127.0.0.1.
- The Services view showed no discovered services.
- A simulated Firefox notification was displayed.
- TabNabbing command events and browser activity were recorded.
- Final TabNabbing page replacement was not independently confirmed by the provided screenshots.

### Documentation

- [Lab Overview](using-the-browser-exploitation-framework-beef/README.md)
- [Part 1 - BeEF GUI and Browser Hooking](using-the-browser-exploitation-framework-beef/notes/part1-beef-gui-browser-hooking.md)
- [Part 2 - Browser Exploitation Capabilities](using-the-browser-exploitation-framework-beef/notes/part2-browser-exploitation.md)

### Security Lessons

Browser-based attacks can manipulate interfaces and observe user interactions. Browser updates, phishing-resistant MFA, URL verification, and strict testing isolation are important defensive controls.

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
