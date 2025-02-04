# Exercise 01: Exploring Narrow Transformations with PySpark
In this exercise, you will work with a dataset to explore and understand narrow transformations in PySpark. Narrow transformations are operations where each input partition contributes to only one output partition. Examples include `select`, `filter`, and `withColumn`.

You will be using the New York Taxi dataset, which contains detailed information about taxi trips in New York City. The goal is to perform various transformations on this dataset and observe their effects.

You will:
- Create a new column `surcharge_amount` containing a surcharge amount where the surcharge is 10%.
- Check if the trip is a long trip or not by adding a column `is_long_trip`, considering that a long trip is defined as having a trip distance greater than 10 miles.
- Add a column `trip_category` based on the number of passengers in the car, categorizing them into 'small group', 'medium group', and 'big group'. The group sizes are defined as follows:
    - `small group`: 1-2 passengers
    - `medium group`: 3-4 passengers
    - `big group`: 5 or more passengers
- Select trips made by VTS only and then select a subset of columns including `vendor_id`, `total_amount`, `surcharge_amount`, `trip_distance`, `is_long_trip`, `passenger_count`, and `trip_category`.

## Objectives

1. **Load the Dataset**: Load the New York Taxi dataset from the specified S3 path.
2. **Apply Transformations**: Perform narrow transformations such as `select`, `filter`, and `withColumn` on the dataset.
3. **Analyze Query Plans**: Use the `explain` method to understand the logical and physical plans generated by Spark for these transformations.
4. **Measure Performance**: Compare the performance of operations on partitioned and non-partitioned data.

## Instructions

1. **Setup the Environment**: 
    - Start an AWS Glue Interactive Session with the following configuration:
      ```python
      %idle_timeout 30
      %glue_version 5.0
      %worker_type G.1X
      %number_of_workers 4
      ```
2. **Load Data**: Load the New York Taxi dataset from the specified S3 path.
3. **Transform Data**: Apply transformations to create new columns like `surcharge_amount`, `is_long_trip`, and `trip_category`, and filter the dataset to include only VTS trips.
4. **Query Plans**: Use the `explain` method to analyze the query plans for your transformations.
5. **Performance Measurement**: Measure the time taken for operations on both partitioned and non-partitioned data and compare the results.

By the end of this exercise, you should have a deeper understanding of narrow transformations in PySpark and how to analyze and optimize your Spark jobs.
