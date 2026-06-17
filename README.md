# FreedomCore Open Datasets

Open, source-backed market-research datasets published by **ATLAS by FreedomCore**.

Live product: **https://atlas.freedomcore.io**

ATLAS is a multi-model AI market research desk covering 200+ symbols across equities, crypto, commodities, forex, indices and ETFs, where every symbol gets a daily, source-cited research brief. The files in this repository are open snapshots of that coverage, refreshed regularly and mirrored to multiple public catalogs.

## Datasets

### atlas-symbol-coverage
A daily research-brief coverage index across 200+ financial symbols. One row per indexable Atlas symbol page, shipped in CSV and JSON with identical content. Columns include `symbol`, `url`, `asset_class`, `sitemap_lastmod`, `context_as_of`, `source_count` and more.

Files: `atlas-symbol-coverage/atlas-symbol-coverage.csv`, `atlas-symbol-coverage/atlas-symbol-coverage.json`, `atlas-symbol-coverage/schema.json`
Mirrors: HuggingFace https://huggingface.co/datasets/freedomcoreai/atlas-symbol-coverage and Kaggle https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-symbol-coverage

### atlas-market-pulse
A dated cross-asset daily market snapshot in a single JSON file: equities, crypto, commodities, forex, indices and ETFs in one consistent shape, with a top-level `pulse` summary and a per-asset `items[]` array.

Files: `atlas-market-pulse/atlas-market-pulse.json`, `atlas-market-pulse/schema.json`
Mirrors: HuggingFace https://huggingface.co/datasets/freedomcoreai/atlas-market-pulse and Kaggle https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-market-pulse

### atlas-security-posture
A small, citable JSON record of the Atlas public security posture: plain-language controls, public evidence links, and an explicit claims boundary you can re-test yourself.

Files: `atlas-security-posture/atlas-security-posture.json`, `atlas-security-posture/schema.json`
Mirrors: HuggingFace https://huggingface.co/datasets/freedomcoreai/atlas-security-posture and Kaggle https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-security-posture

Each dataset carries a `generated_at` timestamp and a content hash, so you can tell snapshots apart and verify integrity. Full column explainers and example uses live on the catalog mirrors above and on the source pages at https://atlas.freedomcore.io/datasets/

## Provenance

All datasets are published by ATLAS by FreedomCore and derived live from https://atlas.freedomcore.io. Each row or record maps to a real, indexable page on the site. This is research metadata. It is not financial advice, not signals, and not brokerage execution.

## Licence

Released under **CC BY 4.0**. Free to reuse, including commercially, provided you give attribution to ATLAS by FreedomCore and link back to https://atlas.freedomcore.io. See [LICENSE](LICENSE).

## Links

- Product: https://atlas.freedomcore.io
- Datasets on Atlas: https://atlas.freedomcore.io/datasets/
- Security posture and proof: https://atlas.freedomcore.io/pages/atlas-security.html
- Contact: freedomcoreai@gmail.com
