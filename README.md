# ETL_Extract_ClaireMwarari_669470
A lab exercise for DSA 2040A, USIU Africa.

## Project Overview

This project demonstrates a basic ETL (Extract, Transform, Load) pipeline using Python and Jupyter Notebook. The main objective was to extract data from a source, apply necessary transformations, and load the processed data for further analysis or storage.

## LAB 3: Practicing Extraction in ETL

### Overview

This lab reinforces the understanding of both **Full Extraction** and **Incremental Extraction** concepts in ETL (Extract, Transform, Load) processes by applying them to a realistic dataset using a Jupyter Notebook.

---

### Steps Performed

1. **Full Extraction:**
   - The entire `custom_data.csv` dataset is loaded in **Section 1** of `etl_extract.ipynb`.
   - Basic statistics are displayed: number of rows, columns, and a sample preview.
   - The notebook prints:  
     `Extracted X rows fully.`

2. **Full Extraction:**
   - In **Section 2**, full extraction is implemented.

2. **Incremental Extraction:**
   - In **Section 3**, incremental extraction is implemented by simulating a "last extraction" time stored in `last_extraction.txt`.
   - Only new or updated records since the last extraction are loaded.

4. **Timestamp Management:**
   - After incremental extraction, the timestamp in `last_extraction.txt` is updated to reflect the most recent extraction time.

5. **Documentation:**
   - All steps are thoroughly documented within `etl_extract.ipynb` for clarity and reproducibility.

6. **Version Control:**
   - Git was initialized in the project folder.
   - A `.gitignore` file excludes files such as Jupyter checkpoints, Python cache, logs, SQLite DBs, and extraction timestamps.
   - All files were committed with a meaningful message and pushed to GitHub.

---

This lab demonstrates practical ETL extraction strategies, preparing the foundation for subsequent transformation and loading steps.

## Folder Structure

```
ETL_Extract_ClaireMwarari_669470/
├── etl_extract.ipynb         
├── custom_data.csv           
├── last_extraction.txt       
├── .gitignore                
└── README.md                 

```



## LAB 4: Transform in ETL

### Overview

In this lab, the ETL pipeline was extended to include a transformation phase. The goal was to apply meaningful data transformations to both the full and incremental datasets, thereby preparing the data for efficient loading and analysis. All changes and new files are tracked in the GitHub repository.

### Steps Performed

1. **Transformation Logic Implemented:**  
   The pipeline was updated to implement at least three distinct transformation techniques on both `transformed_full.csv` and `transformed_incremental.csv`.

2. **Transformation Techniques Used:**
   - **Cleaning:**  
     - Handled missing values in key columns by either imputing defaults or removing incomplete rows.
     - Removed duplicate records to ensure data integrity.
   - **Enrichment:**  
     - Added a calculated column, `total_price`, computed as `quantity * unit_price` for each order.
   - **Structural Transformation:**  
     - Standardized date formats in the `order_date` column to `YYYY-MM-DD` and ensured all data types matched the schema requirements.

3. **Notebook Updates:**  
   - Added **Section 4: Transform Full Data** and **Section 5: Transform Incremental Data** in `etl_extract.ipynb` to document and execute the transformation steps.

4. **Output Files:**  
   - Generated and saved the transformed datasets as `transformed_full.csv` and `transformed_incremental.csv` in the project directory.

5. **Repository Maintenance:**  
   - Updated `.gitignore` to exclude any new outputs or temporary files (`*.log` and `last_extraction.txt`) as needed.

---

This transformation stage ensures that the data is clean, enriched, and structurally consistent, facilitating accurate analysis and reliable loading into downstream systems.

## Folder Structure

```
ETL_Extract_ClaireMwarari_669470/
│
├── .gitignore
├── README.md
├── etl_extract.ipynb
├── last_extraction.txt
├── sales_data_large.csv
├── transformed_full.csv
└── transformed_incremental.csv
```



## Lab 5 – Load

### Overview

In this lab, the final step of the ETL pipeline—**Load**—was implemented. The goal was to load both transformed datasets into a structured, queryable format, preparing them for further analysis or integration. All steps and automation were performed using Jupyter Notebooks and the Python programming language.

---

### Steps Performed

1. **Project Structure Update:**
   - The project folder was extended to include:
     - `etl_load.ipynb`: A new notebook dedicated to the load process
     - `loaded_data/`: Directory for structured output files `full_data.db` and `incremental_data.db`

2. **Loading Targets:**
   - The transformed datasets were loaded into **SQLite databases** using the `sqlite3` library in Python.
   - The following schema was used for both database tables:
     ```sql
     CREATE TABLE full_data (
         id INTEGER PRIMARY KEY,
         customer_name TEXT,
         product TEXT,
         quantity INTEGER,
         unit_price REAL,
         total_price REAL,
         order_date TEXT
     );
     ```

3. **Notebook Automation:**
   - **Section 1: Load Setup** – Imported all necessary libraries and defined file paths for input and output.
   - **Section 2: Load Full Transformed Data** – Loaded `transformed_full.csv` into the `full_data` SQLite table.
   - **Section 3: Load Incremental Transformed Data** – Loaded `transformed_incremental.csv` into the `incremental_data` SQLite table.
   - **Section 4: Verification** – Previewed the loaded tables to ensure the data was accurately stored.

4. **.gitignore Update:**
   - Updated `.gitignore` to exclude output and intermediate files, such as:
     ```
     *.db
     loaded_data/
     ```

5. **Repository Maintenance:**
   - All relevant files and changes were pushed to GitHub to maintain a complete and reproducible lab record.

---

By completing this lab, the ETL pipeline was finalized with a robust loading step, ensuring all transformed data is stored in a structured, queryable format ready for downstream use.

## Folder Structure

```
ETL_Extract_ClaireMwarari_669470/
│
├── transformed_full.csv
├── transformed_incremental.csv
├── etl_extract.ipynb
├── etl_load.ipynb
├── loaded_data/
  ├── full_data.db
  └──incremental_data.db

```


## Author

Claire Mwarari  
Student ID: 669470

---

*This repository is part of the coursework for DSA 2040A at USIU Africa.*