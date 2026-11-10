# EHDS Data Quality Readiness microsite

**Independent educational collection | Revised 10 November 2026**

A standalone static GitHub Pages site that responds to HIQA's two HealthData@IE Work Package 8 pilot reports released publicly on 9 November 2026. The microsite is independent of HIQA, the HSE, HealthData@IE and the European Commission.

## Included content

| File | Description |
| --- | --- |
| `index.html` | New landing page, relationship of resources, sources, status and regulatory context |
| `pages/ehds-readiness-for-data-holders.html` | Introductory guide, interactive timeline and self-check |
| `pages/immat-caf-dq-pilots-analysed.html` | Annotated comparative analysis and interactive IMMAT demonstration |
| `pages/dqul-readiness-specification.html` | Unofficial draft technical specification **v0.2**, criteria set **0.1**, with revised browser-based demonstrator |
| `vocabulary/label-readiness-v0.2.ttl` | Machine-readable **unofficial prototype** RDF vocabulary, designed for a stable hosted URL |
| `reports/hiqa-immat-pilot-report.pdf` | Official HIQA pilot report, Deliverable 8.2, unchanged |
| `reports/hiqa-caf-dq-pilot-report.pdf` | Official HIQA pilot report, Deliverable 8.9, unchanged |
| `pages/nhdsc-specification-v0-3.html` | Historical note about an unavailable companion proposal, **not** a substitute specification |
| `assets/` | Report thumbnails and minimal typographic favicon |

## Deploy on GitHub Pages

1. Create a public repository, for example `ehds-data-quality-readiness`.
2. Upload **the contents** of this folder, not the parent folder, to the repository root. Include `.nojekyll`, `index.html`, `pages/`, `reports/`, `vocabulary/` and `assets/`.
3. In **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, then `main` and `/ (root)`.
4. Open the published URL, normally `https://<owner>.github.io/<repository>/`, and test all three HTML resources, both PDFs and the draft export controls.

The site does not need a build pipeline or backend. All internal page links are relative. The optional external font and W3C resources may require network access.

## Status and regulatory boundary

Two different EHDS instruments should not be confused:

- **Dataset description metadata:** Commission Implementing Regulation (EU) **2026/2098**, adopted 18 September and published 21 September 2026, establishes minimum HealthDCAT-AP-based metadata elements under EHDS Article 77(4). It applies from **26 March 2029**. Official text: https://eur-lex.europa.eu/eli/reg_impl/2026/2098/oj
- **Data Quality and Utility Label:** The implementing acts specifying the label under **Article 78(6)** are expected by **26 March 2027**. The site's independent readiness criteria are proposals and must be reconsidered against the adopted label specifications.

The **IMMAT** is HIQA's high-level information management maturity self-assessment. The **CAF-DQ** concerns HIQA's targeted data-quality assessment approach. The third resource explores an **additional independent architecture for traceable evidence**, rather than replacing either instrument.

**An “Evidence available” result means a process and a release-specific measurement are documented, not that the dataset is good, fit for a purpose or compliant.** The EHDS quality label is attached to a dataset; the more granular release-level evidence record is a design proposal of this microsite, not a legal requirement.

## Demonstrator changes in v0.2

- Renamed positive state from `Ready` to **`Evidence available`** throughout documentation, UI and RDF vocabulary.
- Added draft CSV and Turtle exports that work with incomplete assessments. The exported rows/triples explicitly indicate **draft-unattested** status and include validation issue counts.
- Added a separate **Validate draft** action. This lists unmet proposed requirements but performs no attestation, approval, data-quality grading or regulatory compliance determination.
- E3 requires fields for the retained measurement **method** and **inputs**, as well as the evidence item.
- Completeness (`LR-04`) and consistency (`LR-09`) require a declared variable scope, using `All variables` or `Subset: <identifier>`.
- Marking a criterion not applicable now prompts for a **reviewer name/role and date**, but these are self-entered and not authenticated.
- Added a versioned, bundled draft RDF vocabulary. When hosted, export refers to the deployed `vocabulary/label-readiness-v0.2.ttl#` URI. Keep its published URL stable: **moving or renaming the repository without redirects breaks existing RDF references**. Local file previews fall back to an explicitly provisional `example.org` namespace.
- Made the proposal's definitions of dataset and release self-contained; the missing National Health Dataset Catalogue companion specification is no longer needed to interpret the technical proposal.

The revised demonstrator remains a **prototype**. It does not implement an authenticated approval workflow, signed attestation, immutable versioning, multi-assessor attribution, actual evidence-file inspection, production-grade identity management, security review or formal accessibility certification. **Validation and draft export are not finalisation.** Do not make compliance or quality claims from its output. Work in progress may be stored in browser local storage. Avoid entering real patient data or confidential operational information.

## Maintenance and further development

Keep the deployed vocabulary URL stable, update dates when label implementing acts are adopted, review dependencies on the official HealthDCAT-AP release, and obtain expert assessment of any proposed mapping before production reuse. The two HIQA PDFs are original, unchanged source documents; verify redistribution conditions and replace them with official HIQA links if necessary.

## Source publications

- HIQA announcement (9 November 2026): https://www.hiqa.ie/hiqa-news-updates/hiqa-publishes-reports-tools-developed-support-health-data-holders-ireland
- Regulation (EU) 2025/327: https://eur-lex.europa.eu/eli/reg/2025/327/oj
- Commission Implementing Regulation (EU) 2026/2098: https://eur-lex.europa.eu/eli/reg_impl/2026/2098/oj
- HealthDCAT-AP: https://data.health.europa.eu/healthdcat-ap/releases/latest/
- HIQA National Standards for Information Management (2024): https://www.hiqa.ie/sites/default/files/2024-06/National-Standards-for-Information-Management-2024.pdf
