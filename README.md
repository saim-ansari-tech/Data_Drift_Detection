# Weather Data Drift Detection Using PSI and Weighted Reference Strategy

## Overview

This project focuses on detecting and simulating data drift in weather datasets using statistical techniques.

The project contains two tasks:

- **Task_2:** Detects data drift between a baseline weather dataset and a drifted weather dataset using the Population Stability Index (PSI).
- **Task_3:** Implements a Weighted Reference Drift Strategy by combining original and drifted datasets with a defined ratio to create a new reference dataset.

For Task_2, drift is detected by comparing the feature distributions of the original dataset and the drifted dataset. PSI scores are calculated for numerical features, and visualizations are generated to understand the magnitude of drift.

For Task_3, a weighted reference dataset is created by combining:
- 70% drifted data
- 30% original data

The generated dataset represents a partially adapted reference distribution that can be used for further drift analysis.

---

# Task_2: PSI-Based Data Drift Detection

## Features

* Population Stability Index (PSI) implementation from scratch
* Data drift detection for numerical features
* Drift severity classification:
  * No Drift
  * Moderate Drift
  * Significant Drift
* Distribution comparison using histograms
* PSI bin proportion visualization
* Object-oriented implementation using a `DataDrift` class
* Code quality checks using Flake8

---

## Dataset Features

The following numerical weather features are analyzed:

* Temperature_C
* Humidity_pct
* Precipitation_mm
* Wind_Speed_kmh

---

## PSI Thresholds

| PSI Value   | Interpretation |
| ----------- | -------------- |
| < 0.10      | No Drift |
| 0.10 - 0.25 | Moderate Drift |
| > 0.25      | Significant Drift |

---

# Task_3: Weighted Reference Drift Strategy

## Overview

Task_3 implements a weighted reference strategy for creating a new reference dataset.

Instead of using only the original dataset as a baseline, the strategy combines original and drifted data using weighted sampling.

The generated dataset contains:

- 70% samples from the drifted dataset
- 30% samples from the original dataset

This approach creates a reference dataset that partially reflects the new data distribution while still maintaining information from the original baseline.

---
### Project Structure

---

## Task_3 Output

The process:

1. Loads the original weather dataset.
2. Loads the drifted weather dataset.
3. Selects samples according to the defined weights.
4. Combines both datasets.
5. Saves the generated weighted reference dataset as a CSV file.

---

# Project Structure

```text
project_folder/
│
├── Task_2/
│   │
│   ├── data/
│   │   ├── weather_data.csv
│   │   └── weather_drifted_data.csv
│   │
│   ├── src/
│   │   └── task2.py
│   │
│   └── .github/
│       └── workflows/
│           └── flake8.yaml
│
├── Task_3/
│   │
│   ├── data/
│   │   ├── weather_data.csv
│   │   ├── weather_drifted_data.csv
│   │   └── weighted_reference_data.csv
│   │
│   └── src/
│       └── task3.py
│
├── requirements.txt
└── README.md

The final reference dataset is generated as:
