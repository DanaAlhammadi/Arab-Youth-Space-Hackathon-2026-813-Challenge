# THABAT Data Licence and Security Log

## Purpose

This document records the legal-use, storage, publication, attribution,
and security conditions for every dataset considered during the THABAT
data-exploration sprint.

No dataset may be used in the final PoC until its source, access terms,
storage location, and sharing restrictions have been recorded.

Unknown information must be written as `TO VERIFY` or `UNKNOWN`.
Do not guess a licence, access right, or redistribution permission.

---

# Non-Negotiable Rules

1. Raw commercial or competition-restricted imagery must not be uploaded
   to GitHub.

2. Large raw satellite files must be stored only in the private Google
   Drive folder:

   `Restricted_Data`

3. Google Drive access must remain restricted to the five team members.

4. Never place passwords, API keys, access tokens, signed download URLs,
   private account details, or credentials in:

   - GitHub
   - notebooks
   - screenshots
   - project documents
   - AI chats
   - public presentations

5. A preview image is not automatically permitted for public use.
   Public-display rights must be checked separately.

6. Derived maps or figures may be shared only when the provider's terms
   allow them to be published.

7. Every dataset must be recorded in:

   `data/data_manifest.csv`

8. If a licence is unclear, the dataset remains `CONDITIONAL` and must
   not be published until the provider or organizers clarify the terms.

---

# Storage Structure

The team uses the following private Google Drive structure:

```text
Restricted_Data/
├── 01_Hyperspectral/
│   ├── EnMAP/
│   ├── Tanager/
│   └── Satellite_813/
│
├── 02_High_Resolution/
│   ├── PlanetScope/
│   └── Competition_VHR/
│
├── 03_Multispectral/
│   └── Sentinel_2/
│
├── 04_Thermal/
│   └── Landsat/
│
├── 05_Land_Cover/
│   └── ESA_WorldCover/
│
├── 06_Field_Validation/
│   ├── Photos/
│   ├── Survey_Forms/
│   └── Reference_Records/
│
└── 07_Temporary_Downloads/
