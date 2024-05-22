# Data Quality Scoring

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
