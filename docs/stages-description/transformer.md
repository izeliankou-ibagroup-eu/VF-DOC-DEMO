# Transformer

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Output** | `output` | Transformer stage gives the user an ability to modify columns that will be written to some data storage later on.<br><br>The customization allows for (and not limited to):<br><br>1. Specify only needed columns. <br><br>2. Provide alias for columns.<br><br>3. Use spark-sql functions/procedures to modify (or create new) columns.<br><br>[For more information about Built-in Functions click here.](https://spark.apache.org/docs/latest/api/sql/index.html) |
| **Note** | `note` | An identifier is a string used to identify a database object such as a table, view, schema, column, etc. Spark SQL has regular identifiers and delimited identifiers, which are enclosed within backticks. Therefore be vigilant when you reference certain database objects in your query since some might have symbols that might be misinterpreted (e.g. spark function invocation) if the whole object's name is not guarded by<br><br>[For more information of backticks click here.](https://spark.apache.org/docs/latest/sql-ref-identifier.html) |
| **Mode** | `mode` | Transformer mode defines the type of the SQL query (Spark SQL dialect) that is accepted and executed.<br><br>Simple - only allows you to specify the part between SELECT and FROM. You can do things like these:<br><br>1) col1, concat(col1, col2)<br><br>2) count(*) as count<br><br>3) a, b, row_number() OVER (PARTITION BY a ORDER BY b)<br><br>4) col, exists(col, x -> x % 2 == 0)<br><br>5) col, collect_list(col)<br><br>Syntax:<br><br> <column_name_1> as <alias_1>, function(<column_name_2>) as <alias_2><br><br>Full SQL - allows you to write a full-blown Spark SQL query. Though you would have to specify the table's name in the query by manually referencing the value from the "Table name" parameter. |
| **Table name** | `tableName` | The name of the table that you should use within the Spark SQL query. Only applicable for Full SQL transformer mode. |

