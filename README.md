# Cell Morphology and Measurement Analysis Using Python

## Overview

This project analyzes cell measurements from a CSV dataset to investigate differences in cell size, perimeter, intensity, and identify potentially unusual cells.

The project was developed as a hands-on exercise in using **Pandas and Matplotlib for data analysis and visualization**.

## Dataset

The dataset contains measurements for 200 unique cells with the following features:

- `cell_id` – unique identifier for each cell
- `cell_type` – Type_A or Type_B
- `area` – measured cell area
- `perimeter` – measured cell perimeter
- `intensity` – measured cell intensity

## What I Did

### 1. Data Inspection
- Loaded the dataset using Pandas
- Examined the shape, columns, data types, and summary statistics
- Investigated missing values and duplicate records

### 2. Data Cleaning
- Removed a duplicate cell record
- Investigated missing measurements
- Corrected impossible negative measurements
- Investigated an extreme area value
- Tested circularity as a derived feature but removed it because the resulting values were not reliable for this dataset

### 3. Exploratory Data Analysis
Compared Type_A and Type_B cells using:
- Mean
- Median
- Standard deviation
- Distribution plots

### 4. Visualization

Created visualizations using Matplotlib, including:
- Histograms
- Boxplots
- Scatter plots

### 5. Correlation Analysis

Investigated relationships between:
- Area and perimeter
- Area and intensity
- Perimeter and intensity

The overall correlations were:

| Relationship | Correlation |
|---|---:|
| Area vs Perimeter | 0.634 |
| Area vs Intensity | 0.567 |
| Perimeter vs Intensity | 0.505 |

Correlations within Type_A and Type_B were much weaker, suggesting that the overall relationships were largely associated with differences between the two cell types.

### 6. Unusual Cell Investigation

One cell (`cell_id = 177`) had an intensity of **500**, which was clearly separated from the rest of the intensity distribution.

Its area and perimeter were not similarly unusual, so the value was retained as a **potential intensity outlier** rather than being automatically removed.

## Key Findings

- Type_B cells generally had larger area and perimeter than Type_A cells.
- Type_B cells generally showed higher intensity.
- Type_B measurements showed greater variation.
- Area and perimeter did not show any remaining extreme isolated values after cleaning.
- Cell 177 was identified as a potential intensity outlier.

## Tools Used

- Python
- Pandas
- Matplotlib
- NumPy (imported for future image-analysis work)

## Future Extension

The next stage of the project would be to work with actual microscope images.

The planned workflow is:

Microscope Image  
↓  
NumPy array  
↓  
Image processing and cell segmentation  with scikit-image
↓  
Extract cell measurements  
↓  
Pandas DataFrame  
↓  
CSV  
↓  
Analysis and visualization with Pandas and Matplotlib

## Project Status

**CSV-based analysis completed.**

The microscope-image analysis stage is planned as a future extension.
