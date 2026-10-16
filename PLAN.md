# geomagnetic-model-repo: the founding plan and running record

The **Earth's magnetic field**, from the World Magnetic Models. Created on GitHub by the owner and given its documents by the site's
`pipeline/scaffold/new-origin.py`. **Publishing since 2026-10-16**, daily at 06:17 UTC.

## What it is for

The Earth's main magnetic field by NOAA NCEI and the British Geological Survey's World Magnetic Models, evaluated by the site's pipeline for the first instant of each month: **the field** (WMMHR2025, degree 133 — the core's field and the crust's larger features): declination, inclination, and the total, horizontal, vertical, north and east intensities, a 0.25° world each (`decl-wmmhr.json`, `incl-wmmhr.json`, `magf-`, `magh-`, `magz-`, `magx-`, `magy-wmmhr.json`); **its yearly change** (the same model's secular variation): each of the seven's (`decldot-wmmhr.json` … `magydot-wmmhr.json`); and **the compass's blackout and caution zones** (WMM2025, as NOAA defines them): where the horizontal field is under 2,000 nT (2) or 6,000 nT (1), at 0.5° (`magzone-wmm.json`). Each grid is the field at the month's first instant: its `refTime`, with no span (the values are no mean), the model named as its `stream`. Three products, R2's alone.

## Where the data comes from

NOAA's National Centers for Environmental Information with the British Geological Survey: **WMM2025** (released 2024-12-17, valid 2025.0 to 2030.0, DOI 10.25921/aqfd-sd83) and **WMMHR2025** (valid 2025.0 to 2030.0, DOI 10.25921/qb1c-vn52). **Their terms were read before a line was written** (2026-10-16): both are works of the US Government, free to use and republish, credited to NOAA NCEI and BGS. Their coefficients and NOAA's own test values are kept in the site (`scripts/data/geomag/`), the evaluation held to every test value, each element and its yearly change. No server is asked at run time; a new model release is a new coefficient file there.

## 2026-10-16: the first run, and the schedule

The dispatched run 38926496364 (15:45–15:47 UTC) was green: the three products fresh, fifteen grids for
2026-10-01T00:00:00Z — the field's seven and their yearly change about 6 MB each, the compass zones 1.2 — every
one matching the contract, the weakest field 21,989 nT over South America; R2 equal to the build (23 files),
Pages carrying the status alone. The schedule, daily at 06:17 UTC, in the same commit as this entry.

## Open

1. The month's turn read: each grid's refTime moving to the new month, and nothing new published between turns.
2. WMM2025's successor (by 2030.0, or a mid-term release): its coefficients and test values into the site's `scripts/data/geomag/`.
