# Atlas Quakes (archive to 17 August 2026)

**[Atlas Quakes](https://atlas.freedomcore.io/quakes/)** is the daily record of source-dated company and protocol developments from FreedomCore Atlas. Live editions are on the site, with a dated page for each day at `/quakes/YYYY-MM-DD/` since [2026-10-29](https://atlas.freedomcore.io/quakes/2026-10-29/).

This folder is the archive of earlier editions, which were published under the product's former name. It holds the edition generated on 20 July 2026 (`atlas-quakes-archive.json`, `schema.json`). The Hugging Face archive holds the later files, up to 17 August 2026.

- Live editions: [`/quakes/`](https://atlas.freedomcore.io/quakes/)
- Data catalog: [`/datasets/`](https://atlas.freedomcore.io/datasets/)
- Archive on Hugging Face: [`freedomcoreai/atlas-quakes-archive`](https://huggingface.co/datasets/freedomcoreai/atlas-quakes-archive)

## What changed on 10 November 2026

- The folder and its data file took the product's current name. Earlier states remain in this repository's history (commit `69ef1bae3c20`).
- 17 of the 20 item links pointed at company pages that no longer exist. Those links now point at the live Atlas Quakes page. The 3 working links (GE, UNH, ELV) are unchanged.
- `dataset_id` matches the new name, and `content_hash` was recomputed for the edited payload. The value published on 20 July is kept as `archive_maintenance.original_content_hash`.
- Nothing else in the edition was changed: tickers, names, dates, snippets, source counts and states are as published. Field names and schema identifiers are kept from the original file format.

Licence: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Attribute FreedomCore Atlas and link to [Atlas Quakes](https://atlas.freedomcore.io/quakes/).
