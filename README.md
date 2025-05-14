# EV Route Planning Tool

The EV Route Planning Tool is a Python-based solution designed to assist electric vehicle (EV) drivers with intelligent route planning based on battery range, real-time charging station availability, and geolocation data.

This lightweight and modular tool combines open data APIs and smart logic to ensure EV users reach their destinations efficiently without running out of charge.

---

## Key Features

### 1. Battery-Aware Route Planning
- Calculates how far an EV can travel based on the current battery level.
- Dynamically updates routes to include optimal charging stops as needed.
- Ensures a buffer range is maintained, helping drivers avoid range anxiety.

### 2. Real-Time Charging Station Integration
- Uses the OpenChargeMap API to locate nearby charging stations.
- Provides station details such as:
  - Charger type (fast or normal)
  - Real-time availability
  - Location coordinates
- Filters stations based on minimal detour distance from the original route.

---

## How It Works: Algorithm Overview

1. Geocoding: Origin and destination addresses are converted to coordinates using the Geoapify API.
2. Route Retrieval: Optimal path is calculated using OSRM (Open Source Routing Machine).
3. Battery Monitoring: Continuously checks if the EV can reach the destination with current battery charge.
4. Charging Point Selection:
   - If charging is needed mid-route, nearby stations are fetched via OpenChargeMap.
   - Filters are applied for speed, type, and distance.
5. Route Visualization: An interactive map displays the complete journey, including any charging stops.

---
## Project Structure
```
EV_Route_Planning_Tool/
│
├── ev_route_planning.py # Main script containing the logic
├── requirements.txt # List of dependencies (API libraries, plotting, etc.)
└── README.md # Project documentation
```
---

## Requirements

- Python 3.10 or latest
- `requests`
- `folium` (for map visualization)
- Access to Geoapify and OpenChargeMap API keys
- Neccessary libraries are available in requirements.txt

Install dependencies using:
```bash
pip install -r requirements.txt
```
Run script:
```bash
streamlit run ev_route_planning.py
```
---

## LICENSE
This project is licensed under the MIT License.
