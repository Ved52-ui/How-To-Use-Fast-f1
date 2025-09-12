# Fast-F1 Usage Guide

Fast‑F1 is a Python library for accessing and analyzing Formula 1 data such as timing, telemetry, results, and weather. This guide shows you how to install, use, and explore Fast‑F1 effectively.
--------------------66--------6666666666


## 🚀 Installation

As of **September 5, 2025**, the latest release is **FastF1 3.6.1**.

### Using pip

```bash
pip install fastf1
```

> Requires **Python 3.9+**

### Using conda

```bash
conda install -c conda-forge fastf1
```

---

## ⚡ Getting Started — Basic Workflow

### 1. Import and Cache Setup

Fast‑F1 caches downloaded data for speed. Data is stored locally for reuse.

### 2. Load a Race Session

```python
from fastf1 import get_session

# Example: Qualifying at Monza 2025
session = get_session(2025, 'Monza', 'Q')
session.load()  # Downloads and prepares data
```

### 3. Access Data

```python
# Lap-by-lap timing per driver
laps = session.laps

# Telemetry data for a specific driver (e.g., Leclerc)
lec_tel = session.telemetry['LEC']

# Session results
results = session.results

# Weather information
weather = session.weather
```

### 4. Visualize Data

Use **Matplotlib** for plots:

* Telemetry overlays (e.g., speed vs time)
* Lap time comparisons
* Strategy curves and pit-stop analysis

All data is available as **Pandas DataFrames**, making it easy to analyze and plot.

---

## 📚 Resources & Examples

* **Official Documentation** → [docs.fastf1.dev](https://docs.fastf1.dev)
* **GitHub Repository** → [theOehrly/Fast-F1](https://github.com/theOehrly/Fast-F1)
* **Tutorials**

  * [Formula 1 Data Analysis with FastF1 (Medium)](https://medium.com/%40noviechiuman/formula-1-data-analysis-with-fastf1-%EF%B8%8F-d451b30f3a91)
  * [RacingDataLab Tutorials](https://www.racingdatalab.com/c02.php)

---

## 📝 Quick Cheat Sheet

| Task                 | Code Example                                                  |
| -------------------- | ------------------------------------------------------------- |
| Install              | `pip install fastf1` or `conda install -c conda-forge fastf1` |
| Load session         | `session = get_session(2025, 'Monza', 'R'); session.load()`   |
| View laps            | `session.laps.head()`                                         |
| Driver telemetry     | `session.telemetry['HAM']`                                    |
| Session weather info | `session.weather`                                             |
| Plot comparisons     | Use **Matplotlib** with Fast‑F1 DataFrames                    |

---

## 🎯 Bonus: Using Fast‑F1 via R

There’s also an R package **f1dataR** that leverages Fast‑F1 data.

### Install

```r
install.packages("f1dataR")
library(f1dataR)
```

### Examples

```r
# Load laps from the latest race
laps <- load_laps(season = "current", race = "last")

# Get driver color (for Alonso, 2024, round 3)
get_driver_color("ALO", season = 2024, round = 3)
```

> Note: `f1dataR` uses the **Jolpica‑F1 API** (as Ergast is being deprecated), with data sourced through Fast‑F1 via a Python bridge.

----

📌 **Start your F1 data journey today with Fast‑F1!** 🏎️
