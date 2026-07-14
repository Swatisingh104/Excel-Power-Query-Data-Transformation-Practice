# Excel-Power-Query-Data-Transformation-Practice
Hands-on Power Query practice covering data profiling, joins, transformations, and cleaning to prepare raw data for analysis.
Power Query Data Transformation – Practice Project
+ **📋 Table of Contents**

+ Overview
+ Objective
+ Why This Project Matters
+ Tools Used
+ Data Import & Profiling
+ Merging Queries (Joins)
+ Conditional Columns & Appending Tables
+ Transform vs. Add Column
+ Row & Column Operations
+ Column Management
+ Data Cleaning
+ Key Learnings
+ Skills Demonstrated
+ Real-World Relevance
+ Outcome


## 📌 Overview
This project is a structured, hands-on practice exercise in Microsoft Excel's Power Query Editor, built to develop a strong foundation in the data preparation process that sits behind every reliable dashboard, report, and analysis. Rather than jumping straight into a polished, pre-cleaned dataset, this project deliberately works through the full data-preparation lifecycle step by step — starting from raw, external data and ending with a clean, correctly structured, analysis-ready table.
The exercise is organized into a series of progressive mini-projects, each targeting a specific stage of the data preparation pipeline: profiling, joining, transforming, restructuring, and cleaning. Together, they mirror the real workflow an analyst follows before a single chart or KPI can be trusted.

##🎯 Objective
Raw data — whether pulled from an external table, an operational system, or a business report — is almost never ready for analysis in its original form. It typically contains:

Inconsistent or missing values
Duplicate records
Data spread across multiple related tables that need to be combined
Columns in the wrong format or data type
Unstructured date/time fields that need to be split or extracted

The objective of this project was to practice resolving all of these issues using Power Query's built-in toolkit — building the habit of assessing data quality before transforming it, and transforming it correctly before analyzing it.

 ##💡 Why This Project Matters
A dashboard or report is only as trustworthy as the data preparation behind it. Many data errors in real organizations don't come from bad analysis — they come from skipped or incorrect data preparation: a join that silently drops rows, a null value that gets miscounted, a column left as text when it should be a number. This project was built specifically to practice catching and avoiding those failure points, using the same tools and logic used in professional reporting environments.

## 🛠 Tools Used

Microsoft Excel
Power Query Editor
Merge Queries, Append Queries, Group By, Column Transformations, Data Type Management


## 🔍 1. Data Import & Profiling
Before any transformation was applied, the first step was understanding the data itself.

Imported external data into Power Query directly from a table/range.
Used Power Query's built-in profiling tools to review:

Column Distribution — how values are spread across a column, useful for spotting outliers or unexpected concentrations of a single value.
Column Profile — a statistical summary of each column (distinct values, unique values, error counts), used to quickly assess data health.
Column Quality — a breakdown of valid, error, and empty values per column, expressed as a percentage.



Why this step matters: Skipping profiling is one of the most common mistakes in data analysis — it leads to transformations being applied to data that looks clean but isn't. Profiling first means every decision made afterward (which columns to clean, which joins are safe, which values need handling) is based on evidence rather than assumption.

## 🔗 2. Merging Queries (Joins)
This section focused on combining data from multiple tables — one of the most frequently used and most error-prone operations in data preparation.

Practiced all major join types available in Power Query's Merge feature:

+ Inner Join — keeps only matching rows from both tables.
+ Left Outer Join — keeps all rows from the left table, with matches from the right where available.
+ Right Outer Join — keeps all rows from the right table, with matches from the left where available.
+ Left Anti Join — keeps only rows from the left table that have no match in the right table.
+ Right Anti Join — keeps only rows from the right table that have no match in the left table.
+ Full Outer Join — keeps all rows from both tables, matched where possible.


Explored a critical technical distinction between platforms: Power Query treats matching null values as equal during a join, meaning two null fields will match to each other. SQL Server, by contrast, does not treat null as equal to null — a null will never match another null in a SQL join condition.

Why this matters: This is a subtle but high-impact detail. If a dataset is joined in Power Query and later replicated in SQL Server (or vice versa) without accounting for this difference, the row counts and resulting numbers can silently change — with no error message to flag it. Understanding this difference is essential for anyone who works across both Excel/Power Query and database/SQL environments, since it directly affects data accuracy in cross-platform reporting.

## ➕ 3. Conditional Columns & Appending Tables

Added conditional (custom logic) columns — new columns whose values are generated based on defined if/then rules applied to existing data, similar to a nested IF function but built visually through the Power Query interface.
Practiced appending tables — first combining two tables into one, then extending the same logic to combine three tables, stacking rows from multiple sources into a single unified query.

