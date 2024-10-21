# Wedge Project: Basic Data Engineering & ETL Processing 

## Project Overview
The Wedge Project is a comprehensive data engineering exercise centered around POS transaction data from the Wedge Co-op, a large cooperative grocery store in the Land of 10,000 Lakes. This project leverages Google BigQuery for managing and querying large datasets, and SQLite for building summary tables, with all functionality existing in the following Jupyter notebooks. The goal of this project is to apply core principles of the Extract-Transform-Load (ETL) process to build skills using real-world data and data formats for future analysis.

## Task Breakdown

### Task 1: Data Upload to BigQuery
- **File:** `Task-1-data-GBQ-upload.ipynb`
- **Description:** This notebook contains Python code to programmatically upload the transaction data to Google BigQuery, ensuring schema consistency and avoiding duplicate uploads. The data files were unzipped and uploaded sequentially, with error handling implemented to capture failed uploads.

### Task 2: Sampling Owner Transactions
- **File:** `Task-2-Sample-of-Owners.ipynb`
- **Description:** This notebook connects to BigQuery and extracts a random sample of owner transactions, excluding non-owners. The sample is written to a local text file for further analysis. The dataset can provides insights into how individual owners interact with the co-op over time, while existing as a manageable file size and random sample.

### Task 3: Building Summary Tables
- **File:** `Task-3-Building-Summary-Tables.ipynb`
- **Description:** This notebook processes the transaction data to create three summary tables stored in an SQLite database:
  - **Sales by Date by Hour**
  - **Sales by Owner by Year by Month**
  - **Sales by Product Description by Year by Month**
  
  These tables can be used to answer key business questions such as identifying popular products and sales trends. The department lookup table was also integrated to add department names to the product descriptions.

## Key Challenges & Learnings
- **Data Upload Issues:** Managing large datasets and handling schema inconsistencies were the main challenges in Task 1. Error logging and troubleshooting were essential in overcoming failed uploads to BigQuery.
- **Handling Data Type Inconsistencies:** Task 2 required careful handling of columns with inconsistent data types, which were excluded if deemed unnecessary for analysis.
- **Integrating Department Lookup:** In Task 3, ensuring that the department lookup table was correctly uploaded to BigQuery allowed for proper query joins between department numbers and names.

This project offered a valuable experience in tackling real-world data challenges and applying data engineering best practices. 
