# QA and release notes

## Functional QA
All five pages passed user-executed KPI, slicer, interaction, and visual checks. Register validation reported 5,000 rows and 5,000 unique IDs. Overall: 5,000 orders = 4,673 completed + 327 outstanding; 327 outstanding = 280 overdue + 47 not overdue.

## Release review
User reported passing 20/20 checks spanning privacy, provenance, file integrity, and presentation. Dataset origin: synthetic. Final sharing method: Complete Portfolio Package (case study, screenshots, repository, and interactive demo if feasible).

## Remaining publishing actions
- [ ] Confirm repository contains only intended public files.
- [ ] Add PBIX only after checking embedded queries and source paths.
- [ ] Add dataset or generator only if permitted and verified.
- [ ] Verify README and case study match final screenshots and files.
- [ ] Decide whether to enable public Power BI sharing; verify license/tenant requirements and exposure implications.
- [ ] Test all links from a signed-out browser.

**Important:** QA and privacy reviews were reported by the project author; no independent record-by-record or PBIX binary audit is claimed.
