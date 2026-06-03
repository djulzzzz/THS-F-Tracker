# 🌸 THS-F Tracker

A personal PWA for tracking feminizing hormone therapy — patches, blood work, body measurements, and milestones. Fully offline, zero server, all data stays on your device.

Built by and for trans women. No accounts, no cloud, no analytics.

---

## Features

**🩹 Patch tracking**
- Log each patch with date, time, and placement site (rotation chips)
- Automatic next-patch countdown with urgency states
- Configurable interval (default 3 days)

**🩸 Blood work**
- Log E2, testosterone, LH, FSH, prolactin
- Target range indicators with ✓ / ⚠ badges
- Trend arrows between entries (↑ ↓ →)
- SVG charts for E2 and testosterone over time

**📏 Body measurements**
- Track weight, chest, underbust, waist, hips
- Bra size calculator (EU sizing)
- Multi-curve silhouette chart
- Optional feminization index score and waist/chest ratio card (can be hidden in settings)

**🏆 Milestones**
- Timeline from Day 1 to 2 years with detailed physical, emotional, and practical notes per stage
- Progress bar toward next milestone
- Expandable detail panels

**⚙️ Settings**
- Patch interval and dose
- HRT start date
- Toggle feminization index card on/off
- Toggle waist/chest ratio card on/off
- Export all data as JSON
- Import from JSON backup
- Full data reset

---

## Stack

Single `.html` file — no build step, no dependencies, no backend.

- Vanilla HTML / CSS / JS
- `localStorage` for persistence
- Service Worker (injected as Blob URL) for offline support
- PWA manifest for Add to Home Screen on iOS and Android
- SVG charts drawn by hand (no chart library)

---

## Usage

### Option A — hosted

Upload `ths2.html` anywhere static (GitHub Pages, Netlify, your own server). Open in browser. Done.

### Option B — local

```bash
# No install needed — just open the file
open ths2.html
```

> For the Service Worker to register, serve over HTTP rather than the `file://` protocol. Use any static server:
> ```bash
> npx serve .
> # or
> python3 -m http.server
> ```

### Add to Home Screen

On iOS: Share → Add to Home Screen  
On Android: browser menu → Install app / Add to Home Screen

---

## Data

All data is stored in `localStorage` under the keys:

| Key | Contents |
|---|---|
| `ths2_config` | interval, dose, start date, display preferences |
| `ths2_patches` | patch history |
| `ths2_bilans` | blood work entries |
| `ths2_mensurations` | body measurements |

### Backup & restore

Settings → **📤 Export** generates a timestamped `.json` file.  
Settings → **📥 Import** restores from any backup.

The JSON format is straightforward if you want to seed it manually or migrate from another tool:

```json
{
  "config": {
    "patch_interval_days": 3,
    "patch_dose": "100µg",
    "start_date": "2026-05-18",
    "show_femin": true,
    "show_ratio": false
  },
  "patches": [
    { "id": 1, "applied_at": "2026-05-18 20:30:00", "site": "Cuisse D", "note": "" }
  ],
  "bilans": [
    { "id": 1, "date_bilan": "2026-05-20", "e2": 142, "testosterone": 28, "lh": 0.4, "fsh": 1.2, "prolactine": 8.1, "note": "3 semaines patch" }
  ],
  "mensurations": [
    { "id": 1, "date_mesure": "2026-06-01", "poids": 90.3, "tour_poitrine": 101, "tour_sous_poitrine": 96, "tour_taille": 97, "tour_hanches": 107, "note": "" }
  ]
}
```

---

## Blood work reference ranges

These are the target ranges used for badge coloring — adjust to your protocol and doctor's guidance.

| Marker | Target |
|---|---|
| E2 | 100 – 200 pg/mL |
| Testosterone | < 50 ng/dL |
| LH | < 3 UI/L |
| FSH | < 8 UI/L |
| Prolactin | < 25 µUI/mL |

---

## Privacy

Nothing leaves your device. No requests are made to any external server (the Service Worker only caches the app itself for offline use). No cookies, no telemetry, no third-party scripts.

---

## License

Do whatever you want with it. If it helps someone, that's enough.
