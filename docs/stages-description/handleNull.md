# Handlenull

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Mode** | `mode` | Provide mode:<br><br>1. Drop - Allows to remove rows/column with null values.<br><br>2. Fill - Allows to replace null values. |
| **Drop Type** | `dropType` | Replacement type for missing values ("Column" &#124; "Row").<br><br>"Column" option allows to remove all or specific columns where all the rows have null values.<br><br>"Row" option allows to remove all rows, where all the values are null. |
| **Drop Choice** | `dropChoice` | What to drop:<br><br>1."Names"- remove all rows, where all the values are null in some column (works as a filter).<br><br>2."All". |
| **Drop Columns** | `dropColumns` | Which columns to delete if Drop Choice = "Names" . |
| **Fill Value Type** | `fillValueType` | Replacement type for missing values ("Custom" &#124; "Agg").<br><br>Notes:<br><br>Set aggregation function in "Fill Strategy" field. |
| **Fill Choice** | `fillChoice` | What to fill:<br><br>1."Names"- provide specific column(s) and value for it in "Fill nulls" section.<br><br>2."All".<br><br>Notes:<br><br>Use the Plus button to add Column/Value pairs. |
| **Fill Values** | `fillValues` | Value(s) for columns to replace nulls. |
| **Fill Columns** | `fillColumns` | Column(s) to be replaced by using aggregate function |
| **Fill Strategy** | `fillStrategy` | Aggregation type ("mean" &#124; "median" &#124; "mode") |

