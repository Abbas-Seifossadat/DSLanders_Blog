# PySpark Code Examples

This file contains PySpark code examples demonstrating various data processing and machine learning tasks. The examples are designed to illustrate the capabilities of PySpark for handling large-scale data processing, real-time analytics, and machine learning in a distributed computing environment.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Dataset](#dataset)
- [Code Examples](#code-examples)
  - [Setting Up PySpark](#setting-up-pyspark)
  - [Basic Operations and Transformations](#basic-operations-and-transformations)
  - [Working with DataFrames](#working-with-dataframes)
  - [Machine Learning with PySpark](#machine-learning-with-pyspark)


## Introduction

This notebook provides PySpark code snippets demonstrating the following:
- Setting up a PySpark environment
- Performing basic operations and transformations on DataFrames
- Working with DataFrames for data manipulation
- Building a machine learning pipeline using PySpark's MLlib

These examples use a sample dataset of customer transactions and product details to showcase PySpark's capabilities.

## Getting Started

### Prerequisites

To run the PySpark code examples, you need the following:
- Python 3.x
- PySpark
- Jupyter Notebook

### Installation


1. Install PySpark using pip:
   ```bash
   pip install pyspark
   ```

2. (Optional) Set up a virtual environment to manage dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install Jupyter Notebook:
   ```bash
   pip install jupyter
   ```

## Dataset

The examples use a sample dataset of customer transactions (`transactions.csv`). The dataset contain the following columns:

- **transactions.csv**
  - `transaction_id`: Unique identifier for each transaction
  - `customer_id`: Unique identifier for each customer
  - `transaction_date`: Date of the transaction
  - `product_id`: Unique identifier for each product
  - `quantity`: Quantity of products purchased
  - `price`: Price of the product


## Code Examples

### Setting Up PySpark

The code snippet shows how to set up a PySpark environment and initialize a Spark session.

### Basic Operations and Transformations

The examples demonstrate loading data into a DataFrame, performing basic operations such as selecting columns, filtering rows, and grouping data.

### Working with DataFrames

These examples illustrate how to perform DataFrame transformations, including adding new columns, dropping columns, and renaming columns.


### Machine Learning with PySpark

The examples demonstrate building a machine learning pipeline using PySpark's MLlib, including feature engineering, splitting data into training and test sets, and training a linear regression model.