# Sort Stage.

There are two types of sorting available: *Full sort* and *Sort within partitions*.
*Full sort* classifies dataframe by the specified column(s).
*Sort within partitions* sorts each dataframe partition by the specified column(s). In this case, the order of the output data
is not guaranteed because the data is ordered at the partition level.
Select column(s) to sort by and the sort order (default value is Asc).
Available sort options:

* asc
* asc nulls first
* asc nulls last
* desc
* desc nulls first
* desc nulls last
