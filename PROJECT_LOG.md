# Project Log

## Repo Summary
- Personal academic website built with Jekyll/AcademicPages.
- Research pages live mainly under `_publications/`; shared HTML head metadata lives under `_includes/`.
- Static PDFs and data downloads are served from `files/`, while figures are served from `images/`.

## Entries

### 2026-07-08 18:59:07 +02:00
- What changed: Added Google Scholar citation metadata for Gas Prices and the Macroeconomy, updated the paper download link to a title-matching PDF filename, and copied the current PDF to that new filename.
- Why: Scholar public search was preferring older EconStor/RePEc metadata under the previous title; explicit citation_* tags give Scholar a stronger current metadata source.
- Files touched: _publications/2024-Colombo-Toni.md, _includes/head.html, files/Colombo_Toni_2025_Gas_Prices_and_the_Macroeconomy.pdf, PROJECT_LOG.md.
- Commands/tests run + results: Pending smoke checks after edit.
- Follow-ups / TODOs: Update EconStor/RePEc/LEM metadata upstream so Scholar stops ranking the old title as the main version.

### 2026-07-08 19:00:54 +02:00
- What changed: Completed validation for the Google Scholar metadata update and recorded that local Jekyll tooling is unavailable on PATH.
- Why: The website source now gives Scholar explicit current metadata for Gas Prices and the Macroeconomy, but the rendered build could not be tested locally without Ruby/Bundler/Jekyll.
- Files touched: _publications/2024-Colombo-Toni.md, _includes/head.html, files/Colombo_Toni_2025_Gas_Prices_and_the_Macroeconomy.pdf, PROJECT_LOG.md.
- Commands/tests run + results: Select-String metadata source check passed; targeted PowerShell smoke check passed for front matter, title, authors, DOI, PDF link, head meta tags, and PDF existence; bundle exec jekyll build --trace failed because bundle is not recognized; where.exe ruby/bundle/jekyll found no executables.
- Follow-ups / TODOs: Run bundle exec jekyll build in an environment with Ruby/Bundler/Jekyll before publishing if you want full rendered-site validation; update EconStor/RePEc/LEM metadata upstream.
