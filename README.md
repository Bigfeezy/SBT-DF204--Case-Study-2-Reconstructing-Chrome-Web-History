# SBT-DF204--Case-Study-2-Reconstructing-Chrome-Web-History
Chrome History forensics case study: SQLite analysis of a Chrome History database to reconstruct browsing activity, timeline and evidence log, with documented acquisition and integrity checks.


# Chrome Web History Reconstruction (SBT-DF204 Case Study 2)

A digital forensics case study examining a Chrome `History` SQLite database
to reconstruct browsing activity, document the evidence chain, and assess
what the data can and cannot support.

## What this repo contains
- `queries/` – SQL queries used for analysis (visits, transitions, navigation chains, downloads)
- `report/` – the written report (acquisition, method, findings, timeline, attribution assessment)
- `screenshots/` – query output used as evidence

## Method summary
1. Original `History` file hashed (SHA-256), set read-only, and left untouched
2. Hash-verified working copy opened in read-only mode
3. WebKit timestamps converted to UTC (microseconds since 1601-01-01)
4. Visits joined to URLs; `transition` decoded into base type and qualifiers; `from_visit` used to follow navigation paths
5. Downloads linked to their URL chains
6. Findings kept separate from interpretation, with stated confidence and limitations

## Tools
SQLite / DB Browser for SQLite, SHA-256 hashing, [your OS and versions]

## Notes
The evidence file itself is not included in this repository.
