# DIGITAL FORENSICS LABORATORY REPORT

**Project:** Digital Forensics Lab  
**Case Name:** Case_001_Disk_Analysis  
**Case Number:** DFL-001  
**Examiner:** Cecil Abotsivia Yao  
**Report Type:** Preliminary Forensic Examination Report  
**Status:** In Progress  
**Evidence Image:** 2020JimmyWilson.E01  
**Examination Tool:** Autopsy Digital Forensic Platform  

---

## 1. Executive Summary

This report documents a preliminary forensic examination of a disk image named `2020JimmyWilson.E01`, obtained from the National Institute of Standards and Technology (NIST) Computer Forensic Reference Data Sets (CFReDS).

The examination was conducted using Autopsy to identify the disk structure, partitions, file system, user profiles, Windows operating system directories, and selected system artefacts.

The image was successfully recognised by Autopsy. The examination identified a Microsoft Reserved Partition, a Basic Data Partition, an NTFS file system, several user profile directories, and Windows Prefetch files.

The findings in this report are preliminary. Further examination of registry artefacts, application data, browser history, Prefetch contents, and file-system timelines is required before drawing broader conclusions about user activity or possible malicious activity.

## 2. Objectives

The objectives of this examination were to:

1. Identify and document the forensic evidence image.
2. Establish an initial record of the evidence file's integrity.
3. Examine the disk image structure and partition layout.
4. Identify the file system used by the main data partition.
5. Identify user profile directories.
6. Examine selected Windows operating system artefacts.
7. Document preliminary findings and recommend further analysis.

## 3. Scope and Authorisation

This project is an educational digital forensics exercise using a publicly available forensic reference dataset.

The examination is limited to the evidence image identified in this report and the artefacts observed during the documented examination.

No conclusions are made about the real-world identity, intentions, or activities of individuals based solely on directory names or the presence of files.

## 4. Evidence Identification and Preservation

### 4.1 Evidence details

| Attribute | Description |
|---|---|
| Evidence filename | 2020JimmyWilson.E01 |
| Evidence format | Expert Witness Format (EWF/E01) |
| Source | NIST CFReDS sample dataset |
| File size | 309,818,835 bytes |
| Local evidence location | Evidence/Original/2020JimmyWilson.E01 |
| SHA-256 | 6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5 |

### 4.2 Integrity considerations

A SHA-256 hash was calculated for the downloaded evidence file and recorded as the initial baseline.

The hash is:

`6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5`

This value should be recalculated during subsequent verification to determine whether the local evidence file remains unchanged.

The baseline has not yet been independently compared with a publisher-provided hash. Therefore, it should not be described as a verified publisher match.

The original evidence image is retained in the local project folder and should not be modified.

## 5. Examination Environment and Tools

| Component | Description |
|---|---|
| Operating system | Windows 11 Pro |
| Forensic tool | Autopsy |
| Evidence format | E01 |
| Case name | Case_001_Disk_Analysis |
| Case number | DFL-001 |
| Time zone displayed | Africa/Accra |
| Examination type | Disk image examination |

Autopsy was used to load the evidence image, inspect its partition structure, browse the recognised file system, and identify selected system artefacts.

## 6. Disk Image and Partition Examination

The evidence image was successfully added to the Autopsy case.

Autopsy displayed a logical image size of 891,289,600 bytes and a sector size of 512 bytes.

The logical image size differs from the physical E01 container file size because E01 images can use compression and contain additional format information.

### 6.1 Partition structure

The following partition structures were identified:

| Volume | Partition type | Sector range | Status |
|---|---|---|---|
| vol1 | Unallocated | 0–33 | Unallocated |
| vol4 | Microsoft Reserved Partition | 34–65,569 | Allocated |
| vol5 | Unallocated | 65,570–65,663 | Unallocated |
| vol6 | Basic Data Partition | 65,664–1,736,831 | Allocated |
| vol7 | Unallocated | 1,736,832–1,740,799 | Unallocated |

### 6.2 Partition observations

The examination identified a Microsoft Reserved Partition and a Basic Data Partition.

Autopsy displayed a warning that it could not determine a conventional file system type for the Microsoft Reserved Partition.

This warning does not, by itself, indicate evidence corruption. Microsoft Reserved Partitions are not normally formatted with a conventional user data file system.

The Basic Data Partition was examined separately and contained an identifiable NTFS file system.

## 7. File System Examination

The main data partition, identified as `vol6`, was recognised as NTFS.

The following NTFS metadata files and directories were observed:

- `$MFT`
- `$MFTMirr`
- `$Bitmap`
- `$Boot`
- `$LogFile`
- `$Secure`
- `$Extend`
- `$UpCase`

These entries are associated with the structure and management of an NTFS file system.

The root directory also contained entries including:

- `$OrphanFiles`
- `$Extend`
- `$RECYCLE.BIN`
- `$Unalloc`
- `Documents and Settings`
- `USERS`
- `Users`
- `Windows`

The presence of `$OrphanFiles` and `$Unalloc` in Autopsy does not, by itself, prove that a user intentionally deleted files. Their contents and associated metadata require further examination.

## 8. User Profile Examination

The following profile directory names were identified under the `USERS` directory:

1. BillyBob
2. Fred Flintstone
3. James Russell
4. Jimmy Wilson
5. Joe Nameless

The presence of these directories establishes that corresponding profile directories exist in the examined image. It does not independently establish who used the computer or whether each profile was actively used.

### 8.1 Jimmy Wilson profile

The following profile path was examined:

`/img_2020JimmyWilson.E01/vol_vol6/USERS/Jimmy Wilson/`

