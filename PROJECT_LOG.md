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
- Commands/tests run + results: Targeted source smoke check passed for weather title/authors/DOI/PDF URL, Shocks or Shifts title/author/no-PDF decision, and removal of bottom duplicate suggested-citation lines from gas and weather pages.
- Follow-ups / TODOs: Update EconStor/RePEc/LEM metadata upstream so Scholar stops ranking the old title as the main version.

### 2026-07-08 19:00:54 +02:00
- What changed: Completed validation for the Google Scholar metadata update and recorded that local Jekyll tooling is unavailable on PATH.
- Why: The website source now gives Scholar explicit current metadata for Gas Prices and the Macroeconomy, but the rendered build could not be tested locally without Ruby/Bundler/Jekyll.
- Files touched: _publications/2024-Colombo-Toni.md, _includes/head.html, files/Colombo_Toni_2025_Gas_Prices_and_the_Macroeconomy.pdf, PROJECT_LOG.md.
- Commands/tests run + results: Select-String metadata source check passed; targeted PowerShell smoke check passed for front matter, title, authors, DOI, PDF link, head meta tags, and PDF existence; bundle exec jekyll build --trace failed because bundle is not recognized; where.exe ruby/bundle/jekyll found no executables.
- Follow-ups / TODOs: Run bundle exec jekyll build in an environment with Ruby/Bundler/Jekyll before publishing if you want full rendered-site validation; update EconStor/RePEc/LEM metadata upstream.

### 2026-07-08 19:06:30 +02:00
- What changed: Pushed the Google Scholar metadata update to GitHub Pages and verified the live page.
- Why: Confirmed the deployed HTML now exposes the corrected citation metadata for Scholar crawling.
- Files touched: PROJECT_LOG.md.
- Commands/tests run + results: git push origin master succeeded; live page returned HTTP 200; live HTML contains citation_title, citation_author, citation_publication_date, citation_doi, citation_pdf_url, and citation_abstract_html_url; live HTML contains the new PDF filename and no longer contains the old paper PDF filename.
- Follow-ups / TODOs: Update EconStor/RePEc/LEM records so Scholar search stops preferring the old title from external repositories.

### 2026-07-08 19:15:21 +02:00
- What changed: Added Google Scholar citation metadata for the weather paper and the Shocks or Shifts WIP page; removed bottom duplicate suggested-citation lines where top recommended citations are generated from front matter.
- Why: Keep Scholar-readable metadata consistent across visible research pages while avoiding duplicate visible citation text on publication pages.
- Files touched: _publications/2023-Colombo-Ferrara.md, _publications/2025-Colombo.md, _publications/2024-Colombo-Toni.md, PROJECT_LOG.md.
- Commands/tests run + results: Targeted source smoke check passed for weather title/authors/DOI/PDF URL, Shocks or Shifts title/author/no-PDF decision, and removal of bottom duplicate suggested-citation lines from gas and weather pages.
- Follow-ups / TODOs: Add citation_pdf_url for the Shocks or Shifts WIP page only after the public PDF title/content matches that title.

### 2026-07-08 19:20:49 +02:00
- What changed: Verified the deployed Scholar metadata updates for gas, weather, and Shocks or Shifts pages after GitHub Pages rebuilt.
- Why: Confirmed the live site, not only source files, reflects the citation metadata and duplicate citation cleanup.
- Files touched: PROJECT_LOG.md.
- Commands/tests run + results: git push origin master succeeded for commit 98852f4; raw GitHub source check confirmed weather metadata; YAML front matter parser check passed for all three publication pages; live pages returned HTTP 200; live gas/weather/WIP pages contain expected citation_title metadata; gas and weather no longer contain bottom Suggested citation text; WIP has no citation_pdf_url.
- Follow-ups / TODOs: Add a WIP citation_pdf_url only after the public draft PDF title/content is updated to Shocks or Shifts.
