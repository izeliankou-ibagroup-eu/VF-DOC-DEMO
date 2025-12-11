# Sort

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Sort type** | `sortType` | Choose type of sort (Full sort or Sort within partitions).<br><br>Full sort sorts DataFrame by the specified column(s).<br><br>Sort within partitions sorts each DataFrame partition by the specified column(s).<br><br>The order of the output data is not guaranteed because the data is ordered on partition-level. |
| **Order columns** | `orderColumns` | Choose column(s) and sorting order (default value is asc).<br><br>Possible sorting orders: asc, asc nulls first, asc nulls last, desc, desc nulls first, desc nulls last. |

