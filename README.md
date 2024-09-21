# Crowdfunding ETL Project

## Overview
This project demonstrates an Extract, Transform, and Load (ETL) process by using Python and Pandas. The project involved extracting data from Excel files, transforming it into cleaner CSV files, and loading the data into a PostgreSQL database. The goal was to automate the process of structuring our data from raw crowdfunding data to be ready to be stored and analyzed in a SQL database.

## Project Structure
The project was divided into the following steps:

**Extracting Data:** Extracted data from Excel files (crowdfunding.xlsx and contacts.xlsx).
**Transforming Data:** Used Pandas and Python to clean and transform the data into the necessary structure for database storage. The data was then separated into categories, subcategories, campaigns, and contacts.
**Loading Data:** Exported the transformed data into four CSV files and uploaded them into a SQL database.

## Crucial Files in Repository
- **ETL_Mini_Project_QDaley, ODiakite, KHer.ipynb:** The main Jupyter Notebook where all data extraction, transformation, and loading processes are executed.
- **crowfunding_db_shema.sql:** The SQL schema file containing the database structure for the crowdfunding database.
- **Resources Folder:** Contains the Excel files (crowdfunding.xlsx and contacts.xlsx) for extracting and transforming the data.

## Process
### 1. Extract Data
- The data was extracted from the provided Excel files:
  - crowdfunding.xlsx contained information on crowdfunding campaigns.
  - contacts.xlsx contained contact information for those involved in the campaigns.
    
### 2. Transform Data
Data transformation was split into several components:

**Category and Subcategory DataFrames**
- The categories and subcategories were extracted from the category column in crowdfunding.xlsx and split into separate columns.
- Unique IDs were then assigned for categories (category_id) and subcategories (subcategory_id).

**Campaign DataFrame**
- Campaign data was extracted and cleaned. Specific transformations include:
  - Conversion of goal and pledged columns to float data types.
  - UTC conversion of launched_at and deadline columns to datetime format.
  - Creation of unique category_id and subcategory_id based on the transformed data.

**Contacts DataFrame**
- Contact details were extracted from the contacts.xlsx file and reorganized into a pandas dataframe 

### 3. Load Data
- The transformed data was exported into the following CSV files:
  - category.csv
  - subcategory.csv
  - campaign.csv
  - contacts.csv
-After exporting, these CSV files were uploaded into a SQL database using the schema provided in the crowdfunding_db_schema.sql file.

### 4. Database Creation
- Use the SQL schema file to create the necessary tables in a PostgreSQL database.
- Import the CSV files into the corresponding tables and verify the import by running SELECT statements.
