# Thailand Fire Monitoring – VIIRS Nightfire & Burned Area Alerts

This repository automatically collects and publishes **wildfire detection alerts** for Thailand from the **Earth Observation Group (EOG), Colorado School of Mines** (VIIRS Nightfire & Burned Area Detection).

### 🔥 Fire Alert Types
| Dataset | Name | Description |
|--------|-----|------------|
| **VNF** | VIIRS NightFire | Detects thermal anomalies and fire using nighttime SWIR/LWIR |
| **VBD** | VIIRS Burned Area Detection | Detects burned area pixels from VIIRS |

### 🌏 Region Covered
- Thailand territory and border regions  
- Includes national parks, forest areas, agricultural zones

### 🛰 Satellite Sources
Source: **NOAA-20 & Suomi NPP VIIRS Sensors**  
Updated when new EOG data email alert arrives.

### 🗂 Folder Structure
YYYY/MM/DD/
vnf-YYYY-MM-DD.csv
vbd-YYYY-MM-DD.csv
vnf-YYYY-MM-DD.kmz
vbd-YYYY-MM-DD.kmz
vnf-map-YYYY-MM-DD.png
vbd-map-YYYY-MM-DD.png
