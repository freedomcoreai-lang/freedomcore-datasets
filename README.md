<p align="center">
  <img src="assets/atlas-banner.png" alt="Atlas Symbol Coverage: 6,735 listings — 5,215 equities on 59 exchanges in 53 countries, 1,500 crypto assets, 20 benchmarks" width="100%">
</p>

# FreedomCore Atlas Open Datasets (CC BY 4.0)

I started publishing this register because joining market data on bare tickers quietly breaks things. "SOL" is Solana, but it's also four different listed companies. Every row here is keyed to one exact listing, so a join on the key can't silently merge them. Some listings are still waiting on source records, and each row's record_state says so. If you spot something wrong, open an issue and I'll look into it. Rob, FreedomCore.

[![Platform](https://img.shields.io/badge/Platform-atlas.freedomcore.io-0284c7)](https://atlas.freedomcore.io/)
[![Data catalog](https://img.shields.io/badge/Data_catalog-%2Fdatasets%2F-0f766e)](https://atlas.freedomcore.io/datasets/)
[![Directory](https://img.shields.io/badge/Directory-6%2C715_listings-4f46e5)](https://atlas.freedomcore.io/stocks/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-d97706)](https://creativecommons.org/licenses/by/4.0/)

Public, machine-readable reference datasets published by **[FreedomCore Atlas](https://atlas.freedomcore.io/)** for cross-border financial entity resolution, source-dated market developments and platform security verification.

> **Current release in this repository:** `atlas-symbol-coverage` **v4** (`atlas.symbol_coverage.v4`), **6,735** listings (5,215 equities, 1,500 crypto assets, plus indices, commodities and FX) across 69 unique venues (59 equity exchanges + 10 crypto & benchmark namespaces), checked `2026-11-21T21:31Z`. It refreshes daily, together with the [Hugging Face](https://huggingface.co/datasets/freedomcoreai/atlas-symbol-coverage) and [Kaggle](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-symbol-coverage) mirrors.

---

## 1. Canonical web entry points

| Surface | Canonical URL | Scope |
| :-- | :-- | :-- |
| Atlas homepage | [`https://atlas.freedomcore.io/`](https://atlas.freedomcore.io/) | Global market overview and dated observations |
| Public data catalog | [`/datasets/`](https://atlas.freedomcore.io/datasets/) | `schema.org/DataCatalog` index, CSV/JSON downloads |
| Symbol Coverage dataset page | [`/datasets/atlas-symbol-coverage/`](https://atlas.freedomcore.io/datasets/atlas-symbol-coverage/) | Canonical page for the files in this repository |
| Realm directory | [`/stocks/`](https://atlas.freedomcore.io/stocks/) | 6,715 company and crypto listings; equities across 53 countries |
| Research Centre | [`/workstation/`](https://atlas.freedomcore.io/workstation/) | Interactive research desk with source citations |
| Atlas Quakes | [`/quakes/`](https://atlas.freedomcore.io/quakes/) | Source-dated company and protocol developments; dated editions at `/quakes/YYYY-MM-DD/` since 2026-10-29 |
| Atlas Studio | [`/studio/`](https://atlas.freedomcore.io/studio/) | Audio briefings and recorded market observations |
| Daily Notes | [`/notes/daily/`](https://atlas.freedomcore.io/notes/daily/) | Receipt-bound public research editions |
| Methodology | [`/methodology/`](https://atlas.freedomcore.io/methodology/) | Source admission rules, clock separation, non-fabrication boundary |
| Security and trust | [`/security/`](https://atlas.freedomcore.io/security/) | Public controls and reproducible proof |

---

## 2. Dataset families and official mirrors

| Family | Canonical Atlas route | Hugging Face | Kaggle | Status in this repository |
| :-- | :-- | :-- | :-- | :-- |
| **Symbol Coverage** (`atlas-symbol-coverage`) | [`/datasets/atlas-symbol-coverage/`](https://atlas.freedomcore.io/datasets/atlas-symbol-coverage/) | [`freedomcoreai/atlas-symbol-coverage`](https://huggingface.co/datasets/freedomcoreai/atlas-symbol-coverage) | [`atlasfreedomcoreio/atlas-symbol-coverage`](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-symbol-coverage) | **v4** (6,735 rows, refreshed daily, digests below) |
| **Atlas Quakes (archive to 17 August 2026)** (`atlas-quakes-archive`) | [`/quakes/`](https://atlas.freedomcore.io/quakes/) | [`freedomcoreai/atlas-quakes-archive`](https://huggingface.co/datasets/freedomcoreai/atlas-quakes-archive) | Not mirrored | **Archive.** Earlier editions, published under the product's former name. This folder holds the 20 July 2026 edition; the Hugging Face archive runs to 17 August 2026. Live editions are on the site: [Atlas Quakes](https://atlas.freedomcore.io/quakes/) |
| **Global Ticker Collisions** (`atlas-global-ticker-collisions`) | [`/datasets/`](https://atlas.freedomcore.io/datasets/) | [`freedomcoreai/atlas-global-ticker-collisions`](https://huggingface.co/datasets/freedomcoreai/atlas-global-ticker-collisions) | [`atlasfreedomcoreio/atlas-global-ticker-collisions`](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-global-ticker-collisions) | **v1** (355 colliding bare-ticker groups / 781 verified listings; 353 equity+crypto groups / 776 listings; 100% HTTP 200 canonical URLs) |
| **Security Posture** (`atlas-security-posture`) | [`/datasets/atlas-security-posture/`](https://atlas.freedomcore.io/datasets/atlas-security-posture/) | [`freedomcoreai/atlas-security-posture`](https://huggingface.co/datasets/freedomcoreai/atlas-security-posture) | [`atlasfreedomcoreio/atlas-security-posture`](https://www.kaggle.com/datasets/atlasfreedomcoreio/atlas-security-posture) | **v3.3** (12 controls, re-checked 2026-11-20 against 6,735-row register; CSV, JSON, schema and summary in this folder) |

Mirror revisions are managed per platform and can lag this repository. The canonical Atlas dataset pages state the current revision for each platform.

---

## 3. Symbol Coverage v4 files and digests

| File | Bytes | SHA-256 | Description |
| :-- | --: | :-- | :-- |
| `atlas-symbol-coverage/atlas-symbol-coverage.csv` | 2,774,937 | `e4842641169b9bd1900e3e499f5c2e47db34d892ffdce3dfbdc752172afe3f82` | Full 6,735-row CSV register (25 columns, `atlas.symbol_coverage.v4`) |
| `atlas-symbol-coverage/atlas-symbol-coverage.json` | 5,637,677 | `9a3646db5ed066d67e2198249e6d1c732d89be776c5e5689f663e90f19f3a22f` | Full 6,735-record JSON register |
| `atlas-symbol-coverage/schema.json` | 3,720 | `8a69589461dc00b4e914e44c13d725ebb600647b5d609c4f1695dd44b01dd33f` | Machine-readable 25-column v4 schema |
| `atlas-symbol-coverage/atlas-symbol-coverage-summary.json` | 1,456 | `9e09f1b9c0af0205a7d55ce8edfb490cfc7a850f843d8221816378eef73aed50` | Counts for this release (quote, profile, research and chart layers) |

Columns (`25`): `listing_key`, `ticker`, `name`, `asset_class`, `exchange`, `country_code`, `route_slug`, `profile_url`, `workstation_url`, `sec_cik`, `coingecko_id`, `profile_state`, `profile_as_of`, `research_state`, `research_as_of`, `quote_state`, `quote_observed_at`, `chart_bars`, `checked_at`, `record_exists`, `record_state`, `record_checked_at`, `record_sha256`, `stored_source_count`, `dated_source_count`.

`listing_key` is the primary key: `EXCHANGE:TICKER` for equities, `CRYPTO:SYMBOL` or `COINGECKO:ID` for digital assets. `quote_state` says whether the price is live for that exchange's session (`live`), stored but awaiting a fresh accepted capture, stale, or held because the venue calendar isn't certified yet. `record_*` columns are carried from v3 with their original 23-25 October dates.

---

## 4. Why exact `listing_key` disambiguation matters (353 colliding bare-ticker groups)

Joining global datasets on bare ticker strings corrupts cross-border equity and crypto data. Across the 6,715 company and crypto listings in this register, **353 bare tickers collide across 776 distinct listings.** Every record is keyed by its exact `listing_key` and canonical profile route:

| Bare ticker | Canonical `listing_key` | Instrument | Class | Country | Canonical profile route | `quote_state` |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| `SOL` | `CRYPTO:SOL` | Solana | `crypto` | `GL` | [`/stocks/SOL/`](https://atlas.freedomcore.io/stocks/SOL/) | `live` |
| `SOL` | `ASX:SOL` | Washington H. Soul Pattinson and Company Limited | `equity` | `AU` | [`/stocks/asx-sol/`](https://atlas.freedomcore.io/stocks/asx-sol/) | `live` |
| `SOL` | `BME:SOL` | Soltec Power Holdings SA | `equity` | `ES` | [`/stocks/bme-sol/`](https://atlas.freedomcore.io/stocks/bme-sol/) | `live` |
| `SOL` | `JSE:SOL` | Sasol Limited | `equity` | `ZA` | [`/stocks/jse-sol/`](https://atlas.freedomcore.io/stocks/jse-sol/) | `live` |
| `SOL` | `MIL:SOL` | SOL S.p.A. | `equity` | `IT` | [`/stocks/mil-sol/`](https://atlas.freedomcore.io/stocks/mil-sol/) | `live` |
| `ARB` | `CRYPTO:ARB` | Arbitrum | `crypto` | `GL` | [`/stocks/ARB/`](https://atlas.freedomcore.io/stocks/ARB/) | `live` |
| `ARB` | `NZX:ARB` | ArborGen Holdings Limited | `equity` | `NZ` | [`/stocks/nzx-arb/`](https://atlas.freedomcore.io/stocks/nzx-arb/) | `live` |
| `BCH` | `CRYPTO:BCH` | Bitcoin Cash | `crypto` | `GL` | [`/stocks/BCH/`](https://atlas.freedomcore.io/stocks/BCH/) | `live` |
| `BCH` | `SET:BCH` | Bangkok Chain Hospital Public Co., Ltd. | `equity` | `TH` | [`/stocks/set-bch/`](https://atlas.freedomcore.io/stocks/set-bch/) | `live` |
| `LDO` | `COINGECKO:lido-dao` | Lido DAO | `crypto` | `GL` | [`/stocks/cg-lido-dao/`](https://atlas.freedomcore.io/stocks/cg-lido-dao/) | `live` |
| `LDO` | `MIL:LDO` | Leonardo SpA | `equity` | `IT` | [`/stocks/mil-ldo/`](https://atlas.freedomcore.io/stocks/mil-ldo/) | `live` |
| `1810` | `HKEX:1810` | Xiaomi Corporation Class B | `equity` | `HK` | [`/stocks/hkex-1810/`](https://atlas.freedomcore.io/stocks/hkex-1810/) | `live` |
| `1810` | `TADAWUL:1810` | Seera Holding Group | `equity` | `SA` | [`/stocks/tadawul-1810/`](https://atlas.freedomcore.io/stocks/tadawul-1810/) | `live` |
| `7203` | `TADAWUL:7203` | Elm Company | `equity` | `SA` | [`/stocks/tadawul-7203/`](https://atlas.freedomcore.io/stocks/tadawul-7203/) | `live` |
| `7203` | `TSE:7203` | Toyota | `equity` | `JP` | [`/stocks/7203/`](https://atlas.freedomcore.io/stocks/7203/) | `live` |

---

## 5. Coverage in this release (2026-11-21)

| Metric | Value | Note |
| :-- | --: | :-- |
| Listings | 6,735 | 5,215 equities, 1,500 crypto, 9 indices, 8 commodities, 3 FX |
| Venues | 69 | 59 equity exchanges + 10 crypto & benchmark namespaces |
| Live price | 5,304 | current for the listing's exchange session |
| Stored price awaiting fresh capture | 994 | |
| Valid price held (calendar not certified) | 48 | |
| Stale / none collected / source conflict | 366 / 2 / 21 | |
| Verified profile text | 6,735 | |
| Research report observed | 5,161 | |
| Chart renderable | 5,728 | listings with daily bars |

Counts are computed from the files in this repository. Unknown never means delisted, and prices that fail a check are held rather than guessed.

---

## 6. Provenance and licence

All files are published by FreedomCore Atlas and derived from https://atlas.freedomcore.io. Each row maps to a real, indexable Atlas page. This is research metadata: not financial advice, not signals, not brokerage execution.

Released under **[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)**. Reuse, including commercial reuse, is permitted with attribution to **FreedomCore Atlas** and a link to https://atlas.freedomcore.io/. See [LICENSE](LICENSE). Contains public identity and provenance metadata only: no paid research prose, no third-party article bodies, no subscriber data.

Contact: [support@freedomcore.io](mailto:support@freedomcore.io)
