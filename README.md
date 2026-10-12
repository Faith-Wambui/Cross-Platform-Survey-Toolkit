# Cross-Platform Survey Portability Toolkit

[![XLSForm Standard](https://img.shields.io/badge/XLSForm-v1.0-brightgreen.svg)](https://xlsform.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A reference implementation and engineering guide for building portable, multi-platform household baseline surveys. This toolkit uses a single **XLSForm master specification** as the source of truth and documents the operational nuances, field-type constraints, dynamic skip logic, and cascading select behaviors when deploying across **KoboToolbox**, **SurveyCTO**, and **CommCare**.

---

## 🎯 Project Overview

* **Domain Context:** Smallholder Farmer Household Baseline Survey (Kenya context).
* **Questionnaire Scope:** 58 questions organized into 6 core sections:
  1. **Section A:** Registration & Consent (GPS, Admin Hierarchies, Enumerator metadata)
  2. **Section B:** Household Roster (`begin_repeat` loop, Demographics, Education, Occupation)
  3. **Section C:** Land & Farming (Tenure, Calculated Land Totals, Cascading Crop Selection)
  4. **Section D:** Livestock (Ownership, Asset Counts, Media Attachment)
  5. **Section E:** Income & Food Security (Livelihood Bands, Credit, Shock Matrix)
  6. **Section F:** Closing & Observations (Duration Calculations, Signature Capture)
* **Core Standards:** Dual-language localization (`label::English` & `label::Kiswahili`), standard ODK XPath expressions, and cascading geographic hierarchies (8 Regions, 47 Counties, Sub-Counties).

---

## 📁 Repository Structure

```text
cross-platform-survey-toolkit/
├── README.md                   # Project overview & operational guidelines
├── .gitignore                  # Git tracking rules
├── forms/                      # Form specifications & platform exports
│   ├── reference-form.xlsx     # Source-of-truth master XLSForm
│   └── kobo-export.xlsx        # KoboToolbox compiled output
├── docs/                       # Technical documentation & platform logs
│   ├── translation-notes.md    # Multi-platform conversion & syntax log
│   └── platform-comparison.md # Comparative feature matrix (Kobo vs SurveyCTO vs CommCare)
├── lint/                       # Automated validation scripts (Python/XLSForm)
└── screenshots/                # Validation run screenshots & UI logs