# TavaScope Roadmap

TavaScope is a free, open-source, privacy-first ADIF activation log analyzer built for the global Parks on the Air (POTA) community. This roadmap describes the current state of the project and the planned development path.

All features on this roadmap will be released under the MIT License and remain free to use, self-host, and modify.

---

## Current State — v1.7

TavaScope is a working, deployed web application with an active user base in the POTA community. Core capabilities include:

- ADIF file import — confirmed working with QRZ.com, POTA.app, and DXKeeper
- Automatic park name and number detection via the POTA API
- Single, Combined, and Compare activation analysis views
- Eleven stat blocks across two rows:
  - **Row 1 (Core):** Total QSOs, QSOs/Hour, Bands Used, Primary Mode, Unique Grids, Call Areas
  - **Row 2 (Insight):** Furthest QSO, Best 1-Hour Period, Hottest 15 Minutes, Most Productive Band, Most Active Mode
- Interactive contact map (Leaflet.js) with grid square and DXCC prefix fallback
- Four download formats: Blog Card, Stats Only Card, Full Dashboard, Contact Map
- Sort and filter across saved activations (newest, oldest, most QSOs, best rate, A→Z)
- Browser-based local storage — no server, no account, no data upload
- Fully static — runs in any browser, self-hostable with no backend

---

## Phase 1 — Broad ADIF Validation and Robustness (Near-Term)

**Goal:** Formally validate TavaScope against the full range of logging software used by the POTA community and harden the parser for real-world edge cases.

TavaScope already works with standard ADIF exports from QRZ.com, POTA.app, and DXKeeper. Because ADIF is a standardized format, most compliant software should work without modification. However, real-world ADIF files vary in how they handle optional fields, encoding, line endings, and POTA-specific extensions such as `MY_SIG` and `MY_SIG_INFO`.

Planned work:
- Formal test suite using real ADIF samples from N1MM+, WSJT-X, Ham Radio Deluxe, Log4OM, and MacLoggerDX
- Graceful error handling and clear user feedback for malformed or unrecognized fields
- ADIF field normalization to handle version and dialect variations across software
- Community ADIF sample library — operators contribute anonymized test files across software versions
- Documentation of confirmed-compatible software with version numbers

This phase moves TavaScope from "works in practice" to "verified compatible" — a meaningful distinction for operators who need to trust their data.

---

## Phase 2 — Beyond POTA (Medium-Term)

**Goal:** Extend TavaScope to serve operators participating in other portable on-the-air programs that use ADIF logs.

POTA is the largest parks-on-the-air program globally, but it is not the only one. Summits on the Air (SOTA), World Wide Flora and Fauna (WWFF), Islands on the Air (IOTA), and Castles on the Air (COTA) all use ADIF-based logging and have large, active international communities. The core analysis engine in TavaScope applies to all of them.

Planned work:
- SOTA reference detection and summit data lookup
- WWFF reference detection and nature area data lookup
- IOTA reference support
- Program-agnostic analysis mode for any ADIF-based portable operation
- Combined cross-program stats view for operators active in multiple programs

This phase transforms TavaScope from a POTA-specific tool into general-purpose portable operations analysis software serving a significantly larger global community.

---

## Phase 3 — Mobile and Field Use (Medium-Term)

**Goal:** Make TavaScope usable in the field, not just at home after an activation.

POTA operators are by definition in the field. A tool that only works well on desktop misses a critical use case — reviewing stats and sharing results immediately after an activation from a phone or tablet.

Planned work:
- Responsive mobile layout optimized for phone screens
- Progressive Web App (PWA) support — installable on phone home screen
- Offline capability — app functions without an internet connection after first load
- Touch-optimized controls for the contact map and stat blocks
- Lightweight mobile download format optimized for sharing to social media from the field

---

## Phase 4 — Multilingual Support (Medium-Term)

**Goal:** Make TavaScope accessible to the global ham radio community in their own languages.

POTA is active in dozens of countries across six continents. The current English-only UI is a barrier for the large international community of operators in Japan, Germany, Brazil, Spain, France, and beyond.

Planned work:
- Internationalization (i18n) framework for all UI strings
- Initial translations: Spanish, German, Japanese, Portuguese, French
- Community-contributed translation workflow via GitHub
- Locale-aware date, time, and number formatting

---

## Phase 5 — Community and Sharing Features (Longer-Term)

**Goal:** Enable operators to share results publicly without compromising the privacy-first design.

TavaScope will never require accounts or upload user data to a server. However, operators frequently want to share their activation stats publicly — on social media, on their POTA page, or in club newsletters. This can be achieved entirely client-side.

Planned work:
- Shareable activation cards generated entirely in-browser
- Operator profile export — a static, self-contained HTML page summarizing all activations
- Optional public stats URL using URL-encoded data (no server required)
- Enhanced image exports with social media dimension presets
- Printable activation summary report for club logs and paper records

---

## Phase 6 — Contribution Infrastructure (Ongoing)

**Goal:** Make TavaScope a project that others can contribute to, not just use.

Planned work:
- Comprehensive developer documentation
- Contributor guide and code of conduct
- Automated ADIF test suite with real-world sample files across logging software
- CI/CD pipeline for automated testing on pull requests
- Translation contribution workflow and tooling

---

## Long-Term Vision

TavaScope's long-term goal is to become the standard open-source portable operations analyzer for the global amateur radio community — a neutral, privacy-respecting, community-maintained tool that any operator can use, any club can recommend, and any developer can contribute to.

Amateur radio portable operations programs are growing rapidly worldwide. TavaScope aims to grow with them, remaining free, open, and operator-first.

---

## Contributing

If you want to help build any phase of this roadmap, please open an issue on GitHub to discuss your idea before starting work. Contributions of all kinds are welcome — code, testing, translations, documentation, and ADIF sample files for testing.

See [README.md](README.md) for setup instructions.

---

## Version History

| Version | Notes |
|---------|-------|
| v1.7 | Current release — ADIF import, POTA API park detection, contact map, 11 stat blocks, three analysis views, four download formats, browser localStorage |
| v1.0–v1.6 | Initial development and iteration |
