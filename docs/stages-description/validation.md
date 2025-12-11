# Validation

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **isError** | `isError` | End job with error if validation fails. |
| **Schema** | `validationSchema` | Provide validation schema. |
| **Column** | `column` | Specify column name. |
| **dataType** | `dataType` | Data type of column.<br><br>Note: may work incorrectly when reading files without a schema (when reading сsv files, all fields have string type). |
| **minValue** | `minValue` | Minimum field value. |
| **maxValue** | `maxValue` | Maximum field value. |
| **minLength** | `minLength` | Minimum string length. |
| **maxLength** | `maxLength` | Maximum string length. |
| **inValues** | `inValues` | Possible values separated by commas. |
| **regex** | `regex` | Regular expression. |
| **notNull** | `notNull` | Doesn't contain null value. |
| **uniqueness** | `uniqueness` | Contains only unique values. |

