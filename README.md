# Utah Ballot Count Tracker — Tactical Data

Live ballot counting for Utah's 2026 general election, through canvass:
statewide total, all 29 counties, all 108 districts (4 CD / 29 SD / 75 HD),
the closest races with per-release history, and party registration vs vote
choice by congressional district.

Live at: https://data.tacticalcampaigns.com/utah-ballot-tracker/

## How it is built

This site is generated, not hand-edited. The generator is
`build_org_site.py` in the tracker's working directory; it reads the same
data the original tracker reads (state All-Results reports, county Ballot
Statistics estimates, district registration from the Tableau extract,
race-release history, Universal RRS) and regenerates the five HTML pages.
The hourly cron runs the generator and pushes the output here.

Dual publish: the original tracker at
joshadaniels.github.io/utah-election-dashboards keeps running from the same
pipeline; this repo is its Tactical Data twin.

## Data sources

- Utah Lieutenant Governor's election results (electionresults.utah.gov):
  state All-Results reports, county Ballot Statistics reports, county
  Summary Results PDFs.
- Ali Majid's November 2026 Dashboard (Tableau Public) for registration.
  No L2 data is used anywhere.
- District boundaries: Utah Geospatial Resource Center (AGRC) ArcGIS
  services — House/Senate 2022–2032, Congressional 2026–2032 (the 2025
  court-ordered map), county boundaries. GeoJSON sidecars in this repo.

All figures are unofficial until canvassed. This tracker is not affiliated
with the State of Utah or any county.
