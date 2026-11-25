# Google Dork Reference — Ranked Defensive Catalogue

**Maintainer:** [MTR-SEC](https://github.com/mtr-sec)  
**Scope:** Educational awareness, authorised self-auditing and defensive website administration.

> The source website reports 200 patterns across ten categories. This file preserves all ten category themes, but does not reproduce the source's 200 query strings verbatim. The examples below are newly written, safer examples about intentionally public material. See [SOURCES.md](SOURCES.md).

## Operator quick reference

| Operator | Meaning | Safe example |
|---|---|---|
| `site:` | Restricts results to a domain or URL prefix. | `site:example.com about` |
| `filetype:` | Restricts results to a file type. | `site:example.com filetype:pdf brochure` |
| `ext:` | Commonly used as a file-extension filter. | `site:example.com ext:pdf newsletter` |
| `"phrase"` | Searches for an exact phrase. | `site:example.com "annual report"` |
| `-word` | Excludes a word from results. | `site:example.com events -archive` |
| `OR` | Searches for either term. | `site:example.com news OR updates` |
| `after:` | Limits results to pages dated after a date. | `site:example.com after:2024-01-01` |
| `before:` | Limits results to pages dated before a date. | `site:example.com before:2025-01-01` |
| `intitle:` | Looks for a term in a page title. | `site:example.com intitle:newsletter` |
| `inurl:` | Looks for a term in a URL. | `site:example.com inurl:events` |
| `intext:` | Looks for a term in page text. | `site:example.com intext:"contact us"` |

Operator behaviour can change. Search results are not a complete inventory and do not prove that a site is secure or vulnerable.

---

# Priority 01 — Sensitive Configuration & Deployment Hygiene
**Original category:** Configuration  
**Why this ranks first:** Configuration and deployment mistakes can expose credentials, private keys, internal architecture or application settings.

### 1.1 Public configuration documentation
- **Purpose:** Find documentation intentionally explaining how a service is configured.
- **How it works:** A site restriction plus a public documentation phrase narrows the results.
- **Safe example:** `site:example.com "configuration guide"`
- **Defensive action:** Keep actual environment settings and secrets outside public web directories. Use a secrets manager and rotate any secret suspected of exposure.

### 1.2 Public setup instructions
- **Purpose:** Locate public setup guides for users or developers.
- **How it works:** Searches for a phrase commonly used in published help material.
- **Safe example:** `site:example.com "setup instructions"`
- **Defensive action:** Publish documentation, not live configuration files or local development artefacts.

### 1.3 Public deployment overview
- **Purpose:** Find a high-level deployment explanation.
- **How it works:** Searches public documentation on the selected domain.
- **Safe example:** `site:example.com deployment overview`
- **Defensive action:** Keep internal manifests, environment values and deployment credentials in controlled systems.

### 1.4 Certificate renewal help
- **Purpose:** Find user-facing or administrator-facing certificate renewal guidance.
- **How it works:** Searches for a public help phrase.
- **Safe example:** `site:example.com "certificate renewal"`
- **Defensive action:** Protect private keys; publish only appropriate certificate and renewal guidance.

### 1.5 Public service settings guide
- **Purpose:** Find an approved guide describing service settings.
- **How it works:** Uses a site restriction and a descriptive topic.
- **Safe example:** `site:example.com "service settings"`
- **Defensive action:** Review published examples to ensure they contain no real tokens, passwords, internal hostnames or private endpoints.

---

# Priority 02 — Backup, Archive & Temporary File Exposure
**Original category:** Files & backups  
**Why this ranks second:** Backups and temporary copies can retain older data or material that was not approved for public release.

### 2.1 Public PDF publications
- **Purpose:** Find approved PDF publications.
- **How it works:** `filetype:pdf` narrows results to PDF documents.
- **Safe example:** `site:example.com filetype:pdf publications`
- **Defensive action:** Keep backup copies outside the public document root and review each published file.

### 2.2 Public annual reports
- **Purpose:** Find annual reports intentionally published for readers.
- **How it works:** Combines a site restriction, file type and exact phrase.
- **Safe example:** `site:example.com filetype:pdf "annual report"`
- **Defensive action:** Review document content and metadata before release.

### 2.3 Public brochures
- **Purpose:** Find approved brochures and public information sheets.
- **How it works:** Searches a public topic within the selected domain.
- **Safe example:** `site:example.com brochure`
- **Defensive action:** Publish final approved versions only; remove drafts from public hosting.

### 2.4 Public presentations
- **Purpose:** Find presentations intentionally made public.
- **How it works:** Uses a file-type restriction and a topic.
- **Safe example:** `site:example.com filetype:pptx presentation`
- **Defensive action:** Review speaker notes, hidden slides and metadata before publication.

### 2.5 Public newsletters
- **Purpose:** Find newsletters published for public readership.
- **How it works:** Searches a public content term.
- **Safe example:** `site:example.com newsletter`
- **Defensive action:** Confirm attachments and contact information are appropriate for public release.

---

# Priority 03 — Diagnostic Logs & Debugging Hygiene
**Original category:** Logs & debug  
**Why this ranks third:** Diagnostic output can contain personal data, tokens, internal paths and detailed implementation information.

### 3.1 Public troubleshooting guide
- **Purpose:** Find approved troubleshooting articles.
- **How it works:** Searches a public help topic.
- **Safe example:** `site:example.com troubleshooting`
- **Defensive action:** Publish general instructions, not raw production logs.

### 3.2 Public error-handling documentation
- **Purpose:** Find user-facing documentation about application errors.
- **How it works:** Searches for a documentation phrase.
- **Safe example:** `site:example.com "error handling"`
- **Defensive action:** Return generic production errors and keep detailed diagnostics in access-controlled logging systems.

### 3.3 Public debug-mode guide
- **Purpose:** Find documentation explaining development and production modes.
- **How it works:** Searches a public technical topic.
- **Safe example:** `site:example.com "debug mode"`
- **Defensive action:** Disable verbose debugging in production and verify the deployed configuration.

### 3.4 Public logging policy
- **Purpose:** Find an organisation's published logging policy.
- **How it works:** Searches for an exact public phrase.
- **Safe example:** `site:example.com "logging policy"`
- **Defensive action:** Store logs outside public web roots, limit access and redact sensitive values.

### 3.5 Public service status information
- **Purpose:** Find public service-status explanations.
- **How it works:** Searches a public status topic.
- **Safe example:** `site:example.com status`
- **Defensive action:** Expose service summaries only, not internal diagnostic consoles.

---

# Priority 04 — Cloud Storage & Shared Resource Governance
**Original category:** Cloud storage  
**Why this ranks fourth:** Incorrect sharing permissions can make stored files accessible beyond their intended audience.

### 4.1 Public cloud storage guidance
- **Purpose:** Find user-facing documentation about cloud storage.
- **How it works:** Searches public documentation for a topic.
- **Safe example:** `site:example.com "cloud storage"`
- **Defensive action:** Review bucket, container and object permissions in the cloud provider's console.

### 4.2 Public data-sharing policy
- **Purpose:** Find published rules about sharing data.
- **How it works:** Searches a public policy phrase.
- **Safe example:** `site:example.com "data sharing"`
- **Defensive action:** Apply least privilege and time-limited sharing where supported.

### 4.3 Public backup policy
- **Purpose:** Find public explanations of backup practices.
- **How it works:** Searches for a public policy topic.
- **Safe example:** `site:example.com "backup policy"`
- **Defensive action:** Keep backup copies private, encrypted and separate from public website storage.

### 4.4 Public cloud architecture overview
- **Purpose:** Find high-level architecture material intentionally published.
- **How it works:** Searches a public documentation phrase.
- **Safe example:** `site:example.com "cloud architecture"`
- **Defensive action:** Do not publish credentials, private endpoints or sensitive infrastructure details.

### 4.5 Public file-sharing help
- **Purpose:** Find guidance for users who share files.
- **How it works:** Searches a public help phrase.
- **Safe example:** `site:example.com "file sharing"`
- **Defensive action:** Review default-sharing settings and periodically audit external shares.

---

# Priority 05 — Source Control & Software Supply-Chain Hygiene
**Original category:** Source control  
**Why this ranks fifth:** Development artefacts and repository history can contain secrets, internal discussions and information about software components.

### 5.1 Public open-source projects
- **Purpose:** Find project pages intentionally describing public software.
- **How it works:** Searches for a public project topic.
- **Safe example:** `site:example.com "open source"`
- **Defensive action:** Review repository visibility and remove secrets from history if they were committed.

### 5.2 Public release notes
- **Purpose:** Find release notes intended for users.
- **How it works:** Searches a public release phrase.
- **Safe example:** `site:example.com "release notes"`
- **Defensive action:** Review release notes for internal-only information before publication.

### 5.3 Public developer documentation
- **Purpose:** Find developer guides intentionally made public.
- **How it works:** Searches for a public developer topic.
- **Safe example:** `site:example.com developers`
- **Defensive action:** Keep repository metadata, build secrets and private issue discussions out of deployed public content.

### 5.4 Public contribution guide
- **Purpose:** Find contribution instructions for an open project.
- **How it works:** Searches for a public contribution topic.
- **Safe example:** `site:example.com contributing`
- **Defensive action:** Separate public contribution guidance from internal development workflows.

### 5.5 Public version history
- **Purpose:** Find public software version information.
- **How it works:** Searches for a version-history phrase.
- **Safe example:** `site:example.com "version history"`
- **Defensive action:** Publish supported-version information while protecting internal inventories and deployment secrets.

---

# Priority 06 — Directory Indexing & Public File Structure
**Original category:** Directory listings  
**Why this ranks sixth:** Automatic directory indexes can reveal file names and unlinked content. A directory name is not an access-control mechanism.

### 6.1 Public resource pages
- **Purpose:** Find curated public resource pages.
- **How it works:** Searches for the word `resources`.
- **Safe example:** `site:example.com resources`
- **Defensive action:** Disable automatic directory indexing unless there is a deliberate, reviewed public use case.

### 6.2 Public documentation index
- **Purpose:** Find a curated documentation landing page.
- **How it works:** Searches for a URL keyword.
- **Safe example:** `site:example.com inurl:documentation`
- **Defensive action:** Publish a curated index instead of exposing a raw server directory.

### 6.3 Public media gallery
- **Purpose:** Find public gallery pages.
- **How it works:** Searches for a public page topic.
- **Safe example:** `site:example.com gallery`
- **Defensive action:** Review media before publication and ensure unpublished drafts are not in public folders.

### 6.4 Public archive page
- **Purpose:** Find an organisation's intentionally published archive.
- **How it works:** Searches for a public page term.
- **Safe example:** `site:example.com archive`
- **Defensive action:** Apply retention rules and remove superseded material that should no longer be public.

### 6.5 Public downloads page
- **Purpose:** Find a curated public downloads page.
- **How it works:** Searches for a public page topic.
- **Safe example:** `site:example.com downloads`
- **Defensive action:** Review the directory contents and publish only approved downloadable material.

---

# Priority 07 — Application Errors & Information Disclosure
**Original category:** Error output  
**Why this ranks seventh:** Detailed errors can reveal internal paths, framework information or application implementation details.

### 7.1 Public help for common errors
- **Purpose:** Find help articles that explain common user-facing errors.
- **How it works:** Searches for a public help phrase.
- **Safe example:** `site:example.com "common errors"`
- **Defensive action:** Explain recovery steps without exposing internal traces.

### 7.2 Public technical support
- **Purpose:** Find official technical support pages.
- **How it works:** Searches a public support topic.
- **Safe example:** `site:example.com "technical support"`
- **Defensive action:** Route detailed diagnostics to protected internal monitoring.

### 7.3 Public error-page guidance
- **Purpose:** Find public documentation about error pages.
- **How it works:** Searches a public phrase.
- **Safe example:** `site:example.com "error page"`
- **Defensive action:** Use generic production responses and keep technical details in protected logs.

### 7.4 Public reliability documentation
- **Purpose:** Find published reliability information.
- **How it works:** Searches a public topic.
- **Safe example:** `site:example.com reliability`
- **Defensive action:** Publish service-level summaries, not raw traces or request data.

### 7.5 Public incident reports
- **Purpose:** Find incident reports deliberately published for transparency.
- **How it works:** Searches for a public report phrase.
- **Safe example:** `site:example.com "incident report"`
- **Defensive action:** Remove personal information, tokens and secrets from reports before publication.

---

# Priority 08 — Public Documents & Metadata Governance
**Original category:** Documents  
**Why this ranks eighth:** Documents can contain comments, hidden content, revision history and metadata beyond the visible text.

### 8.1 Public policy documents
- **Purpose:** Find published policy documents.
- **How it works:** Combines a site restriction with a public topic and file type.
- **Safe example:** `site:example.com filetype:pdf policy`
- **Defensive action:** Review content and metadata before publication.

### 8.2 Public research papers
- **Purpose:** Find research papers made available by an organisation.
- **How it works:** Uses a domain restriction and file-type filter.
- **Safe example:** `site:example.com filetype:pdf research`
- **Defensive action:** Check publication permissions, citations and included participant information.

### 8.3 Public blank forms
- **Purpose:** Find blank forms intended for public use.
- **How it works:** Searches for a public forms page.
- **Safe example:** `site:example.com forms`
- **Defensive action:** Publish blank templates only; keep completed submissions private.

### 8.4 Public dated publications
- **Purpose:** Find public pages within a date range.
- **How it works:** Combines `after:` and `before:` date filters.
- **Safe example:** `site:example.com after:2024-01-01 before:2025-01-01`
- **Defensive action:** Review old content and remove outdated information through the normal publishing process.

### 8.5 Document publishing guidance
- **Purpose:** Find the organisation's own document publishing instructions.
- **How it works:** Searches a public documentation phrase.
- **Safe example:** `site:example.com "document guidelines"`
- **Defensive action:** Inspect metadata, comments and hidden content locally before releasing documents.

---

# Priority 09 — Application Interfaces & Access-Control Boundaries
**Original category:** Interfaces  
**Why this ranks ninth:** Public-facing interfaces should be intentionally available; administrative functions must rely on authentication and authorisation.

### 9.1 Public sign-in help
- **Purpose:** Find user help about signing in.
- **How it works:** Searches public support content.
- **Safe example:** `site:example.com "sign in help"`
- **Defensive action:** Keep support documentation public but protect account functions with authentication.

### 9.2 Public account guidance
- **Purpose:** Find account-management help.
- **How it works:** Searches for a public help topic.
- **Safe example:** `site:example.com "account settings"`
- **Defensive action:** Ensure account data is available only to the authenticated account owner.

### 9.3 Public API documentation
- **Purpose:** Find documentation intended for developers.
- **How it works:** Searches for a public documentation phrase.
- **Safe example:** `site:example.com "API documentation"`
- **Defensive action:** Publish approved documentation only; enforce authentication, authorisation and rate limits on actual APIs.

### 9.4 Public support portal
- **Purpose:** Find official support and contact pages.
- **How it works:** Searches a public support topic.
- **Safe example:** `site:example.com support`
- **Defensive action:** Keep private support tickets and customer records behind access controls.

### 9.5 Public service descriptions
- **Purpose:** Find pages describing public services.
- **How it works:** Searches for a public service topic.
- **Safe example:** `site:example.com services`
- **Defensive action:** Separate public service descriptions from private operational interfaces.

---

# Priority 10 — Public Records, Privacy & Data Minimisation
**Original category:** Public records  
**Why this ranks tenth:** Public information still requires careful, lawful handling. Personal data should not be collected or compiled unnecessarily.

### 10.1 Official organisation contact page
- **Purpose:** Find an organisation's official contact page.
- **How it works:** Searches for a public contact page.
- **Safe example:** `site:example.com contact`
- **Defensive action:** Prefer role-based contact channels and avoid unnecessary personal details.

### 10.2 Public privacy policy
- **Purpose:** Find the organisation's published privacy policy.
- **How it works:** Searches for an exact public phrase.
- **Safe example:** `site:example.com "privacy policy"`
- **Defensive action:** Explain data collection, purpose, retention and available privacy rights.

### 10.3 Public terms of service
- **Purpose:** Find published service terms.
- **How it works:** Searches for an exact phrase.
- **Safe example:** `site:example.com "terms of service"`
- **Defensive action:** Keep legal and policy pages current and accessible.

### 10.4 Public transparency report
- **Purpose:** Find reports an organisation deliberately publishes.
- **How it works:** Searches for a public report title.
- **Safe example:** `site:example.com "transparency report"`
- **Defensive action:** Aggregate and anonymise information where appropriate.

### 10.5 Public accessibility statement
- **Purpose:** Find public accessibility commitments and support information.
- **How it works:** Searches for a public accessibility phrase.
- **Safe example:** `site:example.com accessibility`
- **Defensive action:** Publish accessible contact routes without disclosing private accommodation records.

---

## Site-owner remediation checklist

- [ ] Keep private files and backups outside the public document root.
- [ ] Require authentication and authorisation for private resources.
- [ ] Disable automatic directory indexing unless intentionally required.
- [ ] Keep logs and diagnostic output out of public paths.
- [ ] Disable verbose debug mode in production.
- [ ] Keep secrets out of public repositories and deployment artefacts.
- [ ] Review document metadata before publication.
- [ ] Review cloud-sharing permissions.
- [ ] Remember that `robots.txt` and `noindex` are not access controls.
- [ ] Secure or remove exposed source material before requesting search-index removal.
- [ ] Rotate credentials or keys if exposure is suspected.
- [ ] Recheck fixes using authorised administrative procedures.
