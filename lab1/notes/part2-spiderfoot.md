# Part 2 - SpiderFoot

## Goal
Use SpiderFoot to automate OSINT reconnaissance.

## Target
h4cker.org

## Commands
- spiderfoot -M
- spiderfoot -l 127.0.0.1:5001

## Scan
- Profile: Footprint
- Target: h4cker.org
- Web interface: http://127.0.0.1:5001

## What I Learned
SpiderFoot is a modular OSINT scanner.

Starting from a seed such as a domain, it can correlate information including:
- domains and subdomains
- IP addresses
- DNS information
- URLs
- emails
- technologies
- related Internet assets

Some modules work directly while others require API keys.

## Evidence
- evidence/screenshots/spiderfoot-dashboard
- evidence/screenshots/spiderfoot-module-detail
- evidence/screenshots/spiderfoot-modules.png
- evidence/screenshots/spiderfoot-results

## Key Lesson
SpiderFoot automates OSINT collection and pivoting, but findings still need interpretation.
