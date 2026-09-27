# Part 4 - Interesting Files

## Goal
Identify potentially interesting files exposed at predictable web locations.

## Target
hackxor.net

## Module
discovery/info_disclosure/interesting_files

## Configuration
- SOURCE: hackxor.net
- DOWNLOAD: True
- PROTOCOL: http
- PORT: 80

## Result
The module tested predictable web paths.

One interesting file was found:
http://hackxor.net/robots.txt

robots.txt returned HTTP 200.
The other tested locations returned HTTP 404.

## robots.txt
User-agent: *
Disallow: /settings
Disallow: /pleasebanme

The downloaded evidence was copied to outputs/robots.txt.

## Security Meaning
robots.txt is publicly accessible and is not an access-control mechanism.
Its directives can disclose interesting application paths.

## Evidence
- evidence/screenshots/interesting-files-results
- outputs/robots.txt
