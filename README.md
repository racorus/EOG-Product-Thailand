# Thailand Fire Monitoring – VIIRS Nightfire & Burned Area Alerts

This repository automatically collects and publishes **wildfire detection alerts** for Thailand from the **Earth Observation Group (EOG), Colorado School of Mines** (VIIRS Nightfire & Burned Area Detection).

---

## 🔥 Fire Alert Types

| Dataset | Name | Description |
|---------|------|-------------|
| **VNF** | VIIRS NightFire | Detects thermal anomalies and active fire using nighttime SWIR/LWIR |
| **VBD** | VIIRS Burned Area Detection | Detects burned area pixels from VIIRS |

---

## 🌏 Region Covered

- Thailand territory and border regions
- Includes national parks, forest areas, and agricultural zones

---

## 🛰️ Satellite Sources

**Satellites:** NOAA-20 (JPSS-1) & Suomi NPP — VIIRS Sensors  
**Update frequency:** Automatically updated when a new EOG alert email arrives (every ~12 hours)

---

## 🗂️ Folder Structure

```
EOG-Product-Thailand/
├── VNF/                        ← VIIRS NightFire (active fire)
│   └── YYYY/
│       └── MM/
│           └── DD/
│               ├── *.csv       ← Detection data (lat, lon, intensity, …)
│               ├── *.kmz       ← Google Earth overlay
│               └── *.png       ← Map image from EOG alert email
│
├── VBD/                        ← VIIRS Burned Area Detection
│   └── YYYY/
│       └── MM/
│           └── DD/
│               ├── *.csv
│               ├── *.kmz
│               └── *.png
│
└── README.md
```

---

## 📥 How to Use

### Download a specific date
Browse to the folder for the date you need, for example:
```
VNF/2026/04/01/
VBD/2026/04/01/
```

### View in Google Earth
Download the `.kmz` file and open it directly in **Google Earth Pro** or **Google Earth web**.

### Analyse detection data
Download the `.csv` file — it contains columns such as latitude, longitude, detection time, radiant heat, and satellite pass information.

### Browse via the data viewer
Open [`index.html`](./index.html) (GitHub Pages) to browse all dates, preview CSV data, and view detection points on an interactive map.

---

## ⚙️ Data Pipeline

Emails from `eog@mines.edu` are monitored automatically via **n8n**:

1. Gmail receives VNF / VBD alert email from EOG
2. n8n extracts the CSV and KMZ download links from the email body
3. Files are downloaded and uploaded to this repository under the correct `VNF/` or `VBD/` folder
4. The alert email is deleted from Gmail after a successful upload
5. Map images attached to the email are also saved alongside the data files

---

## 🔗 Data Source

- **Provider:** [Earth Observation Group (EOG)](https://eogdata.mines.edu/) — Colorado School of Mines
- **Product:** VIIRS Nightfire (VNF) & VIIRS Burned Area Detection (VBD)
- **Coverage:** Thailand Regional & National Parks
- **Sensor:** VIIRS on Suomi NPP & NOAA-20 satellites
