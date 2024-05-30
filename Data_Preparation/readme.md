Using Power Query Editor to transform and shape data to be ready for analysis. Various text and numerical transformations, including multiplication, rounding, and split and merge text columns, even more efficient in data preparation.
1. Why Clean Data in Power Query?
Garbage in, garbage out: Analysis quality depends on data quality.
Clean data characteristics:
No missing values (nulls).
No typos or errors.
No duplicates.
Relevant data only.
Outliers handled (capped or filtered).
Correct data types for calculations.
Short & descriptive column/table names.
Power Query for Data Preparation
Power Query: Data manipulation tool in Power BI.
Transformations: Applied one-by-one to clean data.
Shown as "applied steps" (cleaning recipe).
Saved in your "query" for data loading.
Data Types in Power Query

5 native data types:
Numbers
Date/Time
Text
Logical
Binary (base64 encoded, often for images)

Basic Data Structure Transformations
Transforming data structure (doesn't change data):
Promote headers (make first row column headers).
Change column order/sort.
Remove redundant columns/rows.
Rename columns for clarity.

Manual transformations:

Promote first row (if headers are in first row).
Remove top rows (e.g., to remove old column names).
Rename columns (double-click or right-click menu).
Reposition columns (drag and drop).
Sort data by column (click header arrow).


2. Data Preview features in Power Query
  2.1 Helps summarize key characteristics of your dataset.
  Used to identify and fix errors in your data.
Types of Data Previews:

Column Distribution:
Shows distribution of data with a histogram.
Useful for checking duplicate values.
Displays count of unique and distinct values.
Column Quality:
Checks for missing or error values.
Shows percentage of each type of value.
Column Profile (single column):
Displays detailed statistics (average, min, max, standard deviation).
Shows distribution and unique/distinct value count.
Benefits:

Find errors and inconsistencies.
See how transformations impact data.
Quickly summarize data and plan next steps.

  2.2 cleaning Data with Power Query Data Preview

Data Preview Features:

Column Distribution: Shows data distribution (histogram) and unique/distinct value counts.
Column Quality: Identifies missing or error values.
Cleaning Steps:

"Language" column:
All movies are English (1 distinct value).
Remove the column (inform users data is English-only).
"Color" column:
Missing data points (11).
Most values are the same.
Remove the column (inform users data is limited to Color movies).
"Movie_title" column:
Use Column Distribution to find duplicates.
Remove duplicates (keeps 91 unique movies).
"Duration" column:
Use Column Profile to find extreme values.
Filter out movies shorter than 60 minutes or longer than 4 hours.
"Title_year" column:
Use Column Profile to find incorrect values (pre-1895).
Replace incorrect values using value distribution chart (be cautious with replacements!).
Remember: It's generally better to make replacements in the source file, not Power Query.

3. What is clean text data?

Consistent formatting: No duplicates (USA vs United States)
Same capitalization: All lowercase or uppercase for each column
Trim extra characters: Remove leading/trailing spaces, punctuation, etc.
One piece of info per column: Split or combine columns if needed

Power Query Text Cleaning:
Transform > Text > Format:
  Capitalization: Standardize case (uppercase/lowercase) for each column.
Transform > Text > Trim & Clean: Apply to all text columns for better data:
  Trim: Removes leading/trailing spaces (extra blank space).
  Clean: Removes control characters (new lines, carriage returns).

Additional Features:
  Text.Replace: Replace specific characters or text with desired values.
  Text.Remove: Remove unwanted characters (punctuation, symbols).
  Text.Split: Split text into multiple columns based on delimiters (commas, tabs).
  Text.Combine: Combine multiple columns into a single column with a delimiter.
  
4.1 Numerical transformations in Power Query
  Clean data for accurate analysis:

No missing values or errors.
Consider outliers (advanced topic).
Mathematical transformations:

Absolute value (removes negative values).
Logarithmic (advanced, for exponential relationships).
Multiply or add a value to all observations.
Rounding (reduce decimal places, save memory).
Date/Time transformations (not numerical):

Extract specific properties (year, month).
Derived properties (start/end of year).
Extract age (from birth date).
