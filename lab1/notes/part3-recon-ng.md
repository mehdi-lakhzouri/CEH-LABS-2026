# Part 3 - Recon-ng

## Goal
Use Recon-ng as a modular reconnaissance framework and store results in an isolated workspace.

## Workspace
lab-osint

## Target
hackxor.net

## HackerTarget
Module: recon/domains-hosts/hackertarget

Configuration:
- options set SOURCE hackxor.net
- run

## Result
HackerTarget discovered 9 hosts.

- analytics.hackxor.net
- dreaded.hackxor.net
- hkrb.hackxor.net
- hmrc.hackxor.net
- intranet.hackxor.net
- phonecorp.hackxor.net
- research1.hackxor.net
- transparency.hackxor.net
- transperncy.hackxor.net

Most hosts resolved to 138.68.117.124.
intranet.hackxor.net referenced the private address 10.60.10.18.

## Bing
Module: recon/domains-hosts/bing_domain_web

The Bing module executed but added no additional hosts during this run.

## Evidence
- evidence/screenshots/hosts.png

## Key Lesson
Recon-ng stores reconnaissance results in workspace databases and allows different OSINT sources to be compared.
