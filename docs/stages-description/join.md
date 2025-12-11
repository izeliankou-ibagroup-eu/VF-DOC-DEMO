# Join

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Join type** | `joinType` | Inner join. Transfers records from input data sets whose key columns contain equal values to the output data set. Records whose key columns do not contain equal values are dropped.<br><br>Left outer join. Transfers all values from the left data set but transfers values from the right data set only where key columns match. The stage drops the key column from the right data set.<br><br>Right outer join. Transfers all values from the right data set and transfers values from the left data set and intermediate data sets only where key columns match. The stage drops the key column from the left and intermediate data sets.<br><br>Full outer join. Transfers records in which the contents of the key columns are equal from the left and right input data sets to the output data set. It also transfers records whose key columns contain unequal values from both input data sets to the output data set.<br><br>Cross join. Returns a result data set where each row from the first table is combined with each row from the second table.<br><br>Left semi join. Returns values from the left side of the relation that has a match with the right.<br><br>Left anti join. Returns values from the left relation that has no match with the right. |
| **Link Ordering** | `linkOrdering` | This option allows you to specify which input link is regarded as the left link and which link is regarded as the right link. By default the first link you add is regarded as the left link, and the last one as the right link. You can use arrow up and arrow down buttons to override the default order. |
| **Key** | `key` | Specify keys to combine rows from multiple tables. |

