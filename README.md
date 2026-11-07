# pilot_website

A preview copy of the ProofBench website (https://lp-bench.github.io) for sharing the
project with students. It lists the problems by number, category and area only.

Plain HTML, CSS and JavaScript; no build step. Open `index.html` locally to preview.
Publishing runs through GitHub Actions (`.github/workflows/site.yml`; Settings -> Pages ->
Source: GitHub Actions). The workflow only publishes; it never pulls the problem list
from the statements repository.

* `assets/js/problem-data.js`: the official problem list, without the `name`, `summary` and
  `lean` fields and without notes that may cite a source. Nothing updates it automatically: when
  the statements repository changes, run `python scripts/build_problems.py
  path/to/proofbench/ProofBench/DATABASE/Database.json`.
* `scripts/build_problems.py`: the main site's generator, changed so that it never exports
  those fields, and only the notes in `SAFE_NOTES`.
