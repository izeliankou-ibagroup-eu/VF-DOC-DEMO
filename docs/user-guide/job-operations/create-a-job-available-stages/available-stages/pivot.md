Pivot Stage.
The Pivot stage has two operation types:

* Pivot
* Unpivot

*Pivot* function rotates data from one column into multiple columns (transpose a row to a column).
With aggregation one of the grouping column values is transposed into individual columns with distinct data.

| Product | Amount | Country |
| :--- | :--- | :--- |
| Banana | 1000 | USA |
| Carrots | 1500 | USA |
| Beans | 1600 | USA |
| Orange | 2000 | USA |
| Orange | 2000 | USA |
| Banana | 400 | China |
| Carrots | 1200 | China |
| Beans | 1500 | China |
| Orange | 4000 | China |
| Banana | 2000 | Canada |
| Carrots | 2000 | Canada |
| Beans | 2000 | Mexico |

From the above dataframe, to get the total amount exported to each country of each product we group by Product,
pivot by Country and sum the Amount. This transposes the countries from the dataframe rows into columns and pro-
duces the below output. Missing data is represented as Null.

| Product | Canada | China | Mexico | USA |
| :--- | :--- | :--- | :--- | :--- |
| Orange | Null | 4000 | Null | 4000 |
| Beans | Null | 1500 | 2000 | 1600 |
| Banana | 2000 | 400 | Null | 1000 |
| Carrots | 2000 | 1200 | Null | 1500 |

Unpivot is a reverse operation used to transform it back by rotating column values into rows values.
For *Pivot* operation you need to specify:

* Group By. Columns for grouping
* Pivot columns
* Aggregate function and column
* Pivot values. Values from pivot column to be used (optional)

For Unpivot operation you need to specify:

* Unchanged columns
* Unpivot columns. Columns for unpivoting
* Unpivot names. Column names for unpivoting