# Security Policy

## Purpose

This repository contains cybersecurity training material, command outputs, laboratory evidence, and ethical hacking exercises.

Security and responsible disclosure practices must therefore be applied to repository contents.

## Supported Version

The current master branch is the maintained version of this repository.

## Sensitive Information

Do not commit credentials, passwords, access tokens, API keys, private keys, session cookies, environment secrets, or other confidential information.

If sensitive information is accidentally committed:

1. Revoke or rotate the exposed credential immediately.
2. Remove the sensitive data from the repository.
3. Consider rewriting Git history if the secret exists in previous commits.
4. Verify that remote copies no longer expose the information.

Removing a secret from the latest file is not sufficient if it remains in Git history.

## Vulnerability Reporting

If you identify a security issue in this repository itself, avoid publishing sensitive details in a public issue.

Use GitHub private vulnerability reporting or a Security Advisory if available. Otherwise, contact the repository owner privately through GitHub.

## Third-Party Systems

This repository is not a vulnerability disclosure channel for third-party organizations or systems referenced by the labs.

Do not use this repository to publish unverified vulnerabilities, credentials, private information, or sensitive data belonging to third parties.

## Authorized Use

All offensive-security techniques documented here must only be used against:

- authorized laboratory targets;
- intentionally vulnerable systems;
- controlled environments;
- systems for which explicit authorization has been obtained.
