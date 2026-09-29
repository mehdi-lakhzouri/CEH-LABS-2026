# Part 2 - File Metadata Reconnaissance

## Goal
Use ExifTool to inspect metadata contained in local files and understand what information may be exposed publicly.

## Tool
ExifTool 13.55

## Supported File Formats
ExifTool supports a large number of file formats including:
- PDF
- DOC / DOCX
- JPG / JPEG
- PNG
- MP3
- MP4
- ZIP
- AVI
- WAV
- HTML

The supported formats were reviewed using:

```bash
exiftool -listf
```

The output was saved to:

```text
outputs/exiftool-supported-formats.txt
```

## Files Analyzed
Two PNG screenshots were copied into the samples directory:

- samples/sample.png
- samples/sample2.png

Both files had a resolution of 1280x800 pixels and used RGB color.

## Individual File Analysis
ExifTool was executed against each image.

Example:

```bash
exiftool samples/sample2.png
```

Observed metadata included:
- File name
- File size
- File modification time
- File type
- MIME type
- Image width and height
- Bit depth
- Compression method
- Image size
- Megapixel count

No author, creator, camera model, GPS coordinates, or software metadata were present in the tested PNG screenshots.

This demonstrates that metadata availability depends on the file type and the software or device used to create the file.

## Directory Analysis
ExifTool was also executed against the complete samples directory:

```bash
exiftool samples/
```

The complete result was stored in:

```text
outputs/exiftool-all-files.txt
```

## CSV Export
Metadata for the complete samples directory was exported using:

```bash
exiftool -csv samples/ > outputs/metadata.csv
```

The export contained metadata for 2 image files.

## Key Lesson
Metadata can reveal technical or organizational information such as authors, usernames, software, devices, timestamps, and potentially geographic information.

In this execution, the PNG screenshots contained mainly technical image metadata and did not expose sensitive author or location information.

Metadata should therefore be reviewed before files are published publicly.

## Evidence
- evidence/screenshots/06-exiftool-file-metadata.png
- evidence/screenshots/07-exiftool-csv-export.png

## Outputs
- outputs/exiftool-version.txt
- outputs/exiftool-supported-formats.txt
- outputs/exiftool-sample2-png.txt
- outputs/exiftool-all-files.txt
- outputs/metadata.csv
