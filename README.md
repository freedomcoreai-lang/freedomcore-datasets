# FreedomCore Atlas Open Datasets (CC BY 4.0)

[![Platform](https://img.shields.io/badge/Platform-atlas.freedomcore.io-0284c7)](https://atlas.freedomcore.io/)
[![Data catalog](https://img.shields.io/badge/Data_catalog-%2Fdatasets%2F-0f766e)](https://atlas.freedomcore.io/datasets/)
[![Directory](https://img.shields.io/badge/Directory-6%2C375_listings-4f46e5)](https://atlas.freedomcore.io/stocks/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-d97706)](https://creativecommons.org/licenses/by/4.0/)

Public, machine-readable reference datasets published by **[FreedomCore Atlas](https://atlas.freedomcore.io/)** for cross-border financial entity resolution, source-dated market developments and platform security verification.

> **Current release in this repository:** `atlas-symbol-coverage` **v3** (`atlas.symbol_coverage.v3`), **6,375** canonical company and crypto listings, data generated `2026-10-25T09:48:00Z`, byte-identical to the files served at the canonical dataset page. It supersedes the 2026-07-20 (200+ symbol) files previously published here.

---

## 1. Canonical web entry points

| Surface | Canonical URL | Scope |
| :-- | :-- | :-- |
| Atlas homepage | [`https://atlas.freedomcore.io/`](https://atlas.freedomcore.io/) | Global market overview and dated observations |
| Public data catalog | [`/datasets/`](https://atlas.freedomcore.io/datasets/) | `schema.org/DataCatalog` index, CSV/JSON downloads |
| Symbol Coverage dataset page | [`/datasets/atlas-symbol-coverage/`](https://atlas.freedomcore.io/datasets/atlas-symbol-coverage/) | Canonical page for the files in this repository |
| Realm directory | [`/stocks/`](https://atlas.freedomcore.io/stocks/) | 6,375 company and crypto listings across 53 countries |
| Research Centre | [`/workstation/`](https://atlas.freedomcore.io/workstation/) | Interactive research desk with source citations |
| Atlas Quakes | [`/quakes/`](https://atlas.freedomcore.io/quakes/) | Source-dated company and protocol developments (successor to Market Pulse) |
| Atlas Studio | [`/studio/`](https://atlas.freedomcore.io/studio/) | Audio briefings and recorded market observations |
| Daily Notes | [`/notes/daily/`](https://atlas.freedomcore.io/notes/daily/) | Receipt-bound public research editions |
| Methodology | [`/methodology/`](https://atlas.freedomcore.io/methodology/) | Source admission rules, clock separation, non-fabrication boundary |
| Security and trust | [`/security/`](https://atlas.freedomcore.io/security/) | Public controls and reproducible proof |

---

## 2. Dataset families and official mirrors

| Family | Canonical Atlas route | Hugging Face | Kaggle | Status in this repository |
| :-- | :-- | :-- | :-- | :-- |
| **Symbol Coverage** (`atlas-symbol-coverage`) | [`/datasets/atlas-symbol-coverage/`](https://atlas.freedomcore.io/datasets/atlas-symbol-coverage/) | [`freedomcoreai/atlas-symbol-coverage`](https://huggingface.co/datasets/freedomcoreai/atlas-symbol-coverage) | [`atlasfreedomcoreio/atlas-symbol-coverage`](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-symbol-coverage) | **v3** (6,375 rows, three files, digests below) |
| **Market Pulse** (`atlas-market-pulse`) | [`/datasets/atlas-market-pulse/`](https://atlas.freedomcore.io/datasets/atlas-market-pulse/) | [`freedomcoreai/atlas-market-pulse`](https://huggingface.co/datasets/freedomcoreai/atlas-market-pulse) | Removed | **Retired product.** Files here are the retained 2026-07-20 snapshot, unchanged. Live successor: [Atlas Quakes](https://atlas.freedomcore.io/quakes/) |
| **Security Posture** (`atlas-security-posture`) | [`/datasets/atlas-security-posture/`](https://atlas.freedomcore.io/datasets/atlas-security-posture/) | [`freedomcoreai/atlas-security-posture`](https://huggingface.co/datasets/freedomcoreai/atlas-security-posture) | [`atlasfreedomcoreio/atlas-security-posture`](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-security-posture) | Retained 2026-07-20 snapshot, unchanged. Current controls: [`/security/`](https://atlas.freedomcore.io/security/) |

Mirror revisions are managed per platform and can lag this repository. The canonical Atlas dataset pages state the current revision for each platform.

---

## 3. Symbol Coverage v3 files and digests

| File | Bytes | SHA-256 | Description |
| :-- | --: | :-- | :-- |
| `atlas-symbol-coverage/atlas-symbol-coverage.csv` | 1,681,073 | `ceee6577ee01758b0449187149187926ede6c4186eae83e0971e16a4a455d8ef` | Full 6,375-row CSV register (16 columns, `atlas.symbol_coverage.v3`) |
| `atlas-symbol-coverage/atlas-symbol-coverage.json` | 4,291,344 | `ee6f0e00a34fdcab10f86c4457c00488fe1b7f9bcf922f2ca851072b96ed03e3` | Full 6,375-record JSON register with reconciled counts and source pins |
| `atlas-symbol-coverage/schema.json` | 13,128 | `046caa03c47d8b68777bdf345fa63aa294415c87903d915cec9f6156cf2767a6` | Machine-readable 16-column v3 schema and v1-to-v3 field map |

Columns (`16`): `listing_key`, `ticker`, `name`, `asset_class`, `country_code`, `route_slug`, `profile_url`, `workstation_url`, `sec_cik`, `coingecko_id`, `record_exists`, `record_state`, `record_checked_at`, `record_sha256`, `stored_source_count`, `dated_source_count`.

`listing_key` is the primary key: `EXCHANGE:TICKER` for equities, `CRYPTO:SYMBOL` or `COINGECKO:ID` for digital assets. `profile_url` and `workstation_url` are the canonical Atlas routes for each listing.

---

## 4. Why exact `listing_key` disambiguation matters (330 colliding bare-ticker groups)

Joining global datasets on bare ticker strings corrupts cross-border equity and crypto data. Across the 6,375 canonical listings in this register, **330 bare tickers collide across 722 distinct canonical listings.** Every record is keyed by its exact `listing_key` and canonical profile route:

| Bare ticker | Canonical `listing_key` | Instrument | Class | Country | Canonical profile route | `record_state` |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| `SOL` | `CRYPTO:SOL` | Solana | `crypto` | `GL` | [`/stocks/SOL/`](https://atlas.freedomcore.io/stocks/SOL/) | `populated` |
| `SOL` | `ASX:SOL` | Washington H. Soul Pattinson and Company Limited | `equity` | `AU` | [`/stocks/asx-sol/`](https://atlas.freedomcore.io/stocks/asx-sol/) | `record_missing` |
| `SOL` | `BME:SOL` | Soltec Power Holdings SA | `equity` | `ES` | [`/stocks/bme-sol/`](https://atlas.freedomcore.io/stocks/bme-sol/) | `record_missing` |
| `SOL` | `JSE:SOL` | Sasol Limited | `equity` | `ZA` | [`/stocks/jse-sol/`](https://atlas.freedomcore.io/stocks/jse-sol/) | `evidence_collected` |
| `SOL` | `MIL:SOL` | SOL S.p.A. | `equity` | `IT` | [`/stocks/mil-sol/`](https://atlas.freedomcore.io/stocks/mil-sol/) | `record_missing` |
| `ARB` | `CRYPTO:ARB` | Arbitrum | `crypto` | `GL` | [`/stocks/ARB/`](https://atlas.freedomcore.io/stocks/ARB/) | `populated` |
| `ARB` | `NZX:ARB` | ArborGen Holdings Limited | `equity` | `NZ` | [`/stocks/nzx-arb/`](https://atlas.freedomcore.io/stocks/nzx-arb/) | `evidence_collected` |
| `BCH` | `CRYPTO:BCH` | Bitcoin Cash | `crypto` | `GL` | [`/stocks/BCH/`](https://atlas.freedomcore.io/stocks/BCH/) | `populated` |
| `BCH` | `SET:BCH` | Bangkok Chain Hospital Public Co., Ltd. | `equity` | `TH` | [`/stocks/set-bch/`](https://atlas.freedomcore.io/stocks/set-bch/) | `evidence_collected` |
| `LDO` | `COINGECKO:lido-dao` | Lido DAO | `crypto` | `GL` | [`/stocks/cg-lido-dao/`](https://atlas.freedomcore.io/stocks/cg-lido-dao/) | `populated` |
| `LDO` | `MIL:LDO` | Leonardo SpA | `equity` | `IT` | [`/stocks/mil-ldo/`](https://atlas.freedomcore.io/stocks/mil-ldo/) | `evidence_collected` |
| `1810` | `HKEX:1810` | Xiaomi Corporation Class B | `equity` | `HK` | [`/stocks/hkex-1810/`](https://atlas.freedomcore.io/stocks/hkex-1810/) | `record_missing` |
| `1810` | `TADAWUL:1810` | Seera Holding Group | `equity` | `SA` | [`/stocks/tadawul-1810/`](https://atlas.freedomcore.io/stocks/tadawul-1810/) | `record_missing` |
| `7203` | `TADAWUL:7203` | Elm Company | `equity` | `SA` | [`/stocks/tadawul-7203/`](https://atlas.freedomcore.io/stocks/tadawul-7203/) | `record_missing` |
| `7203` | `TSE:7203` | Toyota | `equity` | `JP` | [`/stocks/7203/`](https://atlas.freedomcore.io/stocks/7203/) | `evidence_collected` |

---

## 5. Reconciled coverage and source-record accounting

| Metric | Value | Unit |
| :-- | --: | :-- |
| Company and crypto canonical listings | 6,375 | 4,875 equities across 53 countries + 1,500 crypto assets |
| Total Realm identities | 6,394 | listings + 8 indices + 8 commodities + 3 FX pairs |
| Runtime research admission | 5,163 admitted / 1,231 held | per `TERMINAL_REALM_REVIEW.json` |
| Stored source records present | 3,961 | `populated` 1,244, `evidence_collected` 2,054, `source_unavailable` 572, `checked_no_signal` 91 |
| Stored source records missing | 2,414 | explicit `record_state: "record_missing"` (never blank) |
| `coingecko_id` bound | 1,500 | all crypto rows |
| `sec_cik` bound | 100 | canonical equity rows with SEC filings |

Directory registration, runtime research admission and stored source-record state are separate clocks and are never conflated. Listing, class, country and record-state counts are computed from the CSV in this repository. Realm identity and admission counts come from the reconciled summary published with the v3 release.

---

## 6. Provenance and licence

All files are published by FreedomCore Atlas and derived from https://atlas.freedomcore.io. Each row maps to a real, indexable Atlas page. This is research metadata: not financial advice, not signals, not brokerage execution.

Released under **[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)**. Reuse, including commercial reuse, is permitted with attribution to **FreedomCore Atlas** and a link to https://atlas.freedomcore.io/. See [LICENSE](LICENSE). Contains public identity and provenance metadata only: no paid research prose, no third-party article bodies, no subscriber data.

Contact: freedomcoreai@gmail.com
