# Exploratory Data Analysis (EDA) - Vidio Dataset

This repository contains an Exploratory Data Analysis (EDA) of vidio dataset, specifically utilizing a 1% sampling of the total data. The goal of this analysis is to understand data relationships, handle missing values, and extract new insights through statistical descriptions and plots.

## Tools and Technologies
The following tools and libraries were used for this analysis:
* **Software**: Spreadsheet/Excel, Anaconda Navigator, Jupyter Notebook, and Tableau.
* **Core Libraries**: `pandas` (dataframe operations), `numpy` and `math` (mathematical operations).
* **Visualization**: `plotly`, `matplotlib`, and `seaborn`.

## Dataset Summary
The primary dataset used for this analysis has the following characteristics:
* **Total Rows**: 106,811 
* **Total Columns**: 41 
* **Data Types**: 33 object (string) columns, 3 boolean, 3 float, and 2 integer columns.
* **Key Features**: `hash_content_id`, `hash_play_id`, `hash_visit_id`, `is_login`, `playback_location`, `platform`, `play_time`, `end_time`, `average_bitrate`, `total_bytes`, and `play_duration`.

## Data Cleaning & Preprocessing
To prepare the data for analysis, the following steps were taken:
* **Error Handling**: Used `error_bad_lines=False` while reading the CSV to skip problematic lines that did not match the expected field count.
* **Handling Missing Values**: 
    * Identified columns with significant null counts (e.g., `hash_film_id`, `utm_source`, `city`).
    * Dropped columns with approximately 100,000 missing values to streamline the analysis (e.g., `city`, `utm_campaign`, `film_title`).
* **Duplicate Detection**: Checked for duplicate values across critical identifiers like `hash_play_id` (unique) and `referrer` (duplicated).

## Correlation Analysis
A correlation matrix was calculated for numerical columns to identify how variables influence one another[:
* **Strong Positive Correlation**: A high correlation of **0.81** was found between `total_bytes` and `play_duration`.
* **Negative Correlations**: Identified negative impacts between certain features, such as `has_ad` showing negative correlation with `is_login` (-0.23) and `total_bytes` (-0.15).
* **Visualization**: A heatmap was generated using the Seaborn library to provide a visual representation of these correlations.

## How to Run
1.  Ensure **Anaconda Navigator** and **Jupyter Notebook** are installed.
2.  Import the required libraries:
    ```python
    import pandas as pd
    import numpy as np
    import seaborn as sns
    import matplotlib.pyplot as plt
    ```
3.  [cite_start]Load the dataset and execute the EDA cells to view the statistical descriptions and visualizations.
