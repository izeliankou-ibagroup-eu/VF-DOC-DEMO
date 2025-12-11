# Cdc

This stage is intended to find all differences between before (old) and after (new) datasets.

Based on differences CDC produces additional column 'Operation', which indicates the state of the row from the old dataset considering it's presence/absence in the new one.

CDC compares each row of the new and the old datasets, based on key and columns to compare values and sets Operation value.

NOTE: old and new datasets must not contain duplicates (rows with the same key) based on key column(s).

Old and new datasets columns to compare and key columns must be presented in both datasets with the same names. If there are duplicated rows at least in one of dataset, results of the CDC will be unpredictable.

CDC change codes (column Operation in the result set):

0 - Copy (row doesn't have any changes)

1 - Insert (row exists only in new dataset, should be inserted)

2 - Delete (row exists only in old dataset, should be deleted)

3 - Update (row exists and has different values in both datasets, should be updates in old with new values from new)

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Link Ordering** | `linkOrdering` | This option allows you to specify which input link carries the before data set and which carries the after data set. To rearrange the links, click the up arrow button or the down arrow button. |
| **Key** | `key` | Specify unique key to compare. As example, 1 or more columns. Columns names should be the same. |
| **Mode** | `mode` | Return All. Returns all rows (modified and unmodified).<br><br>Return Delta. Returns only modified rows. |

