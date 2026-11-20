---
language:
- en
license: cc-by-4.0
source_datasets:
- original
pretty_name: FreedomCore Atlas — Global Cross-Exchange Ticker Collisions v1 (355 groups, 781 listings)
size_categories:
- n<1K
task_categories:
- tabular-classification
- feature-extraction
- text-retrieval
tags:
- finance
- entity-resolution
- market-data
- stocks
- crypto
- ticker-disambiguation
- security-master
configs:
- config_name: default
  data_files:
  - split: train
    path: atlas-global-ticker-collisions.csv
---

# FreedomCore Atlas — Global Cross-Exchange Ticker Collisions (`v1`, 2026-11-20)

Joining global financial datasets on bare ticker strings silently corrupts entity resolution: the same ticker string (`SOL`, `BBY`, `AEM`, `1810`, `7203`, `ARB`, `LDO`) routinely identifies completely unrelated companies and crypto assets across different exchanges and countries.

This dataset extracts every colliding bare-ticker group from **[FreedomCore Atlas Symbol Coverage v4](https://atlas.freedomcore.io/datasets/atlas-symbol-coverage/)** (`6,735` listings: `5,215` equities across `59` exchanges in `53` countries, `1,500` crypto assets, `20` benchmarks across `69` unique venues).

## Key numbers (2026-11-20)

| Metric | Count |
| :-- | --: |
| Total colliding bare-ticker groups (full universe) | **355** |
| Distinct listings in colliding groups (full universe) | **781** |
| Colliding groups across equities + crypto | **353** (`776` listings) |
| Equity-only collision groups | 171 |
| Cross-asset equity + crypto collision groups | 150 |
| Max distinct instruments sharing one bare ticker | 5 |
| Live verified HTTP 200 canonical `profile_url` links | **781 / 781 (100%)** |

Source register SHA-256: `444e64893ca87a9af42d703afe1dc8e942e77d8c984727099f5d4ee0516b6a77` · Collision CSV SHA-256: `fe78c15b85e1679aa9111361a335282d4f5fecf2e484cd7d1ab78f517041baef`.

## Selected collision examples

| Bare ticker | Canonical `listing_key` | Instrument | Class | Country | Canonical Atlas page |
| :-- | :-- | :-- | :-- | :-- | :-- |
| `SOL` | `CRYPTO:SOL` / `ASX:SOL` / `BME:SOL` / `JSE:SOL` / `MIL:SOL` | Solana + 4 listed companies (AU, ES, ZA, IT) | crypto & equity | GL, AU, ES, ZA, IT | [`/stocks/SOL/`](https://atlas.freedomcore.io/stocks/SOL/) · [`/stocks/asx-sol/`](https://atlas.freedomcore.io/stocks/asx-sol/) · [`/stocks/jse-sol/`](https://atlas.freedomcore.io/stocks/jse-sol/) |
| `7203` | `TSE:7203` / `TADAWUL:7203` | Toyota Motor vs Elm Company | equity | JP, SA | [`/stocks/7203/`](https://atlas.freedomcore.io/stocks/7203/) · [`/stocks/tadawul-7203/`](https://atlas.freedomcore.io/stocks/tadawul-7203/) |
| `1810` | `HKEX:1810` / `TADAWUL:1810` | Xiaomi Corp vs Seera Holding Group | equity | HK, SA | [`/stocks/hkex-1810/`](https://atlas.freedomcore.io/stocks/hkex-1810/) · [`/stocks/tadawul-1810/`](https://atlas.freedomcore.io/stocks/tadawul-1810/) |
| `LDO` | `COINGECKO:lido-dao` / `MIL:LDO` | Lido DAO vs Leonardo S.p.A. | crypto & equity | GL, IT | [`/stocks/cg-lido-dao/`](https://atlas.freedomcore.io/stocks/cg-lido-dao/) · [`/stocks/mil-ldo/`](https://atlas.freedomcore.io/stocks/mil-ldo/) |

## Quickstart (Python)

```python
import pandas as pd

df = pd.read_csv(
    "https://huggingface.co/datasets/freedomcoreai/atlas-global-ticker-collisions/resolve/main/atlas-global-ticker-collisions.csv",
    dtype={"sec_cik": str},
)
print(df.groupby("bare_ticker")["listing_key"].nunique().sort_values(ascending=False).head(10))
```

## Canonical links & mirrors

- **Atlas site:** [https://atlas.freedomcore.io/](https://atlas.freedomcore.io/)
- **Open data catalog:** [https://atlas.freedomcore.io/datasets/](https://atlas.freedomcore.io/datasets/)
- **Full 6,735-listing register:** [freedomcoreai/atlas-symbol-coverage](https://huggingface.co/datasets/freedomcoreai/atlas-symbol-coverage)
- **GitHub mirror:** [freedomcore-datasets/atlas-global-ticker-collisions](https://github.com/freedomcoreai-lang/freedomcore-datasets/tree/main/atlas-global-ticker-collisions)
- **Kaggle mirror:** [atlasfreedomcoreio/atlas-global-ticker-collisions](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-global-ticker-collisions)

## Licence & citation

Released under **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)**. Attribute **FreedomCore Atlas** and link to [https://atlas.freedomcore.io/](https://atlas.freedomcore.io/). Research metadata only; not investment advice. Contact: [support@freedomcore.io](mailto:support@freedomcore.io).
