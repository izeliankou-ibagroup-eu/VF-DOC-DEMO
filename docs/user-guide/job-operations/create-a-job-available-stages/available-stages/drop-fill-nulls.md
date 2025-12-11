# Drop/Fill Nulls Stage.

Drop/Fill Null stage allows gracious null handling.
There are 2 modes:

* Drop
* Fill

With Drop mode you can:

1) Remove all columns where all the rows have null values. For that you need to set *Drop Type* to *Column* and *Drop
Choice* to *All*.

2) Remove specific columns where all the rows have null values. For that you need to set Drop Type to Column, Drop
Choice to Names and specify column names you want to drop.

3) Remove all rows where all the values are null. For that you need to set *Drop Type* – *Row* and *Drop Choice – All*.

4) Remove all rows, where all the values are null in specific columns. (Works as a filter). For that you need to set *Drop
Type* to *Row*, *Drop Choice* to *Names* and specify drop column names.

*Fill* mode is used to replace NULL values on a dataframe column with any constant value or using aggregate function.
( *Fill Value Type* - *Custom* or *Agg* respectively ).
*Fill Value Type* - Custom allows you to replace all columns with one value at once or specify a specific value per column
you want to fill with. For that you need to select *Fill Choice* - *All* or *Names* respectively.
*Fill Value Type* - *Agg* allows you to fill a specific column with a *Strategy*, which stands for the aggregation types:
"*mean*", "*median*" or "*mode*".

![](../../../../assets/user-guide-img/image34.png)
