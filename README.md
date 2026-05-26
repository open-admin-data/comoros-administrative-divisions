# Comoros Administrative Divisions / Comores



## Overview

| Item | Details |
|------|---------|
| Island | 3 |
| Prefecture | 17 |
| Commune | 55 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-26 |

## Browse by Island

| # | Island | Prefectures | Communes | Link |
|---|----|----|----|------|
| 1 | Anjouan (Ndzouani) | 5 | 20 | [Browse](divisions/anjouan-ndzouani-km1/) |
| 2 | Grande Comore (Ngazidja) | 9 | 29 | [Browse](divisions/grande-comore-ngazidja-km2/) |
| 3 | Mohéli (Mwali) | 3 | 6 | [Browse](divisions/mohli-mwali-km3/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-island.json](data/all-island.json) | JSON | All 3 island records |
| [all-prefecture.json](data/all-prefecture.json) | JSON | All 17 prefecture records |
| [all-commune.json](data/all-commune.json) | JSON | All 55 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-island.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['prefecture']} prefectures")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-island.json", "utf-8"));
console.log(`Total: ${data.length} islands`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=island, 2=prefecture, 3=commune |
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
divisions/{island-slug}/
divisions/{island-slug}/{prefecture-slug}/
```

Communes are listed inline in each prefecture's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-island links
- [Per-island data](docs/llms-full/) — Full data by island

## Citation

```
Comoros Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/comoros-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
