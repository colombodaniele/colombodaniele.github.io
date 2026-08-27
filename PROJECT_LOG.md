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

### 2026-08-21 11:18:16 +02:00
- What changed: Updated the Gas Prices and the Macroeconomy website abstract to match the current PDF.
- Why: Keep the Research page aligned with the August 1, 2026 paper draft.
- Files touched: _publications/2024-Colombo-Toni.md, PROJECT_LOG.md.
- Commands/tests run + results: Python/pypdf comparison passed after normalizing PDF ligatures and line-break hyphenation; the website abstract matches the PDF abstract.
- Follow-ups / TODOs: Add the requested Orthogonalizing Shocks draft-coming-soon research entry after confirming its exact title and citation details.

### 2026-08-21 11:40:20 +02:00
- What changed: Added the Orthogonalizing Proxy-Identified Shocks work-in-progress entry; replaced the legacy Gas Prices PDF with the current version; changed the Gas Prices download and citation metadata to the established legacy PDF URL.
- Why: Display the new preliminary project while preserving a stable, widely shared paper URL that now serves the current 112-page version.
- Files touched: _publications/2026-Colombo-Ragusa.md, _publications/2024-Colombo-Toni.md, files/COLOMBO_TONI_2024_Gas_Price_Shocks_and_the_Inflation_Surge.pdf, PROJECT_LOG.md.
- Commands/tests run + results: SHA-256 comparison passed for legacy and current PDF copies; source check passed for both uses of the stable URL and the WIP entry title/status/text; git diff --check passed with only existing line-ending warnings.
- Follow-ups / TODOs: Keep the legacy Gas Prices filename in place for future revisions; replace its contents whenever a newer version should become the public default.

### 2026-08-21 12:03:08 +02:00
- What changed: Updated the Shocks or Shifts website abstract from the latest `MAIN_normalization.tex` manuscript source; retained the existing title.
- Why: Keep the Work in Progress page aligned with the current Overleaf draft's framing of observed shifts, latent shocks, normalization, and inference.
- Files touched: _publications/2025-Colombo.md, PROJECT_LOG.md.
- Commands/tests run + results: Python comparison passed after normalizing LaTeX en-dash punctuation and whitespace; git diff --check passed with only existing line-ending warnings.
- Follow-ups / TODOs: Commit and push this abstract update when ready.

### 2026-08-21 12:49:06 +02:00
- What changed: Rebuilt the Research page as a dedicated, compact paper-card list with distinct Working Papers and Work in Progress sections; added status badges, abstract previews, and available Paper/SSRN/Slides/Details actions; standardized research-card metadata without changing the Gas Prices entry's visible 2024 year.
- Why: Replace the visually uneven generic archive layout with a clearer research-specific hierarchy while preserving the generic archive template for other site sections.
- Files touched: _pages/publications.md, _includes/research-card.html, _sass/_research.scss, assets/css/main.scss, _publications/2023-Colombo-Ferrara.md, _publications/2024-Colombo-Toni.md, _publications/2025-Colombo.md, _publications/2026-Colombo-Ragusa.md, PROJECT_LOG.md.
- Commands/tests run + results: PowerShell static checks passed for card fields, stable Gas Prices year, action conditions, stylesheet import, and valid theme variables; git diff --check passed with existing line-ending warnings only. Ruby/Bundler/Jekyll are not installed on PATH, so a rendered local build was not available.
- Follow-ups / TODOs: Commit and push the Research redesign, then visually check the deployed `/papers/` page on desktop and mobile. If reverted after commit, `git revert <commit>` restores the former generic archive layout in one step.

### 2026-08-21 13:08:56 +02:00
- What changed: Removed the Research-page introduction and repeated Working Paper badges; made truncated abstract previews expandable through a native ellipsis control and collapsible with Show less.
- Why: Reduce repeated visual labels and let visitors read full abstracts on the Research page without leaving it or loading JavaScript.
- Files touched: _pages/publications.md, _includes/research-card.html, _sass/_research.scss, PROJECT_LOG.md.
- Commands/tests run + results: PowerShell checks passed for removal of the requested text and badge fallback, preservation of WIP labels, and presence of the native expandable-control markup/styles; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push this follow-up, then visually test ellipsis expansion and collapse on the deployed page.

### 2026-08-21 13:52:02 +02:00
- What changed: Added a Home-page-only layout flag and stylesheet that hide the redundant visible Home heading, enlarge the existing introduction, and render the unchanged Updates entries as a responsive date-aligned timeline.
- Why: Improve landing-page hierarchy and scanability without rewriting its content or changing the shared layout for other pages.
- Files touched: _pages/about.md, _layouts/single.html, _sass/_home.scss, assets/css/main.scss, PROJECT_LOG.md.
- Commands/tests run + results: PowerShell structural checks passed for Home layout flags, scoped title hiding, timeline selectors, mobile styles, and stylesheet import; git diff --check passed with existing line-ending warnings only. Ruby/Bundler/Jekyll remain unavailable on PATH, so no rendered local build was possible.
- Follow-ups / TODOs: Commit and push the Home-page visual update, then inspect the deployed Home page at desktop and mobile widths.

### 2026-08-27 19:41:36 +02:00
- What changed: Updated the Home-page About me line from fourth-year to fifth-year Ph.D. student.
- Why: Keep the academic status current.
- Files touched: _pages/about.md, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell source check passed; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push the status update when ready.

