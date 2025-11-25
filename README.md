Data Leverager – Power Query ETL Project
Project Overview
This repository contains the Power BI .pbix file and supporting documentation for the "Data Leverager" ETL-only project. All steps are performed using Power Query, focusing on data extraction, cleaning, preparation, transformation, merging, aggregation, and basic profiling. No visualization or DAX formulas are included.

Sources Used
HTML Table (Web Extract):

Wikipedia country-wise GDP and COVID statistics table (sample source)

Sales Files:

Sales_Jan.xlsx, Sales_Feb.xlsx, Sales_Mar.xlsx (Monthly sales Excel files loaded from folder)

Employee File:

Employee.xlsx, containing EmployeeID, Name, Department, Region, Join Date

Transformations Applied
Data Extraction: Loaded data from web and folder-based Excel sources

Cleaning and Shaping:

Removed blank rows/columns

Promoted first row to headers

Renamed columns to meaningful names

Changed data types (using locale for currency/dates)

Filtered duplicates and null values

Text Tools: Applied UPPER, LOWER, TRIM, CLEAN, REPLACE, and SPLIT BY DELIMITER on customer/address fields

Numeric Tools: Rounded revenue to two decimals; added “Profit” as (Revenue – Cost)

Date & Time Tools: Extracted Day, Month, Year, Quarter, Fiscal Month; calculated Age from Birthdate

Conditional Columns & Indexing: Created “SalesCategory” (High, Medium, Low); added 0-based and 1-based index columns

Pivot/Unpivot: Pivoted monthly columns; unpivoted for normalized view

Merging & Appending: Merged sales with employee data (by Region or EmployeeID); appended all monthly sales

Grouping & Aggregation: Grouped by Region; computed total sales, average order value, transaction count

Profiling & Quality: Used Power Query Column Profile, Distribution, and Quality tools

Parameters & Source Settings: Configured dynamic folder path; managed source credentials for refresh

Refresh Simulation: Added new sales file (Sales_Apr.xlsx) and verified auto-refresh

Challenges Faced & Solutions
Challenge: Data type mismatches and locale issues on currency/date columns
Solution: Used “Change Type with Locale” and inspected error rows before type conversion.

Challenge: Address fields with inconsistent delimiters
Solution: Applied SPLIT BY DELIMITER and manual column inspection/cleanup.

Challenge: Monthly files with different column headers
Solution: Standardized header names before appending.

Challenge: Ensuring auto load/refresh with new files
Solution: Verified folder query setup and refreshed queries on adding new monthly files.

Challenge: Duplicates and missing values after merge
Solution: Used Table.Distinct and filtered by non-null keys before aggregation.

How To Use
Download the .pbix file from this repository.

Open in Power BI Desktop.

Examine transformations in Power Query Editor (Home > Transform Data).

Replace file paths, folder sources, or web tables as needed for your own data.

License
