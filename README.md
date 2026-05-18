# TavaScope — POTA Activation Analyzer

**A free, open-source, privacy-first activation log analyzer for Parks on the Air (POTA) operators.**

🌐 **Live App:** [w4ggj.github.io/TavaScope](https://w4ggj.github.io/TavaScope)  
📻 **By:** Joe Leone, W4GGJ — [tavaone.com](https://tavaone.com)  
📄 **License:** MIT  
🔖 **Version:** v1.8

---

## What Is TavaScope?

TavaScope turns your ADIF activation logs into a full analysis dashboard — contact maps, stat blocks, rate charts, sortable activation history, and download-ready images for your blog or POTA page.

**Everything runs in your browser. No server. No account. No upload. Your data never leaves your device.**

---

## Features

### 📂 ADIF Import
- Upload any ADIF file exported from your logging software
- Compatible with standard ADIF exports from QRZ.com, POTA.app, DXKeeper, and other ADIF-compliant software
- Park name and park number auto-detected from the POTA API
- Drop a file, click to browse, or **try the built-in demo activation** to explore without uploading anything

### 📊 Three Analysis Views
| View | Description |
|------|-------------|
| **Single** | Full dashboard for one activation |
| **Combined** | Merged stats across selected activations |
| **Compare** | Side-by-side comparison between activations |

### 📈 Eleven Stat Blocks

**Row 1 — Core Stats**

| Stat Block | Description |
|------------|-------------|
| **Total QSOs** | Total contacts logged in the activation |
| **QSOs/Hour** | Average contact rate across the session |
| **Bands Used** | Number of distinct bands worked |
| **Primary Mode** | Most-used operating mode (CW, SSB, FT8, etc.) |
| **Unique Grids** | Number of unique Maidenhead grid squares worked |
| **Call Areas** | Number of distinct US call areas worked |

**Row 2 — Insight Stats**

| Stat Block | Description |
|------------|-------------|
| **Furthest QSO** | Most distant contact calculated from grid squares |
| **Best 1-Hour Period** | Highest QSO count in any rolling 60-minute window |
| **Hottest 15 Minutes** | Highest QSO count in any rolling 15-minute window |
| **Most Productive Band** | Band with the highest QSO count |
| **Most Active Mode** | Mode with the highest QSO count |

### 📉 Rate Detail Explorer
- Full-activation overview rate chart (10-minute bins)
- Zoomable detail chart with adjustable window sizes: **15m / 30m / 1h / 2h**
- Scrub slider to move the detail window through the activation timeline
- Jump buttons: **Start**, **Peak** (auto-finds your fastest period), **End**
- **UTC / Local timezone toggle** — switch all chart labels between UTC and your local time

### 🗺 Contact Map
Interactive contact map powered by Leaflet.js showing the geographic spread of all QSOs from an activation, plotted using grid squares with DXCC prefix fallback.

### 💾 Saved Activations
All activations saved locally in your browser with sort options:
- Newest / Oldest
- Most QSOs / Fewest QSOs
- Best Rate
- A→Z by park name

### 📥 Download Options
| Download | Description |
|----------|-------------|
| **Blog Card** | Full card with park info, date, and all 11 stat blocks — ready for blog posts |
| **Stats Only Card** | Stat blocks only, no park info — for your POTA page or homepage stats bar |
| **Full Dashboard** | Screenshot of everything currently on screen |
| **Contact Map** | Standalone map image |

---

## How to Use It

1. **Activate a park** and log your contacts in your preferred software
2. **Export your log** as an ADIF file
3. **Rename the file to your park ID** — for example, `us-6700.adi`
4. **Go to [w4ggj.github.io/TavaScope](https://w4ggj.github.io/TavaScope)**
5. **Upload your ADIF** — park name and number are detected automatically
6. **Explore your stats**, view your contact map, and download your images

> **Why rename the file?** TavaScope reads the park reference number from your filename and uses it to look up the park name from the POTA API. A filename like `us-6700.adi` or `k-4860.adi` works. A filename like `log_export.adi` does not.

No registration. No login. Works in any modern browser.

---

## Privacy

TavaScope is designed with privacy as a core principle:

- **All processing happens in your browser** — no data is sent to any server
- **No account or login required** — ever
- **No tracking, no analytics, no cookies**
- **Your logs stay on your device** — stored in browser localStorage
- Data is never shared or transmitted

---

## Supported Logging Software

TavaScope works with any logging software that exports standard ADIF files. Confirmed working:

| Software | Status |
|----------|--------|
| QRZ.com Logbook | ✅ Confirmed |
| POTA.app | ✅ Confirmed |
| DXKeeper | ✅ Confirmed |
| N1MM+ | ⚠️ Untested — likely works |
| WSJT-X | ⚠️ Untested — likely works |
| Ham Radio Deluxe | ⚠️ Untested — likely works |
| Log4OM | ⚠️ Untested — likely works |
| MacLoggerDX | ⚠️ Untested — likely works |

If you test TavaScope with software not on this list, please open an issue and report the result. See [ROADMAP.md](ROADMAP.md) for planned formal validation work.

---

## Running Locally

TavaScope is a static web app — no build step, no dependencies to install.

```bash
git clone https://github.com/w4ggj/TavaScope.git
cd TavaScope
```

Open `index.html` in your browser, or serve with any static file server:

```bash
npx serve .
# or
python3 -m http.server 8000
```

---

## Contributing

Contributions are welcome. If you are a ham radio operator, web developer, or both, there are meaningful ways to help:

- **Test with your own ADIF files** and report compatibility results
- **Add support for additional logging software** ADIF dialects
- **Improve the contact map** rendering or geographic data
- **Translate the UI** into other languages (POTA is a global program)
- **Open an issue** for bugs, feature requests, or questions

Please open an issue before starting significant new work so we can discuss the approach. See [ROADMAP.md](ROADMAP.md) for the full development plan.

---

## About the Author

Joe Leone is **W4GGJ**, a General Class amateur radio operator, POTA activator, and published author based in St. Petersburg, Florida (grid EL87PT). He is a member of SPARC (St. Petersburg Amateur Radio Club) and the Gulf Coast Contest Club.

He writes about amateur radio at [tavaone.com](https://tavaone.com) and is the author of *FT8 for the First Time*, available on [Amazon](https://amazon.com/author/tavaone).

---

## License

MIT License — see [LICENSE](LICENSE) for full text.

Copyright (c) 2025 Joe Leone (W4GGJ)
