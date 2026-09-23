# I Ching and Bazi Source Code | Five Elements and JavaScript Chart Pages

[简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.en.md) · [Product page](https://niubideren111.github.io/I-Ching-Divination-System/en/)

A JavaScript Bazi chart reference with common utilities, timezone handling and image export support, accompanied by screenshots of traditional Chinese chart interfaces.

**I Ching source code · Bazi source code · Chinese astrology JavaScript · five elements chart**

## Introduction

This repository is a Zhouyi development reference whose public runnable entry point is a browser-based Bazi chart page. The root `index.html` accepts birth date, time and gender inputs and presents Four Pillars, Ten Gods, hidden stems, luck cycles, annual cycles and transition information. `common.js`, `utils.js`, `timezone.js` and `canvas2image.js` support shared logic, timezone handling and chart-image export.

The documentation also describes interface structures and product references for Zi Wei Dou Shu, Qi Men Dun Jia, Da Liu Ren and Seven Governors and Four Remainders. In the public file set, these extended systems are primarily documentation or screenshot material; treat an algorithm as implemented only when its referenced source is present.

## Features

| Feature | Public implementation or reference scope |
|---|---|
| Four Pillars Bazi chart | Browser presentation of year, month, day and hour pillars |
| Ten Gods and hidden stems | Information areas associated with each pillar |
| Luck and annual cycles | UI and data presentation for cycles and transition timing |
| Birth-data input | Date, time and gender inputs for chart generation |
| Timezone support | Supporting timezone material in `timezone.js` |
| Image export | Canvas image-export support in `canvas2image.js` |
| Five Elements references | Numeric workbook, explanatory document and stem-branch PDF |
| Zi Wei Dou Shu references | Interface and data-structure documentation in `docs/algorithm_api.md` |
| Qi Men Dun Jia references | Documented time-chart, configuration and direction examples |
| Seven Governors references | Documented planetary-chart data structures and product screenshots |
| Da Liu Ren references | Product screenshots and extended-module documentation |
| Static web deployment | HTML and JavaScript deployment through static hosting |

## Technical composition and public scope

| Layer | Material |
|---|---|
| Page | HTML, CSS and vanilla JavaScript Bazi chart page |
| Utilities | Shared functions, date/timezone helpers and Canvas image export |
| Data references | Five Elements values, stem-branch ordering and supporting documents |
| Interface documentation | Bazi, Zi Wei Dou Shu, Qi Men Dun Jia and Seven Governors structures |
| Visual references | Bazi, Da Liu Ren, annual-cycle and other chart screenshots |

This project is suitable as a learning reference for traditional-culture chart pages, data structures and interface design. Calendar rules vary by timezone, true solar time, day-boundary convention and school. Validate results against authoritative calendars and test cases, and do not treat demonstration output as a basis for real-world decisions.

## What this repository presents

### Bazi chart page

The root index.html is the original chart page; the product presentation remains isolated under docs.

### Web utilities

Review common.js, utils.js, timezone.js and canvas2image.js as supporting files.

### Chart design references

Use screenshots and Five Elements tables to study information architecture for chart products.

## How to evaluate the material

1. **Confirm the product:** review the screenshots and captions to identify the product type and visible workflow.
2. **Inspect the evidence:** open the listed source files or documents instead of relying on feature claims alone.
3. **Check buildability:** verify that required dependencies, assets, configuration and startup scripts are present for the part you intend to run.
4. **Confirm licensing:** read the repository license and obtain written permission for any commercial assets or complete-project delivery.

## Product screenshots

![Bazi chart with stems and branches](docs/assets/seo/i-ching-divination-system-01.jpg)

![Da Liu Ren chart table](docs/assets/seo/i-ching-divination-system-02.jpg)

![Annual-cycle data and chart list](docs/assets/seo/i-ching-divination-system-03.jpg)

![Bazi information summary screen](docs/assets/seo/i-ching-divination-system-04.jpg)

## Public source and documents

| File | Description |
|---|---|
| [index.html](index.html) | Public HTML file: index.html. |
| [common.js](common.js) | Public JS file: common.js. |
| [timezone.js](timezone.js) | Public JS file: timezone.js. |
| [canvas2image.js](canvas2image.js) | Public JS file: canvas2image.js. |
| [五行数值328.xlsx](%E4%BA%94%E8%A1%8C%E6%95%B0%E5%80%BC328.xlsx) | Public XLSX file: 五行数值328.xlsx. |
| [docs/algorithm_api.md](docs/algorithm_api.md) | Public MD file: algorithm_api.md. |

## Start reading

```bash
git clone https://github.com/niubideren111/I-Ching-Divination-System.git
cd I-Ching-Divination-System
```

## Questions

### Does the presentation replace the original chart page?

No. The presentation is under docs while the original root index.html remains intact.

### Are all algorithms shown in screenshots included?

The public code entry focuses on the Bazi page and supporting JavaScript; other screenshots describe the broader product interface.

## Documentation roadmap

Future updates should add a versioned dependency list, a verified setup or import procedure, a concise architecture or product-flow diagram, and release notes tied to real file changes. Large authorized assets belong in GitHub Releases with checksums; secrets, production endpoints and user data must never be committed.

## Related repositories

- [Chess-and-Card-Game-Product-Design-Copy](https://github.com/niubideren111/Chess-and-Card-Game-Product-Design-Copy)

## Scope and license

The public repository includes the Bazi page, JavaScript utilities, design references and chart screenshots. Screenshots do not imply that every depicted algorithm is publicly included. Public files should be evaluated against their actual paths, dependencies and license. No search ranking, production readiness or performance result is guaranteed.

- Telegram: [@fox_lovemyself](https://t.me/fox_lovemyself)
- GitHub: [I-Ching-Divination-System](https://github.com/niubideren111/I-Ching-Divination-System)
