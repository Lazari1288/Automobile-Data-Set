# Data-Wrangling
Data Wrangling is the process of converting data from the initial format to a format that may be better for analysis.

### In this project I want to predict the price of cars
I downloaded a raw csv file. I identified  all the missing values.
First I converted "?" to NaN which is Python's default missing value marker, for reasons of computational speed and convenience. Here I used the function:
.replace(A, B, inplace = True) 
to replace A by B
Then I used .isnull() function to output True when is missing and False when is not missing.Using a for loop in Python I can quickly figure out the number of missing values in each column.  Each column has 205 rows of data, with seven columns containing missing data:

1."normalized-losses": 41 missing data
2."num-of-doors": 2 missing data
3."bore": 4 missing data
4."stroke" : 4 missing data
5."horsepower": 2 missing data
6."peak-rpm": 2 missing data
7."price": 4 missing data
### Deal with missing data
1. Drop data 
    a. drop the whole row
    b. drop the whole column
2. Replace data
    a. replace it by mean
    b. replace it by frequency
    c. replace it based on other functions

Whole columns should be dropped only if most entries in the column are empty.
### Replace by mean:

"normalized-losses": 41 missing data, replace them with mean
"stroke": 4 missing data, replace them with mean
"bore": 4 missing data, replace them with mean
"horsepower": 2 missing data, replace them with mean
"peak-rpm": 2 missing data, replace them with mean
### Replace by frequency:

"num-of-doors": 2 missing data, replace them with "four".
### Drop the whole row:

"price": 4 missing data, simply delete the whole row
### Correct data format

The last step in data cleaning is checking and making sure that all data is in the correct format (int, float, text or other).
I used:
**.dtype()** to check the data type
**.astype()** to change the data type
### Data Standardization
Data is usually collected from different agencies with different formats. (Data Standardization is also a term for a particular type of data normalization, where we subtract the mean and divide by the standard deviation.

What is Standardization?

Standardization is the process of transforming data into a common format which allows the researcher to make the meaningful comparison.

Transform mpg to L/100km:
In my dataset, the fuel consumption columns "city-mpg" and "highway-mpg" are represented by mpg (miles per gallon) unit.
I will need to apply **data transformation** to transform mpg into L/100km
The formula for unit conversion is L/100km = 235 / mpg
### Data Normalization
Why normalization?

Normalization is the process of transforming values of several variables into a similar range. Typical normalizations include scaling the variable so the variable average is 0, scaling the variable so the variable variance is 1, or scaling the variable so the variable values range from 0 to 1.
Example

To demonstrate normalization, I want to scale the columns "length", "width" and "height"
**Target:**   Normalize those variables so their value ranges from 0 to 1.
**Approach:** Replace origianl value by (original value)/(maximum value)
### Binning
Why binning?

Binning is a process of transforming continuous numerical variables into discrete categorical 'bins' for grouped analysis.
Example: 

In  dataset, "horsepower" is a real valued variable ranging from 48 to 288, and it has 57 unique values. 
I will use the Pandas method 'cut' to segment the 'horsepower' column into 3 bins.
### Indicator variable (or dummy variable)
What is an indicator variable?
An indicator variable (or dummy variable) is a numerical variable used to label categories. They are called 'dummies' because the numbers themselves don't have inherent meaning.

Example
The column "fuel-type" has two unique values, "gas" or "diesel". Regression doesn't understand words, only numbers. To use this attribute in regression analysis, I convert "fuel-type" into indicator variables. I will use the panda's method 'get_dummies' to assign numerical values to different categories of fuel type.
#### Finnaly save the new csv

