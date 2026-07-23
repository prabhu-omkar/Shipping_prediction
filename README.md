# Shipping Delay Prediction using PySpark

## Overview
This project uses Apache Spark (PySpark) and Machine Learning to predict whether an e-commerce shipment will arrive on time or be delayed. It processes historical shipping data and uses a Logistic Regression algorithm to calculate the probability of a delay based on various package and transit factors.

## Tech Stack
* **Language:** Python 3
* **Big Data Framework:** Apache Spark (PySpark)
* **Machine Learning:** PySpark MLlib
* **Environment:** Jupyter Notebook / Google Colab

## Dataset
The model trains on a dataset (`shipping.csv`) containing historical e-commerce shipping records. 
Key features analyzed include:
* `Warehouse_block`: The warehouse the item is shipped from.
* `Mode_of_Shipment`: Flight, Ship, or Road.
* `Product_importance`: Low, medium, or high.
* `Cost_of_the_Product`: The price of the item.
* `Discount_offered`: Discount percentage applied.
* `Weight_in_gms`: The weight of the package.

## Project Pipeline
1. **Data Loading & Cleaning:** Imports the CSV, formats column names to be Spark-compatible, and drops null values.
2. **Feature Engineering:** Converts categorical text data (like "Ship" or "Flight") into numerical indices using `StringIndexer`. Combines all features into a single array using `VectorAssembler`.
3. **Model Training:** Trains a `LogisticRegression` classification model to recognize patterns that lead to shipping delays.
4. **Prediction:** Evaluates new, unseen shipment data and outputs a `1.0` (On Time) or `0.0` (Delayed) alongside the exact probability percentages.

## How to Run
### Option 1: Cloud (Recommended)
The easiest way to run this project is via Google Colab, which bypasses local Java and Python environment configurations.
1. Upload `shipping.csv` to your Google Colab workspace.
2. Run `!pip install pyspark` in the first cell.
3. Execute the notebook cells in order.

### Option 2: Local Environment
If running locally on Windows, ensure you have the following configured:
1. Python 3.11 (PySpark currently has compatibility issues with Python 3.12).
2. Java Development Kit (JDK 17).
3. Set your `JAVA_HOME` and `PYSPARK_PYTHON` environment variables to point to your respective installations.                          