# Part 1 - Social-Engineer Toolkit Exploration

## Objective
Explore the Social-Engineer Toolkit (SET), identify its available modules, and understand their roles in authorized security assessments.

## Environment
- Operating system: Kali Linux
- Tool: Social-Engineer Toolkit (SET)
- Version: 8.0.3 (Maverick)
- Scenario: Cisco Ethical Hacker Lab 4.4.7

## Launching SET
SET was launched with root privileges:

```bash
sudo setoolkit
```

The main SET menu was displayed successfully.
A startup warning related to Python object serialization appeared, but it did not prevent menu navigation.

## Main Menu
The following modules were observed:

1. Social-Engineering Attacks
2. Penetration Testing (Fast-Track)
3. Third Party Modules
4. Update the Social-Engineer Toolkit
5. Update SET configuration
6. Help, Credits, and About
99. Exit

## Social-Engineering Attack Categories
After selecting option 1, SET displayed:

1. Spear-Phishing Attack Vectors
2. Website Attack Vectors
3. Infectious Media Generator
4. Create a Payload and Listener
5. Mass Mailer Attack
6. Arduino-Based Attack Vector
7. Wireless Access Point Attack Vector
8. QRCode Generator Attack Vector
9. Powershell Attack Vectors
10. Third Party Modules

## Spear-Phishing Module
The spear-phishing submenu was inspected.
SET displayed options for mass email, FileFormat payload creation, and social-engineering templates.
No malicious payload or phishing campaign was executed.

## Lab Questions
**Q1: Which option concerns malicious removable media?**
Answer: Option 3 - Infectious Media Generator.

**Q2: How could removable-media simulations support a penetration test?**
Answer: An explicitly authorized simulation can assess how personnel handle unknown removable devices and measure security-awareness effectiveness without deploying harmful software.

## Security Considerations
- SET modules must only be used in authorized assessments.
- Social-engineering simulations require defined scope and consent.
- Malicious payloads and real phishing distribution were outside this exercise.

## Evidence
- Suggested screenshot: evidence/screenshots/01-set-social-engineering-menu.png
- Actual screenshots must be verified before publishing.

## Conclusion
SET 8.0.3 was launched successfully. Its principal menus and attack categories were explored, establishing the foundation for the controlled Web Attack Vector exercise.
