# Category Map & Priority Rationale

The source page lists ten original categories. This edition retains all ten source category labels and adds extended descriptive names. The order below is a new editorial ranking based on defensive impact.

| New rank | Extended name | Original source name | Why it is placed here |
|---:|---|---|---|
| 01 | Sensitive Configuration & Deployment Hygiene | Configuration | Configuration mistakes can expose secrets and internal architecture. |
| 02 | Backup, Archive & Temporary File Exposure | Files & backups | Old copies and archives may contain superseded or confidential material. |
| 03 | Diagnostic Logs & Debugging Hygiene | Logs & debug | Logs and debug output may include personal data and internal details. |
| 04 | Cloud Storage & Shared Resource Governance | Cloud storage | Incorrect sharing permissions can expose stored resources. |
| 05 | Source Control & Software Supply-Chain Hygiene | Source control | Repository history and development artefacts may reveal secrets or internals. |
| 06 | Directory Indexing & Public File Structure | Directory listings | Automatic indexes can reveal unlinked public paths and files. |
| 07 | Application Errors & Information Disclosure | Error output | Detailed error output can disclose implementation details. |
| 08 | Public Documents & Metadata Governance | Documents | Documents may contain hidden content and metadata. |
| 09 | Application Interfaces & Access-Control Boundaries | Interfaces | Public interfaces need clear separation from protected functions. |
| 10 | Public Records, Privacy & Data Minimisation | Public records | Public information must still be handled proportionately and lawfully. |

This is an editorial ranking for learning and defensive review. It is not the ranking used by the source website.
