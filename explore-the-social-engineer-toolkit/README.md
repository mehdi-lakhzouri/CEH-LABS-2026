# 4.4.7 - Explore the Social-Engineer Toolkit (SET)

## Overview
This laboratory explores the Social-Engineer Toolkit (SET) and demonstrates the security risks associated with deceptive login interfaces.

The exercise follows the Cisco Ethical Hacker Lab 4.4.7 and uses an isolated Kali Linux environment with Docker-based DVWA.

## Learning Objectives
- Explore the SET interface and social-engineering modules.
- Understand Website Attack Vectors and Site Cloner.
- Deploy and verify a local DVWA laboratory.
- Observe synthetic authentication form submissions.
- Identify network exposure and defensive controls.

## Tools and Technologies
| Tool | Purpose |
|---|---|
| Kali Linux | Security testing environment |
| SET 8.0.3 | Social-engineering simulation |
| Docker Compose | Local application deployment |
| DVWA | Intentionally vulnerable Web application |
| MariaDB | Application database |
| curl | HTTP connectivity verification |
| ss | Listening port verification |
| iptables | Temporary network restriction |

## Laboratory Architecture

```text
Kali Linux VM
|
+-- SET 8.0.3
|   +-- Local HTTP listener: TCP/80
|
+-- Docker Compose
    +-- DVWA: 127.0.0.1:4280
    +-- MariaDB: Internal Docker network
```

The demonstration was performed locally using synthetic credentials.
The SET listener was observed on all IPv4 interfaces and was temporarily restricted with a firewall rule.

## Lab Parts
| Part | Description | Result |
|---|---|---|
| Part 1 | SET menus and module exploration | Completed |
| Part 2 | Local DVWA Website Cloning | Completed |
| Part 3 | Synthetic form submission observation | Capture verified |

## Main Observations
- SET version: 8.0.3 (Maverick).
- DVWA and MariaDB containers started successfully.
- Original DVWA HTTP endpoint returned 302 to login.php.
- SET Site Cloner initialized successfully.
- The local demonstration page returned HTTP 200.
- SET received username, password, Login, and user_token form parameters.
- All submitted account data was synthetic.
- The SET HTTP listener initially used 0.0.0.0:80.

## Documentation
- [Part 1 - SET Exploration](notes/part1-set-exploration.md)
- [Part 2 - Website Cloning](notes/part2-website-cloning.md)
- [Part 3 - Controlled Simulation](notes/part3-phishing-simulation.md)

## Project Structure

```text
explore-the-social-engineer-toolkit/
|-- README.md
|-- notes/
|   |-- part1-set-exploration.md
|   |-- part2-website-cloning.md
|   `-- part3-phishing-simulation.md
|-- outputs/
|-- evidence/
|   `-- screenshots/
`-- tools/
```

## Security and Ethical Scope
This work was performed for educational purposes inside a local laboratory.
No real credentials were collected and no external phishing campaign was performed.
Raw credential-harvesting logs, session tokens, and unredacted screenshots must not be published.

## Remaining Validation
- Confirm browser behavior following form submission.
- Confirm whether SET generated its XML report.
- Verify SET shutdown and removal of temporary firewall rules.
- Verify and sanitize screenshots before the Git commit.

## Key Takeaways
The exercise demonstrates how social-engineering tooling can reproduce familiar authentication interfaces and why technical safeguards, phishing-resistant MFA, and user awareness are important.

## Reference
Cisco Networking Academy - Ethical Hacker - Lab 4.4.7: Explore the Social-Engineer Toolkit.
