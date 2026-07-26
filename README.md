# VA Rough Roads

A route-planning tool for checking driving routes against Virginia's
Very Poor-condition and unpaved state roads.

**Live site:** `https://JustinSosnicki.github.io/VA-Rough-Roads`

## What it does

- Shows Virginia's Very Poor-condition roads (colored by VDOT CCI score) and
  unpaved roads over a live map
- Import up to 3 GPX tracks to compare candidate drives against the rough-road data
- Automatically flags stretches where a route overlaps a poor-condition or
  unpaved road
- Shows % of route on rough roads, length-weighted average CCI, and an
  unpaved-road warning per route, plus a side-by-side comparison when
  multiple routes are loaded
- Right-click (desktop) any point on the map to jump to Street View there
- Export a printable route map as a PNG

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
