# WRF Namelist Doctor

A single-file browser tool that finds the mistakes that crash WRF runs before you submit the job, and tells you how to fix them. Built with Claude.

**Why:** WRF fails late and cryptically. A bad nest size or time step costs a queue wait on an HPC cluster. This catches it in seconds, offline, with nothing uploaded.

## Features
- **Namelist checks** on `namelist.input`: nest rule `(e_we-1) % parent_grid_ratio`, nests outside or too near the parent edge, `time_step` vs 6x dx, dates, `e_vert` consistency, PBL/surface-layer pairing, cumulus scheme at convection-permitting grids.
- **One-click fixes**: apply a single fix or fix everything, then copy the corrected namelist.
- **To-scale nest map** that turns red when a nest leaves its parent.
- **Core-count guidance**: maximum and efficient MPI ranks for your smallest domain, step count and grid volume.
- **Crash log decoder**: paste `rsl.error.0000` and get the likely cause (CFL blow-up, segfault, missing `met_em`, namelist mismatch, patch too small, out of memory) and a fix.

## Use
Open `index.html` in a browser, or host it with GitHub Pages. No build step, no dependencies, no network calls apart from Google Fonts.

## Rules source
WRF User Guide recommendations; warnings are guidance, errors are likely crashes.

## Author
Divyanka Keshri, IIT Delhi. GitHub: https://github.com/keshridivyanka321-crypto