The directory contained entries including:

- AppData
- Application Data
- Contacts
- Cookies
- Desktop
- Documents
- Downloads
- Favorites
- Links
- Local Settings
- Music
- My Documents
- NetHood
- Pictures
- PrintHood
- Recent
- Saved Games
- Searches
- SendTo
- Start Menu
- Templates
- Videos

These directories provide potential locations for further examination of user activity, application usage, and saved data.

### 8.2 Registry hive metadata

The following file was identified in the Jimmy Wilson profile:

| Attribute | Value |
|---|---|
| Filename | NTUSER.DAT |
| Size | 786,432 bytes |
| File type | Windows Registry hive |
| MD5 | 16cfec32d8949a43ba7b148e0f6813f8 |
| SHA-256 | 7a02ab527e73ecd914a9e14251d13828e3dc371dcd558d27f3deb55c1a3da224 |

Additional registry-related files were also identified:

- `ntuser.dat.LOG1`
- `ntuser.dat.LOG2`
- `NTUSER.DAT{016888bd-6c6f-11de-8d1d-001e0bcde3ec}.TM.blf`
- Transaction log container files

The NTUSER.DAT registry hive may contain useful information about user-specific settings and system activity. Its contents have not yet been analysed.

## 9. Windows Operating System Examination

The `Windows` directory was identified in the main NTFS partition.

Observed directories included:

- `Boot`
- `Fonts`
- `Globalization`
- `Logs`
- `Microsoft.NET`
- `Prefetch`
- `System32`
- `SysWOW64`
- `Temp`
- `winsxs`
- `SoftwareDistribution`
- `servicing`
- `ServiceProfiles`

The presence of these directories is consistent with a Windows operating system installation.

Their existence alone does not establish when the computer was used or what activities were performed.

## 10. Windows Prefetch Examination

The following five Prefetch files were identified under:

`vol6/Windows/Prefetch/`

| Prefetch file | Size (bytes) |
|---|---:|
| DLLHOST.EXE-766398D2.pf | 29,700 |
| RUNDLL32.EXE-411A328D.pf | 64,266 |
| WMIADAP.EXE-F8DFDFA2.pf | 18,810 |
| WMIPRVSE.EXE-1628051C.pf | 35,022 |
| WUAUCLT.EXE-70318591.pf | 50,736 |

These filenames correspond to Windows components and utilities.

Prefetch artefacts can contain useful execution-related metadata. However, the internal contents of these files have not yet been examined.

The file-system timestamps observed during browsing must not be treated as confirmed application execution times without analysing the Prefetch metadata.

## 11. Preliminary Findings

| No. | Observation | Preliminary interpretation |
|---|---|---|
| 1 | E01 image successfully recognised by Autopsy | Evidence image was readable by the examination tool |
| 2 | Microsoft Reserved Partition identified | Partition structure includes an MSR partition |
| 3 | Basic Data Partition identified | A main data partition is present |
| 4 | NTFS metadata files identified | Main data partition uses NTFS |
| 5 | Five user profile directory names identified | Multiple profile directories exist |
| 6 | Jimmy Wilson profile directory identified | Profile contains potential user-related artefacts |
| 7 | NTUSER.DAT identified | Registry hive is available for further analysis |
| 8 | Windows Prefetch directory identified | Potential execution artefacts are available |
| 9 | Five Prefetch files identified | Selected Windows component Prefetch files require examination |

These observations are limited to the artefacts identified so far. They do not establish malicious activity, intentional deletion, or the identity of a computer user.

## 12. Limitations

The following activities remain outstanding:

1. Recalculate the SHA-256 hash and compare it with the recorded baseline.
2. Examine the internal metadata of the identified Prefetch files.
3. Analyse the NTUSER.DAT registry hive.
4. Examine relevant AppData directories.
5. Examine browser history and other browser-related artefacts.
6. Examine Recycle Bin contents and relevant deleted-file artefacts.
7. Review relevant event logs and system activity records.
8. Develop a timeline using validated artefact timestamps.
9. Review Autopsy ingest results and document any errors or warnings.

Until these activities are completed, the report should remain classified as preliminary.

## 13. Recommendations and Further Examination

The next stage should prioritise:

- Integrity verification of the original evidence image.
- Detailed Prefetch analysis to identify available execution metadata.
- Registry analysis to identify relevant user and system configuration artefacts.
- Browser artefact examination, where available.
- Examination of deleted and unallocated data using appropriate forensic methods.
- Timeline analysis to correlate artefacts and establish event sequences.
- Documentation of each finding with its source path, relevant timestamps, and supporting screenshots.

All further examination should preserve the original evidence and maintain a clear record of actions performed.

## 14. Conclusion

The preliminary examination successfully identified the disk image structure, a main NTFS partition, several user profile directories, Windows system directories, and selected Windows Prefetch and registry artefacts.

The findings provide a foundation for further forensic examination. However, the available observations are not sufficient to determine the full history of system use or establish whether suspicious or malicious activity occurred.

Further analysis and integrity verification are required before a final forensic conclusion can be made.

---

## 15. References

1. National Institute of Standards and Technology (NIST), Computer Forensic Reference Data Sets (CFReDS): https://cfreds.nist.gov/
2. Autopsy Digital Forensics Platform: https://www.autopsy.com/
3. Sleuth Kit Documentation: https://www.sleuthkit.org/
4. NIST Computer Security Resource Center: https://csrc.nist.gov/

---

**Report prepared by:**  
Cecil Abotsivia Yao  
Digital Forensics Lab  
**Report status:** Preliminary – Further examination required