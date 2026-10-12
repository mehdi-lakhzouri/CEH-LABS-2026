# Part 2 - Website Cloning with SET

## Objective
Examine the SET Website Attack Vectors module and demonstrate Web page cloning within an isolated, authorized laboratory.

## Laboratory Architecture
- Host: Kali Linux virtual machine
- Target application: Damn Vulnerable Web Application (DVWA)
- Deployment: Docker Compose
- Web container: ghcr.io/digininja/dvwa:latest
- Database container: mariadb:10
- Original login URL: http://127.0.0.1:4280/login.php
- SET demonstration URL: http://127.0.0.1/

## DVWA Verification
The following checks were performed:

```bash
sudo docker ps
curl -I http://127.0.0.1:4280/
```

Both DVWA and MariaDB containers were running.
The HTTP response returned 302 Found with Location: login.php.
The DVWA Web port was published on 127.0.0.1:4280.

## SET Menu Navigation
The following menu sequence was used:

1. Social-Engineering Attacks
2. Website Attack Vectors
3. Credential Harvester Attack Method
2. Site Cloner

## Credential Harvester Methods
SET displayed three available methods:

| Option | Method | Description |
|---|---|---|
| 1 | Web Templates | Use predefined website templates |
| 2 | Site Cloner | Clone an existing Web page |
| 3 | Custom Import | Import a custom HTML page |

## Clone Configuration
The following parameters were entered:

- POST callback address: 127.0.0.1
- Source page: http://127.0.0.1:4280/login.php
- Local SET listener: TCP port 80

SET reported that the Credential Harvester was running on port 80.
An HTTP GET request to the cloned page returned status 200.

## Network Exposure Observation
The listener configuration was inspected using:

```bash
sudo ss -ltnp "( sport = :80 )"
```

Observed listener: 0.0.0.0:80, owned by setoolkit.
This means the service listened on all IPv4 interfaces, despite the loopback callback address.

A temporary firewall rule was added to block inbound TCP/80 traffic on the VMware network interface:

```bash
sudo iptables -I INPUT 1 -i eth0 -p tcp --dport 80 -j DROP
```

The same rule was entered twice. Removal of both rules must be verified during cleanup.

## Lab Questions
**Q1: Which method clones an existing login page?**
Answer: Site Cloner, option 2.

**Q2: Which method supports a custom website?**
Answer: Custom Import, option 3.

**Q3: Why is the URL important?**
Answer: The original application and the cloned demonstration page can look similar while using different ports or hostnames. Users must validate the destination before entering credentials.

## Evidence
- Original DVWA login: evidence/screenshots/02-dvwa-original-login.png
- Web Attack Vectors menu: evidence/screenshots/03-set-web-attack-vectors.png
- Harvester methods: evidence/screenshots/04-set-credential-harvester-methods.png
- Cloned login: evidence/screenshots/05-dvwa-cloned-login.png
- Verify that screenshots exist and contain no sensitive data before publishing.

## Conclusion
SET successfully initialized the Site Cloner demonstration against local DVWA. The exercise also identified a network exposure risk caused by binding the local HTTP listener to all interfaces.
