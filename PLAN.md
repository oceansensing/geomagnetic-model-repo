# geomagnetic-model-repo: the founding plan and running record

The **Earth's magnetic field**, from the World Magnetic Models. Created on GitHub by the owner and given its documents by the site's
`pipeline/scaffold/new-origin.py`. **Nothing is published yet.**

## What it is for

The Earth's main magnetic field by NOAA NCEI and the British Geological Survey's World Magnetic Models, evaluated by the site's pipeline for the first instant of each month: **the field** (WMMHR2025, degree 133 — the core's field and the crust's larger features): declination, inclination, and the total, horizontal, vertical, north and east intensities, a 0.25° world each (`decl-wmmhr.json`, `incl-wmmhr.json`, `magf-`, `magh-`, `magz-`, `magx-`, `magy-wmmhr.json`); **its yearly change** (the same model's secular variation): each of the seven's (`decldot-wmmhr.json` … `magydot-wmmhr.json`); and **the compass's blackout and caution zones** (WMM2025, as NOAA defines them): where the horizontal field is under 2,000 nT (2) or 6,000 nT (1), at 0.5° (`magzone-wmm.json`). Each grid's `refTime` is the month's first instant and its `validTo` the next month's. Three products, R2's alone.

## Where the data comes from

NOAA's National Centers for Environmental Information with the British Geological Survey: **WMM2025** (released 2024-12-17, valid 2025.0 to 2030.0, DOI 10.25921/aqfd-sd83) and **WMMHR2025** (valid 2025.0 to 2030.0, DOI 10.25921/qb1c-vn52). **Their terms were read before a line was written** (2026-10-16): both are works of the US Government, free to use and republish, credited to NOAA NCEI and BGS. Their coefficients and NOAA's own test values are kept in the site (`scripts/data/geomag/`), the evaluation held to every test value, each element and its yearly change. No server is asked at run time; a new model release is a new coefficient file there.

## Open

1. The first dispatched run, read: the three products fresh, R2 alone.
2. Then the daily schedule.
3. The month's turn read: each grid's refTime moving to the new month, and nothing new published between turns.
4. WMM2025's successor (by 2030.0, or a mid-term release): its coefficients and test values into the site's `scripts/data/geomag/`.
