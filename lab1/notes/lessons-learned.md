# Lessons Learned

## OSINT
OSINT requires collecting, validating and correlating information from multiple public sources.

## Automation
SpiderFoot automates many reconnaissance pivots but the results still require analyst validation.

## Recon-ng
Recon-ng organizes investigations using workspaces, modules and a local results database.

## Multiple Sources
Different OSINT sources can return different results for the same target.
HackerTarget discovered 9 hosts while Bing added no new hosts during this execution.

## Information Disclosure
Public files such as robots.txt can expose interesting application paths.

In this lab robots.txt disclosed:
- /settings
- /pleasebanme

robots.txt is not an access-control mechanism.
