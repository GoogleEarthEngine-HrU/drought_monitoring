# 🌾 Drought Severity Monitor (Google Earth Engine + Python)

An interactive tool for monitoring **drought severity** using **MODIS NDVI and LST** datasets, integrated with **Google Earth Engine (EE)**, **geemap**, and **Jupyter widgets**.

## ✨ What it does
- Select a **country and regions** (Ethiopia, Kenya, Somalia, Sudan).
- Choose drought indices: **VCI**, **TCI**, **VHI**.
- Set a **time period** (years and months).
- Classify drought severity into **Extreme, Severe, Moderate, Mild, Normal**.
- **Visualize** the map interactively and **export** results to Google Drive.

## 🗂 Project structure
    ### requirements.txt # Python dependencies
    ### LICENSE # MIT license
    ### README.md # This file
    ### drought_monitor_app.ipynb


## ⚙️ Installation
```bash
git clone https://github.com/GoogleEarthEngine-HrU/drought_monitoring.git
cd drought_monitoring
pip install -r requirements.txt

🔑 Earth Engine setup

In a Python session / Jupyter cell:

import ee
ee.Authenticate()
ee.Initialize(project='ee-mussamahammed1', opt_url='https://earthengine-highvolume.googleapis.com')

▶️ Usage

Open the notebook and run the cells to launch the UI:

Select Area: choose country and one/more regions.

Select Parameters: pick VCI, TCI, or VHI.

Set Date Range: start/end year and month.

Click Analyze to render the classification map.

The script starts a Drive export to GEE_Exports/.

Indices & classes used

VCI: scaled NDVI (0–100)

TCI: scaled LST (0–100, inverted so higher = cooler)

VHI: 0.5 × VCI + 0.5 × TCI

Index	  Extreme	  Severe	  Moderate	  Mild	  Normal
VCI	    0–10	    10–20	    20–30	      30–40	  40–100
TCI	    0–10	    10–20	    20–30	      30–40	  40–100
VHI	    0–15	    15–25	    25–35	      35–45	  45–100

🗺 Data sources

MODIS NDVI: MODIS/061/MOD13A2

MODIS LST: MODIS/061/MOD11A2

Boundaries: FAO/GAUL_SIMPLIFIED_500m/2015/level1

📤 Export

The mean drought class image for the selected regions is exported to Google Drive:

GEE_Exports/
  <INDEX>_<COUNTRY>_<STARTYEAR>_<ENDYEAR>.tif

🛠 Troubleshooting

If widgets don’t show, ensure:

jupyter nbextension enable --py widgetsnbextension


If EE authentication fails, run ee.Authenticate() in a clean cell and ensure browser pop-ups are allowed.

If the map is blank, check that your date range has data and regions match the GAUL names.

📄 License

This project is open-source under the MIT License.

🙋‍♂️ Author

Mohammed Mussa Abdulahi
PhD Researcher – Biodiversity Management and Climate Change
📧 mohammed.mussa@haramaya.edu.et


Copy and paste your Earth Engine UI script into the GEE Code Editor, or run the provided Jupyter notebook for the interactive app.
