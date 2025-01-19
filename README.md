# Crime-Data-Analytics
A crime data analysis project utilizing Apache Spark, Hadoop, and fairness-aware machine learning techniques to process large-scale datasets, ensure ethical insights, and achieve actionable results.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Results](#results)
6. [Technologies Used](#technologies-used)

---

## Introduction

This project applies Big Data tools and machine learning algorithms to analyze crime data on a large scale. It also addresses ethical considerations by integrating fairness evaluation techniques such as demographic parity and reweighting. The goal is to uncover crime patterns and provide actionable insights for policymakers while ensuring equity across demographic groups.

### Objectives:
- Perform scalable crime data analysis using Apache Spark and Hadoop HDFS.
- Clean and preprocess large datasets for reliable results.
- Develop predictive models using logistic regression.
- Evaluate and mitigate biases in the data using fairness-aware methods.
- Visualize findings for better interpretability.

---

## Features

- **Data Collection and Storage:** Crime data from NYC Open Data API, stored on HDFS.
- **Data Preprocessing:** Handles null values, duplicates, and inconsistent entries.
- **Analysis Tools:** Spark SQL and Pandas for exploratory and statistical analysis.
- **Machine Learning:** Logistic regression with a 93% accuracy rate for predictive modeling.
- **Fairness Evaluation:** Metrics such as demographic parity applied with bias mitigation techniques like reweighting.
- **Visualization:** Interactive and static plots to present insights.

---

## Installation

### Prerequisites
- Python (>=3.8)
- Apache Spark (>=3.0)
- Hadoop (>=3.2)
- Required Python libraries 

### Steps
1. **Clone the repository:**
   ```bash
   git clone https://github.com/nqasanova/Crime-Data-Analytics.git
   cd Crime-Data-Analysis

2. **Install Dependencies:**
   Install the required Python libraries by running:
   ```bash
   pip install pandas pyspark matplotlib seaborn
   
3. **Set Up Hadoop and Spark:**
   Follow the official documentation to configure Apache Hadoop and Apache Spark:
   - [Hadoop Setup Guide](https://hadoop.apache.org/)
   - [Apache Spark Documentation](https://spark.apache.org/)

4. **Download the Dataset:**
   - Download the NYC crime dataset from [NYPD Complaint Data Historic](https://data.cityofnewyork.us/resource/qgea-i56i.csv).
   - Split it into smaller chunks (if necessary) and upload them to your Hadoop Distributed File System (HDFS) under `/input/nypd_data/`.

---

## Usage

### Running the Pipeline

1. **Data Preprocessing:**  
   Run the notebook or code provided to fetch, clean, and preprocess the raw dataset into a usable format. Ensure the dataset is uploaded to the Hadoop Distributed File System (HDFS) under `/input/nypd_data/`.

2. **Perform Analysis:**  
   Use Spark SQL queries and Pandas-based scripts to explore the dataset, extract insights, and generate aggregated data. Specific functions for cleaning, filtering, and descriptive statistics are included in the notebook.

3. **Model Training and Evaluation:**  
   Use the provided logistic regression implementation in the notebook to predict crime patterns and evaluate fairness using metrics like demographic parity. Post-mitigation results can also be analyzed directly from the fairness evaluation module.

4. **Visualization:**  
   The notebook includes preconfigured cells for generating visualizations of the analysis results. These plots showcase trends in crime data, demographic patterns, and fairness metrics before and after mitigation.

---
## Results

### Key Findings
- **Crime Hotspots:** Brooklyn had the highest number of reported offenses, with Manhattan and Queens following.
- **Temporal Trends:** 
  - Fridays were the most crime-intensive days.
  - Crime activity peaked at **5:00 PM**.
  - December witnessed the highest number of crimes across years.
- **Demographic Insights:** 
  - Middle-aged individuals were most frequently affected.
  - Crimes were evenly distributed between male and female victims.
  - Specific crimes like *HARRASSMENT 2* and *PETIT LARCENY* were more common among middle-aged females.
- **Machine Learning Results:** 
  - Logistic regression achieved an accuracy of **93.52%**.
  - The model effectively predicted offense levels based on time, location, and demographic attributes.

### Fairness Evaluation
- **Pre-Mitigation Results:**
  - Significant bias was observed across demographic groups.
  - For the sensitive attribute "Sex," the disparity in demographic parity ranged from **8.52%** to **71.91%**.
  - For "Age," the disparity ranged from **16.92%** to **42.01%**.

- **Post-Mitigation Improvements:**
  - Disparity among "Sex" groups reduced from **63.39%** to **38.10%**.
  - Disparity among "Age" groups reduced from **25.09%** to **12.95%**.
  - Significant improvement in fairness without substantial loss in model accuracy.

### Visualizations
The following visualizations were created and analyzed:
1. **Crime Distribution by Borough:** Identified hotspots with Brooklyn leading.
2. **Temporal Trends:** Highlighted crime occurrences by year, month, day, and hour.
3. **Demographic Patterns:** Explored victim age and gender distribution.
4. **Fairness Metrics:** Comparison of fairness metrics before and after mitigation.

These findings and visualizations provide actionable insights for policymakers, law enforcement agencies, and researchers.

---

## Technologies Used

- **Big Data Frameworks:** Apache Spark, Hadoop HDFS
- **Programming Languages:** Python (PySpark, Pandas)
- **Machine Learning:** Logistic Regression 
- **Fairness Techniques:** Demographic Parity, Reweighting
- **Visualization Libraries:** Matplotlib, Seaborn
