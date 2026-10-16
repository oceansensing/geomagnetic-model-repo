# geomagnetic-model-repo

The **Earth's magnetic field**, from the World Magnetic Models: a data repository of the oceansensing ocean map system, with its own
Pages site, its own schedule and its own gigabyte, and no code of its own.

**Nothing is published yet.** `PLAN.md` is the founding plan; `CLAUDE.md` carries what must not be
got wrong and the shared doc doctrine.

## What it publishes

The Earth's main magnetic field by NOAA NCEI and the British Geological Survey's World Magnetic Models, evaluated by the site's pipeline for the first instant of each month: **the field** (WMMHR2025, degree 133 — the core's field and the crust's larger features): declination, inclination, and the total, horizontal, vertical, north and east intensities, a 0.25° world each (`decl-wmmhr.json`, `incl-wmmhr.json`, `magf-`, `magh-`, `magz-`, `magx-`, `magy-wmmhr.json`); **its yearly change** (the same model's secular variation): each of the seven's (`decldot-wmmhr.json` … `magydot-wmmhr.json`); and **the compass's blackout and caution zones** (WMM2025, as NOAA defines them): where the horizontal field is under 2,000 nT (2) or 6,000 nT (1), at 0.5° (`magzone-wmm.json`). Each grid's `refTime` is the month's first instant and its `validTo` the next month's. Three products, R2's alone.

These products are published **operationally but not drawn on the website's map**; the map's status
line still reports them when they fall behind, which is how their health stays visible.

## Where the data comes from

NOAA's National Centers for Environmental Information with the British Geological Survey: **WMM2025** (released 2024-12-17, valid 2025.0 to 2030.0, DOI 10.25921/aqfd-sd83) and **WMMHR2025** (valid 2025.0 to 2030.0, DOI 10.25921/qb1c-vn52). **Their terms were read before a line was written** (2026-10-16): both are works of the US Government, free to use and republish, credited to NOAA NCEI and BGS. Their coefficients and NOAA's own test values are kept in the site (`scripts/data/geomag/`), the evaluation held to every test value, each element and its yearly change. No server is asked at run time; a new model release is a new coefficient file there.

## How it runs

The orchestrator (the site's private `pipeline/`), the fetchers and the
published-file contract all come from `oceansensing.github.io`, checked out at
run time. This repository carries `pipeline/products.toml` and its publish
workflow, and nothing else executable. Each run publishes to GitHub Pages and
to Cloudflare R2 from one build. Related repositories: none it depends on.

**Which document gets what, and what "update docs" means across all
twenty-seven repositories, is the doctrine block at the top of `CLAUDE.md`**: the
same text in all twenty-seven, held equal by the site's `check:docs`.

## Structure

```
README.md       what this is
CLAUDE.md       what must not be got wrong, and the shared doc doctrine
PLAN.md         the founding plan and running record
DECISIONS.md    dated one-way decisions, D1 onward
pipeline/       products.toml, the declaration the orchestrator reads
.github/        the publish workflow
```
