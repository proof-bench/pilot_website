# pilot_website

A preview copy of the ProofBench website (https://proof-bench.github.io) for sharing the
project with students. It lists the problems by number, category and area only.

Plain HTML, CSS and JavaScript; no build step. Open `index.html` locally to preview.
Publishing runs through GitHub Actions (`.github/workflows/site.yml`; Settings -> Pages ->
Source: GitHub Actions). The workflow only publishes; it never pulls the problem list
from the statements repository.

* `assets/js/problem-data.js`: problem list copied from the main site, without the `name`,
  `summary` and `lean` fields.
* `scripts/build_problems.py`: the main site's generator, changed so that it never exports
  those fields if it is ever run here.
