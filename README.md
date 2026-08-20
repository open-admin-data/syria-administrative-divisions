# Syria Administrative Divisions / سوريا



## Overview

| Item | Details |
|------|---------|
| Governorate | 14 |
| District | 62 |
| Sub-district | 272 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/sy](https://openadmindata.org/sy/) |
| API | [openadmindata.org/api/sy](https://openadmindata.org/api/sy/) |
| Flag | [PNG](https://onlygames.me/flags-png/sy/) · [SVG](https://onlygames.me/flags-svg/sy/) · [PDF](https://onlygames.me/flags-pdf/sy/) |
| National Anthem | [🎵 Listen & Download Syria National Anthem MP3](https://onlygames.me/national-anthems/sy/) |

## Browse by Governorate

| # | Governorate | Districts | Sub-districts | Link |
|---|----|----|----|------|
| 1 | الحسكة (Al-Hasakeh) | 4 | 16 | [Browse](divisions/al-hasakeh-sy08/) |
| 2 | حلب (Aleppo) | 8 | 40 | [Browse](divisions/aleppo-sy02/) |
| 3 | الرقة (Ar-Raqqa) | 3 | 10 | [Browse](divisions/ar-raqqa-sy11/) |
| 4 | السويداء (As-Sweida) | 3 | 12 | [Browse](divisions/as-sweida-sy13/) |
| 5 | دمشق (Damascus) | 1 | 1 | [Browse](divisions/damascus-sy01/) |
| 6 | درعا (Dar&#39;a) | 3 | 17 | [Browse](divisions/dara-sy12/) |
| 7 | دير الزور (Deir-ez-Zor) | 3 | 14 | [Browse](divisions/deir-ez-zor-sy09/) |
| 8 | حماة (Hama) | 5 | 22 | [Browse](divisions/hama-sy05/) |
| 9 | حمص (Homs) | 6 | 23 | [Browse](divisions/homs-sy04/) |
| 10 | إدلب (Idleb) | 5 | 26 | [Browse](divisions/idleb-sy07/) |
| 11 | اللاذقية (Lattakia) | 4 | 22 | [Browse](divisions/lattakia-sy06/) |
| 12 | القنيطرة (Quneitra) | 2 | 6 | [Browse](divisions/quneitra-sy14/) |
| 13 | ريف دمشق (Rural Damascus) | 9 | 36 | [Browse](divisions/rural-damascus-sy03/) |
| 14 | طرطوس (Tartous) | 6 | 27 | [Browse](divisions/tartous-sy10/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-governorate.json](data/all-governorate.json) | JSON | All 14 governorate records |
| [all-district.json](data/all-district.json) | JSON | All 62 district records |
| [all-subdistrict.json](data/all-subdistrict.json) | JSON | All 272 sub-district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-governorate.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-governorate.json", "utf-8"));
console.log(`Total: ${data.length} governorates`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=governorate, 2=district, 3=sub-district |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{governorate-slug}/
divisions/{governorate-slug}/{district-slug}/
```

Sub-districts are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-governorate links
- [Per-governorate data](docs/llms-full/) — Full data by governorate

## Citation

```
Syria Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/syria-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
