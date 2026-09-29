# Lab 3 - Finding Out About the Organization

## Objective
Perform passive reconnaissance on an organization using email-related OSINT techniques and file metadata analysis.

The lab focuses on two main areas:
- Email and organization reconnaissance.
- File metadata reconnaissance.

## Tools Used
- EmailHarvester
- SpiderFoot
- Public breach-checking services
- ExifTool

## Part 1 - Email and Organization Reconnaissance

EmailHarvester was used to examine domains and collect publicly available email-related information.

Targets tested included:
- h4cker.org
- hackxor.net

SpiderFoot was also reviewed as an OSINT platform for email, account, archive, search-engine, and breach-related reconnaissance.

Public breach-checking services were used to understand how exposed email addresses can provide additional reconnaissance leads.

### Main Lesson
Email reconnaissance may reveal public information about employees, exposed accounts, domain infrastructure, and potential breach history. Results should be validated using multiple sources.

## Part 2 - File Metadata Reconnaissance

ExifTool 13.55 was used to inspect metadata contained in local files.

Two PNG images were analyzed:
- samples/sample.png
- samples/sample2.png

Observed metadata included:
- File name and size
- File type and MIME type
- Modification timestamps
- Image dimensions
- Bit depth
- Compression method
- Megapixel count

No author, GPS, camera model, creator, or sensitive software metadata was present in the tested screenshots.

ExifTool was also executed against the complete samples directory and the resulting metadata was exported to CSV.

### CSV Export

```bash
exiftool -csv samples/ > outputs/metadata.csv
```

### Main Lesson
Metadata availability depends on the file type and the software or device used to create the file. Public files should therefore be reviewed before publication because metadata can potentially expose technical or organizational information.

## Evidence
- evidence/screenshots/01-breach-check.png
- evidence/screenshots/02-emailharvester-help.png
- evidence/screenshots/03-emailharvester-h4cker.png
- evidence/screenshots/06-exiftool-file-metadata.png
- evidence/screenshots/07-exiftool-csv-export.png

## Outputs
- outputs/emailharvester-help.txt
- outputs/emailharvester-h4cker.txt
- outputs/emailharvester-hackxor.txt
- outputs/exiftool-version.txt
- outputs/exiftool-supported-formats.txt
- outputs/exiftool-sample2-png.txt
- outputs/exiftool-all-files.txt
- outputs/metadata.csv

## Security Considerations
No passwords, leaked credentials, API keys, private information, or other sensitive breach data should be stored in this repository.

## Status
Completed.
