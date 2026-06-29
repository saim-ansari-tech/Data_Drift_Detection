# Weather Data Drift Detection Using PSI

## Overview

This project detects data drift between a baseline weather dataset and a current weather dataset using the Population Stability Index (PSI).

The project simulates drift by modifying selected features in the original dataset and then compares the distributions of both datasets. PSI scores are calculated for numerical features, and visualizations are generated to help understand the extent of the drift.

---

## Features

* Population Stability Index (PSI) implementation from scratch
* Data drift detection for numerical features
* Drift severity classification

  * No Drift
  * Moderate Drift
  * Significant Drift
* Distribution comparison using histograms
* PSI bin proportion visualization
* Object-oriented implementation using a `DataDrift` class
* Code quality checks using Flake8

---

## Dataset Features

The following numerical features are analyzed:

* Temperature_C
* Humidity_pct
* Precipitation_mm
* Wind_Speed_kmh

---

## PSI Thresholds

| PSI Value   | Interpretation    |
| ----------- | ----------------- |
| < 0.10      | No Drift          |
| 0.10 - 0.25 | Moderate Drift    |
| > 0.25      | Significant Drift |

---

## Project Structure

```text
project_folder/
│
├── data/
│   ├── weather_data.csv
│   └── weather_drifted_data.csv
│
├── src/
│   └── task2.py
│
├── .github/
│   └── workflows/
│       └── flake8.yaml
│
├── requirements.txt
└── README.md
```

### Directory Description

* **data/**
  Contains the baseline and drifted weather datasets.

* **src/**
  Contains the source code for PSI calculation, drift analysis, and visualization.

* **.github/workflows/**
  Contains the GitHub Actions workflow used to automatically run Flake8 checks on every push and pull request.

* **requirements.txt**
  Lists the project dependencies.

* **README.md**
  Project documentation and usage instructions.


---

## Installation

Create and activate a virtual environment:

```bash
python -m venv .venv
```

Activate the environment:

### Windows

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Project

```bash
python task2.py
```

The script will:

1. Load baseline and drifted datasets.
2. Calculate PSI for each numerical feature.
3. Classify drift severity.
4. Generate distribution comparison plots.
5. Generate PSI bin proportion plots.

---

## Example Output

```text
DATA DRIFT REPORT

Feature: Temperature_C
PSI: 0.8421
Status: Significant Drift

Feature: Humidity_pct
PSI: 0.3567
Status: Significant Drift
```

---

## Dependencies

* pandas
* numpy
* matplotlib

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

## Author

Developed as part of a data drift detection internship project.
