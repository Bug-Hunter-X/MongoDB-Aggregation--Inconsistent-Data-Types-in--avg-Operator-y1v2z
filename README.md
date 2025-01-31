# MongoDB Aggregation Error: Handling Inconsistent Data Types

This repository demonstrates a common issue in MongoDB aggregation pipelines: errors caused by inconsistencies in data types within fields used in aggregation operations (like `$avg`).

The `bug.js` file contains an aggregation pipeline that attempts to calculate the average age of users older than 25, grouped by city.  However, if the `age` field doesn't consistently contain numbers (e.g., it might sometimes contain strings), the `$avg` operator will fail.

The `bugSolution.js` file offers a solution using the `$type` operator to filter out documents with incorrect data types before performing the aggregation. This ensures the `$avg` operator only works on valid numerical data, preventing errors and producing accurate results.

This example highlights the importance of data validation and consistent data types when working with MongoDB aggregation pipelines.