Why this matters: Appending is different from merging — merging joins tables side-by-side based on a key, while appending stacks tables on top of each other when they share the same structure (e.g., monthly sales files that need to be combined into one yearly table). Knowing when to use which is a core data-preparation decision.

## 🔄 4. Transform vs. Add Column
One of the more nuanced concepts covered was the distinction between two similarly-named but functionally different tabs in Power Query:

Transform — modifies an existing column in place, overwriting its original values with the transformed version.
Add Column — creates a new column alongside the original, preserving the source data while adding the transformed result separately.

Applied Transform operations including:

Trimming extra leading/trailing spaces from text fields
Multiplying numeric values
Adding a fixed value to amount columns

Why this matters: Choosing Transform when Add Column was needed (or vice versa) can silently destroy source data that might be needed later for validation or audit purposes. Understanding this distinction is a small but important habit for maintaining data integrity throughout a workflow.

## ✂️ 5. Row & Column Operations

Removed the top N rows of a dataset directly from the Home tab — useful for stripping out header noise, title rows, or irrelevant leading rows before the actual data begins.
Split columns, including separating a combined date-and-time value into individual date and time columns — a common requirement since timestamp fields are often exported as a single combined column.
Grouped similar records (e.g., grouping rows by product type) using the Group By feature, producing summarized views such as counts or totals per category.

Why this matters: These operations are the building blocks of restructuring raw exports into analysis-friendly tables — removing noise, separating combined fields into usable components, and summarizing detail-level data into business-relevant groupings.

## 🧭 6. Column Management

Reordered and repositioned columns using the "Move To" options, to organize data in a logical, readable sequence.
Added an index column to assign a unique sequential identifier to each row — useful for tracking row order or creating a primary key.
Replaced specific values within a column, swapping out incorrect or inconsistent entries for standardized ones.
Converted combined date-time values into date-only format, and extracted date features — such as year, month, and day — using the Add Column tab, enabling time-based analysis (e.g., grouping by month or year).

Why this matters: Clean, well-organized, and properly typed columns are what make a dataset usable for Pivot Tables, charts, and further analysis — and date-feature extraction in particular is essential for any kind of trend or time-series reporting.

## 🧹 7. Data Cleaning

Removed duplicate rows, matched across all columns, to prevent double-counting in downstream analysis.
Removed and replaced null values, choosing an appropriate handling strategy depending on the context of the column.
Sorted data in ascending and descending order to support review and validation.
Added prefixes and suffixes to text values where standardization was needed (e.g., formatting IDs or labels consistently).
Reviewed and applied the correct data type for every column — text, whole number, decimal, date, etc. — to ensure accuracy in any calculations performed afterward.

Why this matters: Data cleaning is often the least visible but most important part of the process. A single incorrect data type or an unhandled null can cause formulas, aggregations, or downstream reports to silently return wrong numbers without any obvious error.

+ ## 🎓 Key Learnings

Data profiling should always come before transformation — assumptions about data quality are frequently wrong.
Join behavior is not universal across tools; the same logical operation (a join) can produce different results in Power Query versus SQL Server due to how each handles nulls.
"Transform" and "Add Column" look similar but serve different purposes, and the choice between them affects whether source data is preserved.
Clean, correctly-typed, and well-structured data is a prerequisite for any dashboard or report to be trustworthy — not an optional final step.

+ ## 🛠️ Skills Demonstrated
CategorySkillsData PreparationData Import, Column Profiling, Data Quality AssessmentData IntegrationMerge Queries (Inner, Left, Right, Full, Anti Joins), Append QueriesData TransformationConditional Columns, Transform Operations, Column Splitting, GroupingData StructuringIndex Columns, Column Reordering, Date Feature ExtractionData CleaningDuplicate Removal, Null Handling, Sorting, Data Type ManagementToolsMicrosoft Excel, Power Query Editor

+ ## 🌍 Real-World Relevance
The techniques practiced in this project reflect the exact preparation work required before any business report, KPI dashboard, or data-driven decision can be trusted — cleaning inconsistent source data, correctly combining information from multiple systems, and ensuring every column is structured and typed correctly. These are foundational skills for any data analyst role that involves working with raw exports, multi-source datasets, or recurring reporting cycles.

+ ##  ✅ Outcome
By the end of this project, I was comfortable using Power Query to take raw, multi-source, and inconsistently formatted data and transform it into a clean, correctly typed, properly joined, and analysis-ready dataset — the foundational step behind every reliable report or dashboard.
