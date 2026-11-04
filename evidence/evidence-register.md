# DIGITAL FORENSICS EVIDENCE REGISTER

**Project:** Digital Forensics Lab  
**Case Name:** Case_001_Disk_Analysis  
**Case Number:** DFL-001  
**Examiner:** Cecil Abotsivia Yao  
**Register Status:** Initial Record  

---

## 1. Purpose

This evidence register records the digital evidence item used in the examination, its source, storage location, identifying details, and integrity information.

The register supports evidence identification, preservation, traceability, and accountability throughout the examination.

## 2. Evidence Inventory

| Field | Description |
|---|---|
| Evidence ID | E-001 |
| Evidence filename | 2020JimmyWilson.E01 |
| Evidence type | Forensic disk image |
| File format | Expert Witness Format (E01/EWF) |
| Source | NIST Computer Forensic Reference Data Sets (CFReDS) |
| File size | 309,818,835 bytes |
| Local storage location | Evidence/Original/2020JimmyWilson.E01 |
| SHA-256 baseline | 6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5 |
| Examination tool | Autopsy |
| Associated case | Case_001_Disk_Analysis |
| Case number | DFL-001 |
| Evidence status | Retained as original; further integrity verification required |

## 3. Evidence Description

The evidence item is an E01 forensic disk image obtained from the NIST CFReDS public sample dataset.

The image was added to Autopsy for examination. Autopsy recognised the image and displayed a logical image size of 891,289,600 bytes with a sector size of 512 bytes.

The logical image size is distinct from the compressed E01 container file size.

## 4. Integrity Information

The SHA-256 hash recorded for the downloaded evidence file is:

`6C18F662744D55E2769D9510F6173F04DAB668C42B67EF27B675D22E628B4ED5`

This value serves as the initial hash baseline.

**Verification status:** Pending repeat calculation and comparison.

No claim is made that this value matches a publisher-provided hash because an independent publisher hash has not yet been confirmed.

## 5. Evidence Preservation Requirements

The following preservation measures apply:

1. Retain the original E01 image in `Evidence/Original/`.
2. Do not edit, rename, or overwrite the original evidence image.
3. Perform examination using the forensic tool and the evidence image as a source.
4. Recalculate the SHA-256 hash to verify integrity.
5. Record any additional evidence files separately.
6. Keep Autopsy case databases and private examination material outside the public GitHub repository.
7. Do not upload the original evidence image to GitHub.

## 6. Evidence Storage Structure

The intended local structure is:

```text
DIGITAL-FORENSICS-LAB/
│
├── Evidence/
│   ├── Original/
│   │   └── 2020JimmyWilson.E01
│   │
│   ├── evidence-register.md
│   └── hash-verification.md
│
├── methodology/
├── findings/
├── screenshots/
├── references/
└── autopsy_cases/
```

The original evidence image must remain in the `Original` directory.

## 7. Chain of Custody Record

| Date/Time | Activity | Person responsible | Remarks |
|---|---|---|---|
| To be confirmed | Public sample dataset downloaded | Cecil Abotsivia Yao | Original E01 file retained locally |
| To be confirmed | SHA-256 baseline calculated | Cecil Abotsivia Yao | Hash recorded in this register |
| To be confirmed | Evidence image added to Autopsy | Cecil Abotsivia Yao | Case DFL-001 |
| Pending | SHA-256 recalculated | Cecil Abotsivia Yao | Integrity verification outstanding |

Dates and times should be completed using actual records where available. Do not invent timestamps.

## 8. Evidence Handling Notes

This register documents one primary evidence item.

Any extracted files or additional artefacts selected for separate examination should be assigned their own evidence identifiers where appropriate and documented with their source paths and hashes.

The register should be updated whenever the evidence inventory or preservation status changes.

---

**Prepared by:**  
Cecil Abotsivia Yao  
Digital Forensics Lab  
**Register status:** Initial record – integrity verification pending
