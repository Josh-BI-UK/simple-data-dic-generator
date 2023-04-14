# Simple Data Dictionary Generator

## Project Aim
Hobby project to create a simple Python script that can be used to create basic data dictionaries for ETL/DW projects.


## What does the code do?

This Python script analyses a "source CSV" file and provides basic data analysis information for each field.

It is then possible to download and parse the summary table (in JSON format) into Excel and create a standard table from it. The goal is to develop a simple method for creating the foundation of a data dictionary for data warehouse and ETL projects.

<br>

### The summary table contains the following columns:

<br>

1. **Column Name:** Name of a column (i.e. header) within the "source CSV" file.

2. **Sample Data:** A list of values, (a maximum of ten values), randomly sampled from within a column.  Each value should be separated by a semicolon.

3. **Min Value:** Minimum value within a column, only if the data type is "Number" or "Date", else for any other data type state "n-a". If all values within the column are nulls, then state "n-a".

 4. **Max Value:** Maximum value within a column, only if the data type is "Number" or "Date", else for any other data type state "n-a". If all values within the column are nulls, then state "n-a".

 5. **Data Type:** Using basic data types to analyse all of the values within a column. Data types and mappings to Python-style data types are as follows:

    - Unicode values: "Text"
    - String or text values: "Text"
    - Mixed numerical and non-numerical values: "Text"
    - Date and time values: "Date"
    - Integer numbers: "Number"
    - Floating point numbers: "Number"
    - True/False values: "Boolean"
    - Column with all NULLs: "All Nulls"

<br>

6. **Max Character Length:** If data type is "Text", the length of the shortest string value in a column, else for any other data type state "n-a". If all values within the column are nulls, then state "n-a".

7. **Min Character Length:** If data type is "Text", the length of the shortest string value in a column, else for any other data type state "n-a". If all values within the column are nulls, then state "n-a".

8. **% NULL Fields:** Percentage of values which are nulls within a column, formatted to two decimal places. If no nulls are present, state 0%.

9. **NULL field count:** Count of values which are NOT nulls within a column.

10. **Not NULL field count:** Count of values which are nulls within a column.

11. **Count of Unique Values:** Count unique values within a column. If all values are null, then state "n-a".

<br>

### The code should implement the following requirements:

a) Each row of the "output" table should represent one column from the source CSV.

b) For data sets with more than 400,000 rows (this figure can be changed via the variable 'MAX_ROWS'), the analysis will be based on a random sample, equal to MAX_ROWS (default = 400k rows).

c) The "output" JSON can be easily parsed as a table.
