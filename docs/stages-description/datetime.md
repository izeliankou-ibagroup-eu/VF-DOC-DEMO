# Datetime

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Choose operation type** | `chooseOperation` |  |
| **Operation Type** | `operationType` | Operation types possible values description: |

## Option

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **targetColumn** | `targetColumn` | Column where the result is displayed. |
| **sourceColumn** | `sourceColumn` | Column from which data is taken. |
| **format** | `format` | Format specified by the date format.<br><br>Format: 'year', 'yyyy', 'yy' to truncate by year, 'month', 'mon', 'mm' to truncate by month.<br><br>format: 'year', 'yyyy', 'yy' to truncate by year, 'month', 'mon', 'mm' to truncate by month, 'day', 'dd' to truncate by day. Other options are: 'second', 'minute', 'hour', 'week', 'month', 'quarter'.<br><br>Format: yyyy-MM-dd HH:mm:ss. |
| **numMonths** | `numMonths` | Number of months. |
| **days** | `days` | Number of days. |
| **roundOff** | `roundOff` | If roundOff is set to true, the result is rounded off to 8 digits; it is not rounded otherwise. |
| **dayOfWeek** | `dayOfWeek` | Day of the week; For example: Sunday. |
| **startColumn** | `startColumn` | Start date column. |
| **endColumn** | `endColumn` | End date column. |

## Operationtypes

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **current_date** | `current_date` | Returns the current date as a date column. |
| **date_format** | `date_format` | Converts a date/timestamp/string to a value of string in the format specified by the date format given by the second argument. |
| **to_date** | `to_date` | Convert string type containing date value to date format. |
| **add_months** | `add_months` | Add months to date. |
| **date_add** | `date_add` | Add days to the date. |
| **date_sub** | `date_sub` | Subtract the days from date field. |
| **datediff** | `datediff` | Returns difference between two dates in days. |
| **months_between** | `months_between` | Returns number of months between two dates. |
| **next_day** | `next_day` | Returns the first date which is later than the value of the date column. |
| **year** | `year` | Extract the year of a given date as integer. |
| **quarter** | `quarter` | Extract the quarter of a given date as integer. |
| **month** | `month` | Extract the month of a given date as integer. |
| **dayofweek** | `dayofweek` | Returns the first date which is later than the value of the date column that is on the specified day of the week. |
| **dayofmonth** | `dayofmonth` | Extracts the day of the month as an integer from a given date/timestamp/string. |
| **dayofyear** | `dayofyear` | Extracts the day of the year as an integer from a given date/timestamp/string. |
| **weekofyear** | `weekofyear` | Extracts the week number as an integer from a given date/timestamp/string. A week is considered to start on a Monday and week 1 is the first week with more than 3 days, as defined by ISO 8601. |
| **last_day** | `last_day` | Returns the last day of the month which the given date belongs to. |
| **trunc** | `trunc` | Returns date truncated to the unit specified by the format. |
| **current_timestamp** | `current_timestamp` | Returns the current timestamp as a timestamp column. |
| **hour** | `hour` | Extracts the hours as an integer from a given date/timestamp/string. |
| **minute** | `minute` | Extracts the minutes as an integer from a given date/timestamp/string. |
| **second** | `second` | Extracts the seconds as an integer from a given date/timestamp/string. |
| **to_timestamp** | `to_timestamp` | Converts time string with the given pattern to timestamp. |
| **date_trunc** | `date_trunc` | Returns timestamp truncated to the unit specified by the format. |
| **unix_timestamp** | `unix_timestamp` | Returns the current Unix timestamp (in seconds) as a long. |
| **to_unix_timestamp** | `to_unix_timestamp` | Converts time string in format yyyy-MM-dd HH:mm:ss to Unix timestamp. |
| **from_unixtime** | `from_unixtime` | Converts the number of seconds from unix epoch (1970-01-01 00:00:00 UTC) to a string representing the timestamp of that moment in the current system time zone in the given format. |

