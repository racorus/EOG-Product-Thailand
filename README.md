# Thailand Monitoring – VIIRS Nightfire & Boat Detections

This repository automatically collects and publishes detection alerts for Thailand from the Earth Observation Group (EOG), Colorado School of Mines.

## 🛰️ Alert Types

| Dataset | Name | Description |
|---|---|---|
| **VNF** | VIIRS NightFire | Detects thermal anomalies & active fire in Thailand National Parks using nighttime SWIR/LWIR. |
| **VBD** | VIIRS Boat Detections | Detects boats and offshore infrastructure in the Thailand Region using VIIRS nighttime DNB imagery. |

## 🌏 Region Covered
- Thailand territory and marine border regions.
- Includes national parks, forest areas, agricultural zones, and offshore regions.

## 🛰️ Satellite Sources
- **Satellites**: NOAA-20 (JPSS-1) & Suomi NPP — VIIRS Sensors
- **Update Frequency**: Automatically updated when a new EOG alert email arrives (runs every ~12 hours).

## 🗂️ Folder Structure
```text
EOG-Product-Thailand/
├── VNF/                        ← VIIRS Nightfire
│   └── YYYY/
│       └── MM/
│           └── DD/
│               ├── *.csv       ← Detection data (lat, lon, intensity, …)
│               ├── *.kmz       ← Google Earth overlay
│               └── *.png       ← Image from EOG alert email
│
├── VBD/                        ← VIIRS Boat Detections
│   └── YYYY/
│       └── MM/
│           └── DD/
│               ├── *.csv
│               ├── *.kmz
│               └── *.png
│
└── README.md
```

## 📥 How to Use

### Download a Specific Date
Browse to the folder for the date you need, for example:
- `VNF/2026/04/01/`
- `VBD/2026/04/01/`

### View in Google Earth
Download the `.kmz` file and open it directly in Google Earth Pro or Google Earth web.

### Analyze Detection Data
Download the `.csv` file — it contains columns such as latitude, longitude, detection time, radiant heat, and satellite pass information.

### Browse via the Data Viewer
Open `index.html` (via GitHub Pages) to easily browse all dates, download files, and preview CSV detection data in formatted tables.

## ⚙️ Data Pipeline
Emails from `eog@mines.edu` are monitored automatically via n8n:
1. Gmail receives VNF / VBD alert email from EOG.
2. n8n extracts the CSV and KMZ download links from the email body.
3. Files are downloaded and automatically uploaded to this repository under the correct `VNF/` or `VBD/` folder.
4. Images attached to the email are also saved alongside the data files.
5. The alert email is deleted from Gmail after a successful GitHub upload.

## 🔗 Data Source
- **Provider**: Earth Observation Group (EOG) — Colorado School of Mines
- **Products**: VIIRS Nightfire (VNF) & VIIRS Boat Detections (VBD)
- **Coverage**: Thailand Regional & National Parks
- **Sensor**: VIIRS on Suomi NPP & NOAA-20 satellites
