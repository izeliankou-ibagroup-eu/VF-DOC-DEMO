# Transformer Stage.

The *Transformer* stage allows you to modify columns to fill them with data further. *Transformer* mode defines the type
of SQL query (Spark SQL dialect) which is taken to execute.
*Simple* mode only allows you to specify the part between SELECT and FROM. You can do things like these:
```
col1, concat(col1, col2)
count(*) as count
a, b, row_number() OVER (PARTITION BY a ORDER BY b)
col, exists(col, x -> x % 2 == 0)
col, collect_list(col)
```

The syntax is: <column_name_1> as <alias_1>, function(<column_name_2>) as <alias_2>.

*Full SQL* mode allows you to write a full-blown Spark SQL query. In this case, you have to specify a table name
manually or reference a table name from a parameter.

*Table name*. The name of the table which should be used within the Spark SQL query. Applicable for *Full SQL* transformer mode only.