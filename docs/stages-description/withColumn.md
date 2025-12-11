# Withcolumn

'Add/Update Column' stage gives the user an ability to perform the following operations with data:

1. Adding a new column to dataframe.

2. Changing value of an existing column. 

3. Deriving new column from an existing column.

4. Using conditions to provide column values.

5. Changing column data type.

6. Working with Window Functions.

7. Replacing column values that match the pattern with new ones, replace column values character by character, using conditions.

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Operation Type** | `operationType` |  'deriveColumn' — create a new column from the existing one.<br><br> 'addConstant' — create a column with constant values.<br><br> 'changeType' — change column type.<br><br> 'renameColumn' — rename the column.<br><br> 'useConditions' — create a column with values that depend on some conditions.<br><br> 'useWindowFunction' — create a column with values obtained as a result of using the window function.<br><br> 'replaceValues' — replace column values that match the pattern with new ones.<br><br> 'replaceValuesUsingConditions' — replace values in the column using conditions.<br><br> 'replaceValuesCharByChar' — replace column values character by character. |
| **Column** | `column` | Specify column name. |

