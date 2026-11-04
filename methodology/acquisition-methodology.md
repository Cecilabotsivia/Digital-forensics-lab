# DIGITAL FORENSICS ACQUISITION AND PRESERVATION METHODOLOGY

**Project:** Digital Forensics Lab  
**Case Name:** Case_001_Disk_Analysis  
**Case Number:** DFL-001  
**Examiner:** Cecil Abotsivia Yao  
**Evidence ID:** E-001  

---

## 1. Introduction

This document describes the methodology used to identify, obtain, document and preserve the forensic evidence used in this educational digital forensics project.

The project uses a publicly available forensic disk image from the National Institute of Standards and Technology (NIST) Computer Forensic Reference Data Sets (CFReDS).

The objective is to maintain evidence integrity and establish a documented process for subsequent examination.

## 2. Evidence Source

The evidence image used in this project is:

| Attribute | Description |
|---|---|
| Filename | 2020JimmyWilson.E01 |
| Format | Expert Witness Format (E01) |
| Source | NIST CFReDS |
| Evidence ID | E-001 |
| File size | 309,818,835 bytes |

The image was downloaded from the publicly available sample dataset.

## 3. Acquisition Procedure

The following steps describe the acquisition process:

1. Identified a suitable forensic sample from the NIST CFReDS collection.
2. Downloaded the E01 forensic image.
3. Stored the downloaded file in the local project directory under `Evidence/Original/`.
4. Retained the original evidence file without intentional modification.
5. Recorded the evidence filename, format, file size and storage location.
6. Calculated the initial SHA-256 hash using Windows PowerShell.
7. Documented the initial hash in the evidence register.

**Note:** This project uses a pre-existing forensic image. It does not involve creating a new forensic image from a physical storage device.

## 4. Evidence Preservation

The original evidence image is retained at:

`Evidence/Original/2020JimmyWilson.E01`

The following preservation practices apply:

- The original evidence file is retained separately from examination documentation.
- The original image is not intentionally modified.
- Examination is performed using Autopsy.
- Hash values are documented to support integrity verification.
- The original evidence is excluded from the public GitHub repository.
- The Autopsy case database is retained locally and excluded from public upload.

## 5. Hash Calculation and Verification

SHA-256 was selected as the cryptographic hash algorithm for documenting the evidence file's integrity.

The following PowerShell command was used:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath "$env:USERPROFILE\Desktop\DIGITAL-FORENSICS-LAB\Evidence\Original\2020JimmyWilson.E01"
```

Initial SHA-256 value:

`6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5`

A subsequent calculation produced the same value.

This matching result supports the conclusion that the file remained unchanged between the two documented calculations.

## 6. Evidence Handling Principles

The following principles guide evidence handling throughout this project:

1. Preserve the original evidence.
2. Maintain accurate evidence identification records.
3. Document relevant actions and examination procedures.
4. Use cryptographic hashes to support integrity verification.
5. Avoid unsupported conclusions.
6. Keep private examination data separate from public documentation.
7. Maintain a clear record of limitations and outstanding tasks.

## 7. Limitations

This is an educational examination using a pre-existing public forensic image.

The acquisition process described here is the download and preservation of an existing forensic dataset, not a physical-device acquisition conducted by the examiner.

A publisher-provided hash has not yet been independently confirmed.

## 8. Conclusion

The forensic image was downloaded from the NIST CFReDS sample collection, stored in the local project directory and documented as evidence item E-001.

An initial SHA-256 hash was recorded and a subsequent calculation produced a matching value.

These procedures provide a documented starting point for the examination while preserving the distinction between the original evidence and the public project documentation.

---

**Prepared by:**  
Cecil Abotsivia Yao  
Digital Forensics Lab
