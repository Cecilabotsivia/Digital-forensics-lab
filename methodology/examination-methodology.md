# DIGITAL FORENSICS EXAMINATION METHODOLOGY

**Project:** Digital Forensics Lab  
**Case Name:** Case_001_Disk_Analysis  
**Case Number:** DFL-001  
**Examiner:** Cecil Abotsivia Yao  
**Evidence ID:** E-001  
**Forensic Tool:** Autopsy  

---

## 1. Introduction

This document describes the procedures used to examine the forensic disk image `2020JimmyWilson.E01` using Autopsy.

The examination focuses on identifying the disk structure, file system, user profile directories, Windows operating system artefacts and potential sources of digital evidence.

## 2. Examination Environment

| Component | Description |
|---|---|
| Host operating system | Windows 11 Pro |
| Forensic platform | Autopsy |
| Evidence format | E01 |
| Case name | Case_001_Disk_Analysis |
| Case number | DFL-001 |
| Time zone displayed | Africa/Accra |

## 3. Examination Objectives

The examination aims to:

1. Confirm that the evidence image can be recognised by Autopsy.
2. Identify partitions and their structures.
3. Determine the file system of the main data partition.
4. Identify user profile directories.
5. Locate relevant Windows system artefacts.
6. Identify potential sources of user activity evidence.
7. Document observations and limitations.

## 4. Examination Procedure

### 4.1 Case creation

An Autopsy case was created with the following details:

- Case name: `Case_001_Disk_Analysis`
- Case number: `DFL-001`

### 4.2 Adding the evidence image

The E01 image was added as a data source in Autopsy.

Autopsy recognised the image and displayed its logical size and sector information.

### 4.3 Partition examination

The partition structure was reviewed to identify allocated and unallocated areas.

The examination identified a Microsoft Reserved Partition and a Basic Data Partition, alongside unallocated sector ranges.

### 4.4 File system examination

The main Basic Data Partition was examined.

Autopsy identified NTFS metadata files, including:

- `$MFT`
- `$MFTMirr`
- `$Bitmap`
- `$Boot`
- `$LogFile`

### 4.5 User profile examination

The `USERS` directory was reviewed to identify available user profile directories.

The Jimmy Wilson profile was selected for preliminary examination.

### 4.6 Windows artefact examination

The Windows directory was reviewed to identify potential forensic artefacts.

The Prefetch directory and registry hive files were identified for further investigation.

## 5. Artefacts Identified

The preliminary examination identified:

- Five user profile directory names.
- The Jimmy Wilson user profile directory.
- An `NTUSER.DAT` registry hive.
- Windows operating system directories.
- Five Windows Prefetch files.
- NTFS metadata files.

The presence of these artefacts does not independently establish user activity or malicious behaviour.

## 6. Documentation and Reporting

Observations are recorded in the preliminary findings report.

Relevant evidence details are documented in the evidence register and hash verification record.

Screenshots may be captured to support important examination stages, provided they do not expose unnecessary personal or sensitive information.

## 7. Limitations

The following areas require further examination:

1. Internal Prefetch metadata.
2. Registry hive contents.
3. Browser history and application artefacts.
4. Relevant event logs.
5. Deleted-file and unallocated-space artefacts.
6. Timeline reconstruction.
7. Final review of Autopsy ingest results.

No conclusion regarding malicious activity is made at this preliminary stage.

## 8. Conclusion

Autopsy was used to examine the E01 disk image and identify its partition structure, NTFS file system, user profile directories and selected Windows artefacts.

The examination provides a foundation for further analysis.

Additional artefact examination and timeline reconstruction are necessary before a final forensic conclusion can be reached.

---

**Prepared by:**  
Cecil Abotsivia Yao  
Digital Forensics Lab
