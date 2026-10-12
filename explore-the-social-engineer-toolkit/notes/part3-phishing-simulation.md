# Part 3 - Controlled Credential Capture Simulation

## Objective
Observe how a cloned login interface receives submitted form parameters and evaluate the security implications in a controlled laboratory.

## Scope and Safety
- Environment: Local Kali Linux and Docker DVWA
- Testing endpoint: http://127.0.0.1/
- Test inputs: Synthetic, non-production credentials
- No real user accounts or credentials were used
- No phishing emails or links were distributed to external users

## Execution Summary
The cloned Web page was accessed from Firefox on Kali.
SET recorded an HTTP GET request to / with status 200.
An additional request to /favicon.ico returned status 404, which did not prevent the demonstration.

A synthetic login form was submitted through the locally cloned page.
The SET terminal then displayed a successful credential-harvester hit.

## Observed Form Parameters
The following form fields were identified:

| Parameter | Observation |
|---|---|
| username | Synthetic username field received |
| password | Synthetic password field received |
| Login | Login button parameter received |
| user_token | Application form token received |

Actual submitted values and token values are deliberately excluded from this report.

## Lab Questions
**Q1: What information did the cloned page receive?**
Answer: A synthetic username, synthetic password, login parameter, and application form token.

**Q2: Why is this behavior a security risk?**
Answer: A deceptive login page can receive credentials submitted by users who fail to verify the destination URL.

**Q3: How can a security team reduce this risk?**
Answer: Use phishing-resistant MFA, trusted password managers, domain verification, user-awareness training, and monitoring of suspicious authentication flows.

## Findings
- The local demonstration page was reachable.
- The HTTP listener returned status 200.
- SET received parameters from the submitted form.
- The listener was observed on 0.0.0.0:80.
- A firewall rule was added to restrict network access to the test listener.

## Verification Still Required
- Browser redirection to the original DVWA page after submission was not confirmed.
- XML report generation and report path were not confirmed.
- Removal of temporary firewall rules and listener shutdown were not confirmed.

## Cleanup Commands
After stopping SET with Ctrl+C, remove both previously inserted firewall rules:

```bash
sudo iptables -D INPUT -i eth0 -p tcp --dport 80 -j DROP
sudo iptables -D INPUT -i eth0 -p tcp --dport 80 -j DROP
sudo ss -ltnp "( sport = :80 )"
sudo iptables -S INPUT
```

Run the deletion commands only while the corresponding rules exist.
Confirm that no SET listener remains on TCP/80.

## Evidence Handling
- Suggested capture: evidence/screenshots/06-set-credential-capture.png
- Redact password values, usernames, tokens, cookies, and session identifiers.
- Do not commit raw SET XML reports to the public GitHub repository.

## Conclusion
The controlled simulation demonstrated that a cloned login page can receive synthetic authentication form parameters. It illustrates the importance of destination verification, phishing-resistant authentication, and isolation of testing infrastructure.
