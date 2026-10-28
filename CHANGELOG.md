# Changelog

## v1.1 – 28 Oct 2026

First build with a version stamp. Everything before this shipped as an unstamped "v1" — about thirty changes under one label, which is why the stamp now exists. It shows in the page header (`v1.1 · 28 Oct 2026`) and in every option JSON under `generator`.

- Version stamp in the header and the JSON.
- First build published to GitHub Pages.

## Before the stamp

Reconstructed from the project record. Dates are when the change was made.

### 23 Oct 2026

- **`rules.json` is now generated** by the `mce-planning-rules` skill instead of being maintained by hand. Two new councils came with it: **Moreton Bay** and **Sunshine Coast**, both marked unverified until someone checks them against the current scheme.
- **Moreton Bay's rear-lot cap** — Council allows only one rear lot behind a frontage lot, so tandem and two-front-one-rear arrangements are flagged there. Silent on schemes that set no cap.
- **Logan's three frontage minimums** — 12.5 m standard, 10 m on a cul-de-sac head, 15 m on a corner, instead of one flat number. A Logan corner lot between 12.5 m and 15 m used to pass when it should fail.
- **Brisbane slope** — Subdivision code AO2.2 and AO2.3 now tested against the LiDAR the tool has always read. A small lot on a steep fall used to pass every check.

### 3 Oct 2026

- **Address matching rewritten.** "19 Rice Rd" ran as "19 Price Close" — a SQL `LIKE` matched RICE inside PRICE and the scorer tied. Words now match whole, the street type is a ranking signal, and an unclear match **halts** with the candidates listed rather than guessing.
- **Maximum yield** — removes the 10-lot cap for workshopping larger sites.
- **Amalgamation** — "152-156 Cedar Rd" or two addresses joined with `+` are read as one site. Two 3,800 m² lots will carry an internal road neither carries alone.

### 2 Oct 2026

- **Future internal road** — a centreline entered on a form, run through to the far boundary or closed with a cul-de-sac bulb, with lots laid out either side. Sets `extra.new_road` true, which flips shared detention in the CER.
- **Access easements are no longer deducted from lot area.** An easement is a right over another allotment, not a reduction of it — accepted by Brisbane City Council in an RFI. Arrangements that were being wrongly rejected now pass.
- **Uncovered councils halt the run.** The lookup used to fall through to Brisbane for any LGA it did not carry, so a Moreton Bay site came back assessed against the Brisbane scheme with nothing on the sheet to say so.
- Forced front-lot area, and an explicit easement / access handle choice.

### 30 Sep 2026

- **Per-lot driveway and crossover position**, so kerb outlets can be placed clear of the crossing.

### Late Sep 2026

- Corner-lot handling: multiple frontages, chain frontage measurement, corner-split and parallel-split arrangements.
- Building-envelope floor — an arrangement no house fits on is not offered.
- Meliora-only lock on the JSON and DXF outputs.
- Options summary sheet, partner logo, planning-scheme rules summary.
