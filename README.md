# HEALTHCARE ANALYSIS AND INSIGHTS
Data Cleaning:
1) Check for the number of missing values marked with '?' in each column of the “Medical Examinations” Table and "Hospitalization Details" Table.
NO OF "?" IN MEDICAL EXAMINATIONS	: 2 SYNTAX: =COUNTIF(MEDICAL_EXAMINATIONS,"?")		
NO OF "?" IN HOSPITALISATION DETAILS : 15 SYNTAX: =COUNTIF(HOSPITALISATION_DETAILS,"?")		

2) Fill in the missing values of ‘month’ with Sep and ‘year’ with its average rounded to thenearest integer.
For the Month column: created new column named month new and used if function for replacing "?" to "sep".
SYNTAX:=IF([@month]="?","sep",[@month])
 or replace all ? values with "Sep" using Find & Replace 
For the Year column: calcuted Average of Years using Average function(1982.8) SYNTAX:=AVERAGE(B:B)
Then round it to nearest integer.(1983)  SYNTAX:=ROUND(P4,0)
Then created new column named "Year New" and used "if" function for replacing "?" to "1983" or replace using Find & Replace

3) Determine the most frequently occurring values in the ‘smoker’, 'Hospital tier' and 'City tier' columns, and fill in the missing values accordingly.
For Smoker column: Found Mode (N0) using Syntax:
Then replaced "?" using Find & Replace
For 'Hospital tier' and 'City tier' columns: In power query used function groupby and found mode . Then replaced using "replace values". 

4) If any 'State ID' values are missing, consider filling them with 'Unknown' or using another appropriate strategy.
Replaced "?" with "unknown" using Replace values in power query.

Data Transformation: 
1) Split the ‘names’ column in the “Customer Names” Table into 3 meaningful columns: ‘Title’, ‘First Name’, and ‘Last Name’.
     Select the names column.Use Home > Split Column > By Delimiter > ",".This will create columns with can be named as ‘First Name’, and ‘Last Name’.Then again split column by delimiter "."   The column can be named as Title.


3) Convert the "NumberOfMajorSurgeries" column in the “Medical Examinations” Table to numerical data by replacing non-numeric characters with meaningful numerical values.
    Select the NumberOfMajorSurgeries column.Use Transform > Replace Values to replace "No major surgery " to "0".After replacements, change the column type to Whole Number.


4) Check for inconsistencies in the 'Heart Issues' and 'smoker' columns and propose
corrective actions if necessary.
5) Create a new column named “Weight Status” that categorizes BMI into different
categories as below:

BMI Weight Status
Below 18.5 Underweight
18.5 – 24.9 Normal Weight
25.0 – 29.9 Overweight
30.0 and Above Obesity

5) Create a new column named “Diabetes Status” and fill it as per the information given
below:

HbA1C Diabetes Status
Below 5.7 Normal
5.7 – 6.4 Prediabetes
6.5 and Above Diabetes

6) Merge ‘year’, ‘month’ and ‘date’ columns in the “Hospitalization Details” Table into one
column named ‘Date of Birth’ and format it in ‘DD-MMM-YYYY’ custom format.
7) Calculate the ‘Age’ of each customer based on their ‘Date of Birth’ and the date of
collection of the dataset, which is 8
th
June 2023.
8) Format ‘charges’ column as currency ($).
