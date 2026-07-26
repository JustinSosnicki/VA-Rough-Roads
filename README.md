# VA Rough Roads

A route-planning tool for checking driving routes against Virginia's
Very Poor-condition and unpaved state roads.

**Live site:** `https://JustinSosnicki.github.io/VA-Rough-Roads` (fill in once published)

## What it does

- Shows Virginia's Very Poor-condition roads (colored by VDOT CCI score) and
  unpaved roads over a live map, pre-filtered to exclude dead-end /
  subdivision-only branches using network-connectivity analysis
- Import up to 3 GPX tracks (track data only — routes/waypoints are ignored)
  to compare candidate drives against the rough-road data
- Automatically flags stretches where a route overlaps a poor-condition or
  unpaved road, filtering out short/incidental overlaps
- Shows % of route on rough roads, length-weighted average CCI, and an
  unpaved-road warning per route, plus a side-by-side comparison when
  multiple routes are loaded
- Right-click (desktop) any point on the map to jump to Street View there
- Export a printable route map as a PNG — drawn from scratch (no basemap
  tile imagery), with the route, flagged stretches, a scale bar, and
  collision-avoiding road-name labels
- Works as a bottom sheet on mobile

## Running it locally

It's a single self-contained HTML file — just open `index.html` in a
browser. No build step, no server, no dependencies to install.

## Publishing / updating

This repo is set up to serve directly via GitHub Pages from the repo root.
To push an update, just replace `index.html` with a newer export of the app
and commit — Pages will redeploy automatically within a minute or two.

## Data sources & attribution

- Road condition and unpaved-roads data: VDOT Pavement Management System,
  2026 (via VDOT/VGIN open data)
- Map tiles: [CARTO](https://carto.com/attributions) / [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors
- Road name lookups: [OpenStreetMap Nominatim](https://nominatim.openstreetmap.org/)
- Street View links: Google Maps

## Notes on the data

Very Poor-condition and unpaved road segments are filtered to exclude
branches that only connect to the road network through a single dead-end
point (subdivisions, cul-de-sacs) using geometric intersection detection and
articulation-point analysis of the statewide route network — see commit
history / project notes for methodology if you're curious.
