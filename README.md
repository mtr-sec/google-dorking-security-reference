# Google Dork Reference — Ranked Defensive Learning Guide

**Maintainer:** [MTR-SEC](https://github.com/mtr-sec)

An educational reference to search operators, public indexing risks and defensive website administration.

## About this edition

The source page, [Google-Dorks.com — Dorks List](https://google-dorks.com/list/), states that it contains 200 patterns across ten categories. This repository reorganises the ten category themes into a priority order based on defensive impact and adds clearer, more descriptive category names.

**Important:** Here Instead, this edition uses newly written, low-risk examples that focus on intentionally public content, alongside explanations and remediation guidance. Refer to the source page for its original entries.

## Priority ranking

| Rank | Extended category name | Original category |
|---:|---|---|
| 01 | Sensitive Configuration & Deployment Hygiene | Configuration |
| 02 | Backup, Archive & Temporary File Exposure | Files & backups |
| 03 | Diagnostic Logs & Debugging Hygiene | Logs & debug |
| 04 | Cloud Storage & Shared Resource Governance | Cloud storage |
| 05 | Source Control & Software Supply-Chain Hygiene | Source control |
| 06 | Directory Indexing & Public File Structure | Directory listings |
| 07 | Application Errors & Information Disclosure | Error output |
| 08 | Public Documents & Metadata Governance | Documents |
| 09 | Application Interfaces & Access-Control Boundaries | Interfaces |
| 10 | Public Records, Privacy & Data Minimisation | Public records |

The rank is a defensive-learning priority, not a statement that the source website ranks its categories this way.

## How to use

1. Read `SAFE_USAGE.md` before using any search examples.
2. Open `GOOGLE_DORKS_CATALOG.md`.
3. Start with Priority 01 and work down the ranking.
4. Keep `example.com` as the placeholder while learning.
5. For a real self-audit, use only a domain you own or have explicit written permission to assess.
6. Read the explanation and remediation note for each entry.
7. Record only non-sensitive findings. If private information appears unexpectedly, stop and follow the steps in `SAFE_USAGE.md`.

### Search examples

The examples are ordinary search queries about public-facing pages and documentation. Copy a safe example into a search engine if you want to understand how the operator behaves. External searches require an internet connection.

This repository is documentation only. It does not scan websites, access servers, download files or run tests.

## Maintainer

**MTR-SEC** — https://github.com/mtr-sec

## Disclaimer

The category themes and source reference are collected from publicly available internet resources. Explanations and safe examples in this repository are independently written for education and defensive awareness. Third-party material remains the property of its respective publishers.

Educational purpose only. Use search operators responsibly, respect privacy, comply with applicable laws and stay within written authorisation. The maintainer does not encourage unauthorised access, data collection, exploitation or disruption.

No software licence is included in this repository.
