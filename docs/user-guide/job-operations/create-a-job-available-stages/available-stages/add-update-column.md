# Add/Update Column Stage.

The *Add/Update* Column stage is used to add a new column to a dataframe, change value of an existing column, con-
vert the data type of a column or derive a new column from an existing column. Also it gives the ability to use condi-
tions or window functions to provide column values.
It has the following operations types:

* deriveColumn
* addConstant
* changeType
* renameColumn
* useConditions
* useWindowFunctions

If you select useWindowFunctions you need to pick a function from the dropdown list. Each one has its own parame-
ters to enter.

The available window functions are:

* rank
* dense_rank
* percent_rank
* cume_dist
* row_number
* ntile
* lag
* lead
* count
* sum
* avg
* max
* min