# DataLake-Spark-Scala

## Overview

This repository provides a set of Scala scripts for managing data in a Data Lake environment using Apache Spark. The scripts include methods for pulling data from MySQL or other databases, creating and managing staging and curated tables, and optimizing data storage and processing.

## Repository Contents

### Key Features

1. **Data Extraction**
   - **Description**: Methods to pull employee table data from MySQL or any other database under the `empoffice` schema. The scripts handle data extraction efficiently using Spark.

2. **Staging Tables**
   - **Description**: In the `retailstg` database, temporary managed tables are created to stage the imported data. These tables are dropped and recreated on a daily basis, ensuring that the data is cleaned and refreshed each day. This approach eliminates the need for separate data cleanup operations.

3. **External Tables**
   - **Description**: In the `retail_curated` database, external tables are created and partitioned to facilitate efficient querying and data management. These tables are bucketed to improve join operations with other external tables. By using external tables, data is retained for iterative queries and further processing without being dropped.

### How It Works

1. **Data Extraction**:
   - Scripts pull data from the `empoffice` schema in the specified database (e.g., MySQL). This data is then prepared for further processing in Spark.

2. **Staging Data Management**:
   - Temporary managed tables are created in the `retailstg` database. These tables are designed to handle daily data loads, ensuring that each day's data is fresh and clean. The tables are dropped and recreated each day.

3. **Curated Data Management**:
   - External tables are created in the `retail_curated` database with partitioning and bucketing strategies. Partitioning allows for efficient querying by applying filters, while bucketing improves performance for join operations. These tables are used to store data persistently and support iterative queries.

### Getting Started

1. **Set Up the Environment**:
   - Ensure Apache Spark is installed and configured in your environment. Set up the MySQL or other databases as required.

2. **Run Data Extraction Scripts**:
   - Execute the provided Scala scripts to pull data from the `empoffice` schema and load it into Spark for processing.

3. **Create and Manage Staging Tables**:
   - Use the scripts to create and manage temporary tables in the `retailstg` database. These tables will be automatically refreshed daily.

4. **Create and Manage External Tables**:
   - Use the scripts to create external tables in the `retail_curated` database. Configure partitioning and bucketing as needed to optimize data queries and joins.

### Repository Structure

- **DataExtraction.scala**
  - Methods for extracting employee data from MySQL or other databases.

- **StagingTables.scala**
  - Scripts for creating and managing temporary managed tables in the `retailstg` database.

- **ExternalTables.scala**
  - Scripts for creating and managing external tables in the `retail_curated` database, including partitioning and bucketing configurations.

Feel free to explore and adapt the scripts to your specific Data Lake environment. If you have any questions or encounter issues, please open an issue in this repository.

Happy data processing!

---

This README provides a clear description of the repository’s features and functionality, guiding users through the setup and usage of the provided Scala scripts for managing data in a Data Lake environment.
