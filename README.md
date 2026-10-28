# Meliora Subdivision Layout Generator

Single-file HTML tool. Takes a Queensland address or lot-on-plan, reads the DCDB, and generates every subdivision arrangement the site can take — checked against the planning scheme — as DXF, vector PDF, high-resolution PNG and JSON.

**Live:** https://mblyth88.github.io/subdivision-layout-generator/

Meliora Engineering · Brisbane

## What is in this repo

| file | |
|---|---|
| `index.html` | the tool, built as one self-contained file — no external scripts, stylesheets or fonts |
| `rules.json` | planning-scheme rule sets, **generated** by the `mce-planning-rules` skill. Do not edit by hand. |
| `CHANGELOG.md` | newest first, one block per build |

`rules.json` is fetched at load; the tool falls back to a copy built into `index.html` if it is missing, so the two must be regenerated together.

Runtime network calls go to the Queensland DCDB and the QLD aerial/LiDAR services only.