### 2026-08-27 19:45:58 +02:00
- What changed: Replaced the Home-page research-focus sentence with a concise macroeconometrics statement that names energy, climate, and production networks as application areas.
- Why: Better reflect the current methodological focus and research portfolio.
- Files touched: _pages/about.md, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell source check passed; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push the wording update when ready.

### 2026-08-27 19:59:54 +02:00
- What changed: Added a Poster action to the Gas Prices research card using the existing poster PDF.
- Why: Make the poster as directly accessible from the Research page as the slides.
- Files touched: _publications/2024-Colombo-Toni.md, _includes/research-card.html, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell check passed for the Gas Prices poster URL, conditional card action, and local poster PDF existence; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push the Research-card poster action when ready.

### 2026-08-27 20:04:32 +02:00
- What changed: Fixed expandable Research-card abstracts to use only the rendered first abstract paragraph and reveal only the text after the preview, rather than repeating the beginning and including page-level download links.
- Why: The previous expansion duplicated the preview and exposed concatenated page action labels.
- Files touched: _includes/research-card.html, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell check passed for first-paragraph extraction, 42-word preview segmentation, remaining-text expansion, and absence of the old duplicated-full-abstract markup; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push the abstract-expansion fix, then visually test an ellipsis on the deployed Research page.

### 2026-08-27 20:24:35 +02:00
- What changed: Reworked the Research-card abstract control so its closed state shows a preview plus ellipsis, while its open state replaces that preview with the complete abstract and places Show less after it.
- Why: Avoid the visually disconnected remainder fragment shown above Show less in the prior expansion design.
- Files touched: _includes/research-card.html, _sass/_research.scss, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell structural check passed for the complete-abstract markup and open-state flex ordering; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push this interaction refinement, then visually test its collapsed and expanded states on the deployed Research page.

### 2026-08-27 20:32:28 +02:00
- What changed: Added one shared research-detail header for all four paper pages, with compact status/citation blocks and resource buttons; moved each page's existing download links into structured metadata and removed the run-on inline links.
- Why: Give every paper page the same clean format while retaining all paper, SSRN, slides, poster, data, and figure resources.
- Files touched: _layouts/single.html, _includes/research-detail-header.html, _sass/_research.scss, _publications/2023-Colombo-Ferrara.md, _publications/2024-Colombo-Toni.md, _publications/2025-Colombo.md, _publications/2026-Colombo-Ragusa.md, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell validation passed for all four shared detail flags, structured resources, absence of inline download links, layout wiring, styles, and all referenced local files; git diff --check passed with no whitespace errors. Ruby/Bundler/Jekyll remain unavailable on PATH, so no rendered local build was possible.
- Follow-ups / TODOs: Commit and push the shared detail-page redesign, then visually inspect each deployed paper page.

### 2026-08-27 20:42:06 +02:00
- What changed: Refined the expandable abstract control so preview text uses the normal body colour, only the ellipsis and Show less controls use the link colour, and the expanded control does not stretch across the card.
- Why: Match the normal abstract typography and remove the distracting full-row focus/control appearance in the expanded state.
- Files touched: _sass/_research.scss, PROJECT_LOG.md.
- Commands/tests run + results: Targeted PowerShell stylesheet check passed for body-coloured preview text, link-coloured controls, and non-stretching open-state alignment; git diff --check passed with existing line-ending warnings only.
- Follow-ups / TODOs: Commit and push the abstract-control styling refinement, then visually check the closed and open states on the deployed Research page.

### 2026-08-27 20:49:27 +02:00
- What changed: Strengthened the abstract-preview CSS cascade so theme styles cannot make the collapsed summary blue or bold; the ellipsis and Show less remain blue and bold.
- Why: The deployed card still inherited a broader disclosure-control style despite the prior scoped rule.
- Files touched: _sass/_research.scss, PROJECT_LOG.md.
- Commands/tests run + results: Targeted stylesheet smoke check confirmed the normal body-text and interactive-control declarations; git diff --check passed. `bundle exec jekyll build` could not run because Bundler is not installed on PATH.
- Follow-ups / TODOs: Commit and push, then hard-refresh the deployed Research page and verify the preview is regular dark text.

### 2026-08-27 21:41:10 +02:00
- What changed: Removed the right-aligned status badges from Research-page cards, together with their unused layout and responsive styles.
- Why: The section heading and the text in each unfinished paper card already convey the paper status without the redundant labels.
- Files touched: _includes/research-card.html, _sass/_research.scss, PROJECT_LOG.md.
- Commands/tests run + results: Targeted template/stylesheet check confirmed that Research-card status badge markup and styles are absent; git diff --check passed with line-ending warnings only.
- Follow-ups / TODOs: Commit and push, then visually confirm the two work-in-progress cards have no right-side badges.

### 2026-08-27 21:42:48 +02:00
- What changed: Added research-specific Previous/Next navigation for detail pages and enabled it only for pages marked `research_detail`.
- Why: The generic theme navigation follows Jekyll's collection order, which differs from the order displayed on the Research page.
- Files touched: _includes/research-pagination.html, _layouts/single.html, PROJECT_LOG.md.
- Commands/tests run + results: Targeted ordering check passed for Gas Prices, Weather Shocks, Orthogonalizing Shocks, then Shocks or Shifts; layout wiring check and git diff --check passed.
- Follow-ups / TODOs: Commit and push, then open each paper detail page to verify Previous/Next follows the Research-page order.
