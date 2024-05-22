# Data Quality Scoring Tool

## Overview

The goal of this project is to create a versatile tool that can be fed various types of datasets and score them based on their quality. This tool, implemented in the `test_data_quality` function, uses the Great Expectations library to validate and score datasets according to predefined expectations.

## Features

-   **Versatile Data Quality Checks**: Capable of handling different types of datasets including those with ID columns, categorical columns, numeric columns, and date columns.
-   **Configurable Expectations**: Allows setting expectations such as non-null values, uniqueness, length constraints, type checking, and date parseability.
-   **Scoring Mechanism**: Scores datasets based on the number of expectations met versus the total expectations.
-   **Export Functionality**: Option to export rows that failed expectations to a CSV file for further inspection.

## Usage

### Function Definition

```python
def test_data_quality(df, dq_name, id_columns=[], categorical_columns=[], numeric_columns=[], date_columns=[], strictness=0.85, export=False):
```

### Parameters

-   **df**: The dataframe to be tested.
-   **dq_name**: The name for the data quality suite.
-   **id_columns**: List of ID columns.
-   **categorical_columns**: List of categorical columns.
-   **numeric_columns**: List of numeric columns.
-   **date_columns**: List of date columns.
-   **strictness**: The threshold for the expectations (default is 0.85).
-   **export**: Flag to export failed rows to CSV (default is False).

### Running the Function

1. **Initialize the Great Expectations Context**: Ensure you have a valid Great Expectations context.
2. **Create Batch Request**: Generate a batch request for the dataframe.
3. **Initialize Validator**: Initialize the validator with the batch request and expectation suite.
4. **Define Expectations**: Set expectations for ID, categorical, numeric, and date columns.
5. **Test Expectations**: Apply the expectations to the respective columns.
6. **Calculate Score**: Compute the quality score based on the expectations met.
7. **Export Failures**: Optionally export the rows that failed expectations to a CSV file.

## Datasets Used

The function has been tested on the following datasets:

1. **Energy Usage Dataset**
2. **Madrid Housing Dataset 1**
3. **Madrid Housing Dataset 2**
4. **Melbourne Housing Dataset**

Each dataset provided insights into different data quality aspects and helped refine the expectations used in the function.

## Useful expectations

### General expectations

-   `expect_column_to_exist(column_name)`: Checks if the specified column exists in the dataset.
-   `expect_table_row_count_to_be_between(min_value, max_value)`: Checks if the number of rows in the dataset is within the specified range.
-   `expect_column_to_be_of_type(column_name, column_type)`: Checks if the specified column has the expected data type.
-   `expect_column_values_to_not_be_null(column_name)`: Checks if the specified column contains any null values.
-   `expect_column_values_to_be_unique(column_name)`: Checks if all values in the specified column are unique.
-   `expect_column_values_to_be_in_set(column_name, value_set)`: Checks if all values in the specified column are present in the given value set.
-   `expect_column_distinct_values_to_be_in_set(column_name, value_set)`: Checks if the distinct values in the specified column are present in the given value set.
-   `expect_column_pair_values_to_be_in_set(column_A, column_B, value_set)`: Checks if the pair of values in the specified columns are present in the given value set.
-   `expect_column_value_lengths_to_be_between(column_name, min_value, max_value)`: Checks if the length of the values in the specified column is within the specified range.
-   `expect_column_values_to_be_dateutil_parseable(column_name)`: Checks if the values in the specified column can be parsed by the dateutil library.

### Numerical columns

-   `expect_column_values_to_be_between(column_name, min_value, max_value)`: Checks if all values in the specified column are within the specified range.
-   `expect_column_mean_to_be_between(column_name, min_value, max_value)`: Checks if the mean of the values in the specified column is within the specified range.
-   `expect_column_median_to_be_between(column_name, min_value, max_value)`: Checks if the median of the values in the specified column is within the specified range.
-   `expect_column_min_to_be_between(column_name, min_value, max_value)`: Checks if the minimum value in the specified column is within the specified range.
-   `expect_column_max_to_be_between(column_name, min_value, max_value)`: Checks if the maximum value in the specified column is within the specified range.
-   `expect_column_values_to_be_increasing(column_name)`: Checks if the values in the specified column are in increasing order.
-   `expect_column_values_to_be_decreasing(column_name)`: Checks if the values in the specified column are in decreasing order.
