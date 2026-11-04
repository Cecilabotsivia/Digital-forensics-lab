# DIGITAL FORENSICS HASH VERIFICATION RECORD

**Project:** Digital Forensics Lab  
**Case Name:** Case_001_Disk_Analysis  
**Case Number:** DFL-001  
**Examiner:** Cecil Abotsivia Yao  

---

## 1. Purpose

This document records the SHA-256 hash information for the original forensic evidence image.

Hash verification helps establish whether the evidence file has changed between documented verification points.

## 2. Evidence Details

| Attribute | Value |
|---|---|
| Evidence ID | E-001 |
| Filename | 2020JimmyWilson.E01 |
| Format | E01 / Expert Witness Format |
| File size | 309,818,835 bytes |
| Storage location | Evidence/Original/2020JimmyWilson.E01 |
| Hash algorithm | SHA-256 |

## 3. Initial Hash Record

The initial SHA-256 hash recorded for the downloaded evidence image is:

`6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5`

This is the baseline value for subsequent comparison.

## 4. Verification Procedure

The following PowerShell command can be used to recalculate the SHA-256 hash:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath "$env:USERPROFILE\Desktop\DIGITAL-FORENSICS-LAB\Evidence\Original\2020JimmyWilson.E01"
```

The newly calculated hash should be compared character by character with the initial hash.

## 5. Verification Results

| Verification stage | SHA-256 result | Status |
|---|---|---|
| Initial calculation | 6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5 | Recorded |
| Subsequent calculation | 6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5 | Match confirmed |
| Publisher hash comparison | Not available | Not independently confirmed |

**Verification date:** 3 November 2026

## 6. Interpretation and Conclusion

The SHA-256 hash recalculated using Windows PowerShell matches the initial recorded baseline exactly.

This confirms that the evidence file has remained unchanged between the two documented hash calculations.

The matching hash provides evidence of file integrity during this period. However, it does not independently establish that the downloaded image matches the publisher's original because a trusted publisher-provided hash has not yet been confirmed.

**Integrity verification status: PASSED — matching SHA-256 values.**

**Prepared by:**  
Cecil Abotsivia Yao  
Digital Forensics Lab  
**Status:** Initial hash recorded – repeat verification pending
