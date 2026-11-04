# Digital Forensics Lab

An authorised digital forensics training project documenting forensic evidence handling, SHA-256 integrity verification, disk image examination and reporting using Autopsy.

## Project Overview

This project demonstrates a practical digital forensics workflow using a publicly available forensic disk image from the NIST Computer Forensics Reference Data Sets (CFReDS).

The examination focuses on evidence preservation, forensic image verification, disk and file-system structures, user-profile artefacts, Windows system artefacts and the documentation of observed findings.

This is an educational portfolio project. It is not an investigation of a real-world criminal allegation.

## Project Objectives

- Understand the digital evidence examination process.
- Preserve the original forensic image.
- Calculate and record SHA-256 hashes.
- Examine a forensic disk image using Autopsy.
- Identify partitions and file-system structures.
- Explore selected Windows artefacts.
- Document observations, limitations and findings.
- Develop practical digital forensics and reporting skills.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Autopsy | Digital forensic examination |
| Windows 11 Pro | Examination environment |
| PowerShell | SHA-256 hash calculation |
| NIST CFReDS | Public forensic training dataset |
| GitHub | Project documentation and version control |

## Evidence Information

| Field | Recorded information |
|---|---|
| Case reference | DFL-001 |
| Case name | Case_001_Disk_Analysis |
| Evidence filename | 2020JimmyWilson.E01 |
| Evidence format | EWF / E01 |
| Evidence source | NIST CFReDS |
| Evidence file size | 309,818,835 bytes |
| Examination tool | Autopsy |

**Evidence handling:** The original E01 image is retained locally and is not uploaded to this public repository. The Autopsy case database and private examination material are also excluded.

## Evidence Integrity

The SHA-256 hash was calculated locally using PowerShell.

**Recorded SHA-256:**

`6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5`

The recorded value was checked against a subsequent local hash calculation and matched.

This confirms consistency between those local calculations. It does not independently establish a match against a publisher-provided reference hash.

## Examination Methodology

The project follows a structured examination process:

1. Identify and document the forensic evidence.
2. Preserve the original evidence image.
3. Calculate and record its SHA-256 hash.
4. Create an Autopsy case.
5. Add the E01 image as a data source.
6. Examine the available partition and file-system structures.
7. Review selected Windows directories and artefacts.
8. Record observations and relevant limitations.
9. Prepare a findings report.

## Preliminary Examination Observations

The following structures have been observed during the examination:

- The forensic image was recognised by Autopsy.
- A Microsoft Reserved Partition and a Basic Data Partition were identified.
- The main data partition was identified as NTFS.
- Windows directory structures and multiple user-profile directories were observed.
- Windows Prefetch files were identified for further examination.
- A Windows user registry hive (`NTUSER.DAT`) was identified for further examination.

These are preliminary observations. The presence of a file, directory or artefact alone does not establish that a particular user performed an activity.

## Repository Contents

| File | Description |
|---|---|
| `.gitignore` | Excludes original evidence, case databases and temporary files |
| `evidence-register.md` | Evidence identification and handling record |
| `hash-verification.md` | SHA-256 integrity record |
| `acquisition-methodology.md` | Evidence acquisition and preservation methodology |
| `examination-methodology.md` | Examination procedures |
| `findings-report.md` | Documented preliminary findings |

## Limitations

- This is an educational examination using a public training image.
- The original evidence image is not distributed through this repository.
- Some identified artefacts have not yet undergone detailed analysis.
- No conclusion about user intent or criminal activity is made.
- Findings may be updated as further examination is completed.

## References

- [NIST Computer Forensics Reference Data Sets (CFReDS)](https://cfreds.nist.gov/)
- [Autopsy Digital Forensics Platform](https://www.autopsy.com/)
- [The Sleuth Kit](https://www.sleuthkit.org/)

## Project Status

**Status:** In progress

Further work will include detailed Windows artefact examination, timeline analysis where supported by available evidence, additional screenshots and refinement of the findings report.

---

*Developed as part of an educational digital forensics learning and portfolio project.*
