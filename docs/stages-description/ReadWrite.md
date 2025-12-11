# Readwrite

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Choose storage** | `chooseStorage` |  |
| **Storage** | `storage` | Depending on the selected storage type, the corresponding parameters are displayed. |
| **Note** | `note` | Read stage can have only one outgoing arrow. If need more, you can use Cache Stage. |
| **Write mode** | `writeMode` | 1. Append. Append mode means that when saving a DataFrame to a data source, if data/table<br><br>already exists, contents of the DataFrame are expected to be appended to existing data.<br><br>2. Overwrite. It means that when saving a DataFrame to a data source, if data/table already<br><br>exists, existing data is expected to be overwritten by the contents of the DataFrame.<br><br>3. Error if table exists. This mode means that when saving a DataFrame to a data source, if data<br><br>already exists, an exception is expected to be thrown. |
| **Truncate mode** | `truncateModeCascade` | 3. Cascade. The cascade truncation use to overcome fail, if the target table has a primary key<br><br>which is referenced as a foreign key in other tables. The cascade truncation that would not only<br><br>delete the data from target table, but also from other tables that use target table's primary key as a foreign key constraint. |
| **Truncate mode** | `truncateMode` | 1. None. No truncation would occur, but the target table will be deleted and recreated. Note that all <br><br>the indexes, constraints, etc that were defined for this table will be lost.<br><br>2. Simple. The standard truncation that would delete the data from the target table in the efficient<br><br>way, but would leave table's indexes, constraints and other modifiers intact.<br><br>However note that if the target table has a primary key which is referenced as a foreign key in other tables, <br><br>the truncation will fail. To overcome this either drop constraints manually(outside of VF) prior to accessing the table with VF. |
| **There are no additional fields.** | `noAdditionalFields` |  |

## Db2

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **JDBC URL** | `JDBCURL` | A database connection URL is a string that your DBMS JDBC driver uses to connect to a database.<br><br>The connection URL format for the driver is:<br><br>jdbc:database-type://hostname:port[;property=value[;...]]. |
| **User** | `user` | User name for a JDBC connection. |
| **Password** | `password` | Password for a JDBC connection. |
| **Custom SQL** | `customSql` | Displays the schema and the table fields, if you choose false. If you choose true, you will be able to write your own SQL code in the provided field. |
| **Schema** | `schema` | Schema that the table used for reading belongs to. |
| **Table** | `table` | Database table name. |
| **SQL statement** | `optionDbtable` | The code of your own SQL query.<br><br>- You have to specify both schema name and table name in your custom SQL query.<br><br>- Column names must be surrounded by double quotes.<br><br>- Any syntactic error in SQL query wouldn't be highlighted. |
| **Certificate data (optional)** | `certData` | Enter certification data if needed. |
| **Prepare query** | `prepareQuery` | A prefix that will form the final query together with query. As the specified query will be parenthesized as a subquery in the FROM clause and some databases do not support all clauses in subqueries, the prepareQuery property offers a way to run such complex queries. As an example, spark will issue a query of the following form to the JDBC Source.<br><br><prepareQuery> SELECT <columns> FROM (<user_specified_query>) spark_gen_alias |
| **Session init statement** | `sessionInitStatement` | After each database session is opened to the remote DB and before starting to read data, this option executes a custom SQL statement (or a PL/SQL block). Use this to implement session initialization code. Example: option("sessionInitStatement", """BEGIN execute immediate "alter session set "_serial_direct_read"=true"; END;'"') |
| **Partition column, Lower bound, Upper bound** | `partitionColumn` | These options must all be specified if any of them is specified. In addition, numPartitions must be specified. They describe how to partition the table when reading in parallel from multiple workers. partitionColumn must be a numeric, date, or timestamp column from the table in question. Notice that lowerBound and upperBound are just used to decide the partition stride, not for filtering the rows in table. So all rows in the table will be partitioned and returned. This option applies only to reading. |
| **Number of partitions** | `numberOfpartitions` | The maximum number of partitions that can be used for parallelism in table reading and writing. This also determines the maximum number of concurrent JDBC connections. If the number of partitions to write exceeds this limit, we decrease it to this limit by calling coalesce(numPartitions) before writing. |
| **Fetch size** | `fetchSize` | The JDBC fetch size, which determines how many rows to fetch per round trip. This can help performance on JDBC drivers which default to low fetch size (e.g. Oracle with 10 rows). |
| **Batch size** | `batchSize` | The JDBC batch size, which determines how many rows to insert per round trip. This can help performance on JDBC drivers. This option applies only to writing. |
| **Create table options** | `createTableOptions` | This is a JDBC writer related option. If specified, this option allows setting of database-specific table and partition options when creating a table (e.g., CREATE TABLE t (name string) ENGINE=InnoDB.). |
| **Create table column types** | `createTableColumnTypes` | The database column data types to use instead of the defaults, when creating the table. Data type information should be specified in the same format as CREATE TABLE columns syntax (e.g: "name CHAR(64), comments VARCHAR(1024)"). The specified types should be valid spark sql data types. |
| **Custom schema** | `customSchema` | The custom schema to use for reading data from JDBC connectors. For example, "id DECIMAL(38, 0), name STRING". You can also specify partial fields, and the others use the default type mapping. For example, "id DECIMAL(38, 0)". The column names should be identical to the corresponding column names of JDBC table. Users can specify the corresponding data types of Spark SQL instead of using the defaults. |

## Azure

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Path in container** | `pathInContainer` | Path in the container. |
| **Container** | `container` | Name of the basic containers for holding your data. |
| **Storage account** | `storageAccount` | Name of the storage account. |
| **Authentication type** | `authenticationType` | Can be either storage account key or SAS token. |
| **Storage account key** | `storageAccountKey` | Value of the storage account key. |
| **SAS token** | `SASToken` | Value of the SAS token. |
| **Partition by** | `partitionBy` | Partitions the output by the given columns on the file system. If specified, the output is laid out on the file system similar to Hive's partitioning scheme. As an example, when we partition a dataset by year and then month, the directory layout would look like:<br><br>- year=2016/month=01/<br><br>- year=2016/month=02/ |
| **Write mode** | `writeMode` | 1. Append. Append mode means that when saving a DataFrame to a data source, if data/table already exists, contents of the DataFrame are expected to be appended to existing data.<br><br>2. Overwrite. It means that when saving a DataFrame to a data source, if data/table already exists, existing data is expected to be overwritten by the contents of the DataFrame.<br><br>3. Error if table exists. This mode means that when saving a DataFrame to a data source, if data already exists, an exception is expected to be thrown. |

## Google

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Path to JSON key file** | `pathToKey` | Path to the key file. |
| **Partition by** | `partitionBy` | Partitions the output by the given columns on the file system. If specified, the output is laid out on the file system similar to Hive's partitioning scheme. As an example, when we partition a dataset by year and then month, the directory layout would look like:<br><br>- year=2016/month=01/<br><br>- year=2016/month=02/ |
| **Write mode** | `writeMode` | 1. Append. Append mode means that when saving a DataFrame to a data source, if data/table already exists, contents of the DataFrame are expected to be appended to existing data.<br><br>2. Overwrite. It means that when saving a DataFrame to a data source, if data/table already exists, existing data is expected to be overwritten by the contents of the DataFrame.<br><br>3. Error if table exists. This mode means that when saving a DataFrame to a data source, if data already exists, an exception is expected to be thrown. |
| **Path in bucket** | `pathInBucket` | Path in the bucket. |
| **Bucket** | `bucket` | Name of the basic containers for holding your data. |

## Clickhouse

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Host** | `host` | ClickHouse hostname or IP address. |
| **Port** | `port` | ClickHouse port. |
| **User** | `user` | Name of the ClickHouse user. |
| **Password** | `password` | Password of the ClickHouse user. |
| **Custom SQL** | `customSql` | Displays the schema and the table fields, if you choose false. If you choose true, you will be able to write your own SQL code in the provided field. |
| **Database** | `database` | ClickHouse database name. |
| **Schema** | `schema` | Schema that the table used for reading belongs to. |
| **Table** | `table` | Database table name. |
| **SQL statement** | `optionDbtable` | The code of your own SQL query.<br><br>- You have to specify both schema name and table name in your custom SQL query.<br><br>- Column names must be surrounded by double quotes.<br><br>- Any syntactic error in SQL query wouldn't be highlighted. |

## Cos

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Authentication type** | `authType` | Authentication type which displays accessKey and secretKey, if you choose HMAC, or iamApiKey and iamServiceId, if you choose IAM. |
| **Endpoint** | `endpoint` | The endpoint that a service will talk to, for example, 's3.us-south.objectstorage.softlayer.net'. |
| **Access key** | `accessKey` | The COS access key ID. |
| **Secret key** | `secretKey` | The COS secret access key. |
| **Api key** | `iamApiKey` | The COS IAM api key. |
| **ServiceId key** | `iamServiceId` | The COS IAM service id. |
| **Bucket** | `bucket` | Name of the basic containers for holding your data. |
| **Path in bucket** | `pathInBucket` | Path in the bucket. |
| **File format** | `format` | Spark DataFrame format.<br><br>For CSV, please, specify Header and Delimiter. |
| **Partition By (optional)** | `partitionBy` | Partitions the output by the given columns on the file system. If specified, the output is laid out on the file system similar to Hive's partitioning scheme. As an example, when we partition a dataset by year and then month, the directory layout would look like:<br><br>- year=2016/month=01/<br><br>- year=2016/month=02/ |
| **avroSchema** | `avroSchema` | Avro can be used to define the data schema for a record's value.<br><br>This schema describes the fields allowed in the value, along with their data types. |

## Aws

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Anonymous access** | `anonymousAccess` | Anonymous access which does not display accessKey and secretKey. |
| **SSL** | `ssl` | Whether to enable SSL connections on all supported protocols.<br><br>False by default. |
| **Endpoint** | `endpoint` | The endpoint that a service will talk to, for example, 's3.us-south.objectstorage.softlayer.net'. |
| **Access key** | `accessKey` | The AWS access key ID. |
| **Secret key** | `secretKey` | The AWS secret access key. |
| **Bucket** | `bucket` | Name of the basic containers for holding your data. |
| **Path in bucket** | `pathInBucket` | Path in the bucket. |
| **File format** | `format` | Spark DataFrame format.<br><br>For CSV, please, specify Header and Delimiter. |
| **Partition By (optional)** | `partitionBy` | Partitions the output by the given columns on the file system. If specified, the output is laid out on the file system similar to Hive's partitioning scheme. As an example, when we partition a dataset by year and then month, the directory layout would look like:<br><br>- year=2016/month=01/<br><br>- year=2016/month=02/ |
| **avroSchema** | `avroSchema` | Avro can be used to define the data schema for a record's value.<br><br>This schema describes the fields allowed in the value, along with their data types. |

## Elastic

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Nodes** | `nodes` | Node is an instance of an Elasticsearch where you can store, index, and search data. |
| **Port** | `port` | Port to bind to for incoming HTTP requests. |
| **User** | `user` | User name for connection. |
| **Password** | `password` | Password for connection. |
| **Index** | `index` | The index where the document resides. |
| **SSL** | `ssl` | Whether to enable SSL connections on all supported protocols.<br><br>False by default.<br><br>If it set to True then Certificate data is available, but it is optional. |
| **Certificate data (optional)** | `certData` | Enabled when SSL is set to True.<br><br>Enter certification data for SSL connection if needed. |

## Mongo

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Database** | `database` | MongoDB database name. |
| **Collection** | `collection` | MongoDB collection name. |
| **Host** | `host` | MongoDB hostname or IP address. |
| **Port** | `port` | MongoDB port. |
| **User** | `user` | Name of the MongoDB user. |
| **Password** | `password` | Password of the MongoDB user. |
| **SSL** | `ssl` | Enables/Disables SSL connection. Does not work with self-signed certificates. |

## Cassandra

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Keyspace** | `keyspace` | Name of the keyspace to connect to. |
| **Table** | `table` | Name of the table to connect to. |
| **Cluster (optional)** | `cluster` | Name of the cluster to connect to. |
| **Host** | `host` | Contact point to connect to the Cassandra cluster. |
| **Port** | `port` | Cassandra native connection port. |
| **SSL** | `ssl` | Enable secure connection to Cassandra cluster. |
| **Username** | `username` | Login name for password authentication. |
| **Password** | `password` | Password for password authentication. |
| **Push down enabled** | `pushdownEnabled` | Whether to use pushdown optimizations. |
| **Certificate data (optional)** | `certData` | Custom certificate for SSL connection. |

## Redis

| UI Name | Key (Code) | Description                                                                                                                                                                                                                                           |
| :--- | :--- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Host** | `host` | Host or IP of the initial node we connect to. The connector will read the cluster topology from the initial node, so there is no need to provide the rest of the cluster nodes.                                                                       |
| **Port** | `port` | The initial node's TCP Redis port.                                                                                                                                                                                                                    |
| **Password** | `password` | The initial node's AUTH password.                                                                                                                                                                                                                     |
| **SSL** | `ssl` | Set to true to use TLS. currently it's not allowed to pass client's certificate.                                                                                                                                                                      |
| **Model [binary, hash]** | `model` | Defines the Redis model used to persist DataFrame, default is hash.                                                                                                                                                                                   |
| **Key column** | `keyColumn` | When writing - specifies unique column used as a Redis key, by default a key is auto-generated.<br><br>When reading - specifies column name to store hash key.                                                                                        |
| **Read mode [key, pattern]** | `readMode` | Defines the way that the read operation would be handled. If "key" is selected, then the read would be done based on the "table" field. In case of the "pattern", a provided pattern(option "keysPattern") will dictate what Redis keys will be read. |
| **Table** | `table` | The table name is used to organize Redis keys in a namespace.                                                                                                                                                                                         |
| **Keys pattern** | `keysPattern` | Spark-Redis tries to extract the key based on the key pattern: if the pattern ends with * and it's the only wildcard, the trailing substring will be extracted otherwise there is no extraction - the key is kept as is.                              |
| **TTL** | `ttl` | Data time to live in seconds. Data doesn't expire if TTL is less than 1. By default, it's 0.                                                                                                                                                          |

## Redshift

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Host** | `host` | Host of the Redshift master node. |
| **Port** | `port` | Port of the Redshift master node. |
| **Database** | `database` | Identifies a Redshift database name. |
| **User** | `user` | Credentials to access the database. |
| **Password** | `password` | Credentials to access the database. |
| **SSL** | `ssl` | Whether Redshift connection should be secured via SSL. |
| **Bucket** | `tempdir` | A writeable location in Amazon S3, to be used for unloaded data when reading and Avro data to be loaded into Redshift when writing.<br><br>If you're using Redshift data source for Spark as part of a regular ETL pipeline, it can be useful to set a Lifecycle Policy on a bucket and use that as a temp location for this data. |
| **Access key** | `accessKey` | AWS access key, must have write permissions to the S3 bucket. |
| **Secret key** | `secretKey` | AWS secret access key corresponding to provided access key. |
| **Extra copy options (optional)** | `extraCopyOptions` | A list of extra options to append to the Redshift COPY command when loading data, e.g. TRUNCATECOLUMNS or MAXERROR n (see the Redshift docs for other options).<br><br>Note that since these options are appended to the end of the COPY command, only options that make sense at the end of the command can be used, but that should cover most possible use cases. |
| **Custom SQL** | `customSql` | Whether to read from custom query or from the table. |
| **Table** | `table` | Database table to read/write. |
| **Query** | `query` | Custom SQL query that will be loaded into DataFrame. |



"noAdditionalFields": "There are no additional fields.",


## Stdout

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Description** | `description` | The results can be seen in the logs. |
| **Quantity** | `quantity` | Number of rows that will be displayed in the logs.<br><br>The default value is 10.<br><br>The minimum value is 1.<br><br>The maximum value is 2147483631. |

## Cluster

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **File Path** | `filePath` | File path. |
| **File Name** | `fileName` | File name. |
| **File format** | `format` | Spark DataFrame format.<br><br>For CSV, please, specify Header and Delimiter. |
| **avroSchema** | `avroSchema` | Avro can be used to define the data schema for a record's value.<br><br>This schema describes the fields allowed in the value, along with their data types. |
| **Partition By (optional)** | `partitionBy` | Partitions the output by the given columns on the file system. If specified, the output is laid out on the file system similar to Hive's partitioning scheme. As an example, when we partition a dataset by year and then month, the directory layout would look like:<br><br>- year=2016/month=01/<br><br>- year=2016/month=02/ |
| **File selection** | `fileSection` | Path glob filter - It is used to only include files with file names matching the pattern.<br><br>Recursive file lookup - Disables partition inferring.<br><br>Modified before timestamp - Optional timestamp to only include files with modification times occurring before the specified time. The provided timestamp must be in the following format: YYYY-MM-DDTHH:mm:ss (e.g. 2020-06-01T13:00:00).<br><br>Modified after timestamp - Optional timestamp to only include files with modification times occurring after the specified time. The provided timestamp must be in the following format: YYYY-MM-DDTHH:mm:ss (e.g. 2020-06-01T13:00:00). |
| **Compression codec** | `compressionCodec` | Compression codec - Compression codec to use when saving to file. |
| **Binary format** | `binaryFormat` | Binary format - Type of binary file to process.<br><br>Output content column - Column to store parsed content as a text.<br><br>Output path content - Column to store path to the parsed binary file. |
| **CSV format** | `csvFormatRead` | Header - Column name.<br><br>Delimeter - Delimeter<br><br>Sampling ratio - Defines fraction of input JSON objects used for schema inferring.<br><br>Quote character - Sets a single character used for escaping quoted values where the separator can be part of the value.<br><br>Escape character - Sets a single character used for escaping quotes inside an already quoted value.<br><br>Schema inference - Infers the input schema automatically from data. It requires one extra pass over the data. CSV built-in functions ignore this option.<br><br>Schema enforcement - If it is set to true, the specified or inferred schema will be forcibly applied to datasource files, and headers in CSV files will be ignored.<br><br>Ignore leader white space - A flag indicating whether or not leading whitespaces from values being read/written should be skipped.<br><br>Ignore trailing white space - A flag indicating whether or not trailing whitespaces from values being read/written should be skipped.<br><br>Null value - Sets the string representation of a null value.<br><br>Non-number value - Sets the string representation of a non-number value. |
| **CSV format** | `csvFormatWrite` | Header - Column name.<br><br>Delimeter - Delimeter<br><br>Compression codec - Compression codec to use when saving to file.<br><br>Quote character - Sets a single character used for escaping quoted values where the separator can be part of the value.<br><br>Quote all - A flag indicating whether all values should always be enclosed in quotes. Default is to only escape values containing a quote character.<br><br>Escape character - Sets a single character used for escaping quotes inside an already quoted value.<br><br>Escape quotes - A flag indicating whether values containing quotes should always be enclosed in quotes. Default is to escape all values containing a quote character.<br><br>Ignore leader white space - A flag indicating whether or not leading whitespaces from values being read/written should be skipped.<br><br>Ignore trailing white space - A flag indicating whether or not trailing whitespaces from values being read/written should be skipped.<br><br>Null value - Sets the string representation of a null value. |
| **Delta format** | `deltaFormatRead` | Merge schema - Columns that are present in the DataFrame but missing from the table are automatically added as part of a write transaction when mergeSchema is true.<br><br>Table version timestamp - Delta time travel to specific timestamp. Read version of the data at specific timestamp.<br><br>Table version - Read specific version of the data. |
| **Delta format** | `deltaFormatWrite` | Overwrite schema - By default, overwriting the data in a table does not overwrite the schema. When overwriting a table using mode('overwrite') without replaceWhere, you may still want to overwrite the schema of the data being written. You replace the schema and partitioning of the table by setting the overwriteSchema option to true.<br><br>Replace where - Overwrite data matching a predicate over partition columns only.<br><br>Max records per file - Specify the maximum number of records to write to a single file for a Delta Lake table. |
| **JSON format** | `jsonFormatRead` | Sampling ratio - Defines fraction of input JSON objects used for schema inferring. |
| **JSON format** | `jsonFormatWrite` | Compression codec - Compression codec to use when saving to file. |
| **ORC format** | `orcFormatRead` | Merge schema - Columns that are present in the DataFrame but missing from the table are automatically added as part of a write transaction when mergeSchema is true. |
| **ORC format** | `orcFormatWrite` | Compression codec - Compression codec to use when saving to file. |
| **Parquet format** | `parquetFormatRead` | Merge schema - Columns that are present in the DataFrame but missing from the table are automatically added as part of a write transaction when mergeSchema is true. |
| **Parquet format** | `parquetFormatWrite` | Compression codec - Compression codec to use when saving to file. |
| **Text format** | `textFormatRead` | Whole text - If true, read each file from input path(s) as a single row. |
| **Text format** | `textFormatWrite` | Compression codec - Compression codec to use when saving to file. |

## Dataframe

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Spark Dataframe** | `dataframe` | Represent data as a Spark dataframe. |

## Kafka

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Kafka Bootstrap Server URLs** | `bootstrapServers` | Enter a comma-separated list of host and port pairs that are the addresses of the Kafka brokers in a "bootstrap" Kafka cluster that a Kafka client connects to initially to bootstrap itself. |
| **Topic Name** | `topicName` | Provide the name of the topic you want to read events from in your Kafka data stream. Apache Kafka uses topics to organize and durably store events. You can use the drop-down list to select the topic from the Kafka data source. You can also use the field to search for the topic name. |
| **Certificate** | `filePath` | Upload certificate. |
| **Options** | `options` | Use 'Configure Options' button to set required key/value configuration. |

## Api

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Host** | `host` | API host is the domain name or IP address of the host that serves the API. |
| **Method** | `method` | API method(GET, POST, PUT, DELETE, PATCH). |
| **Headers** | `headers` | Use 'ADD HEADERS' button to set API headers in key/value format. |
| **Params** | `params` | Use 'ADD PARAMS' button to set API parameters in key/value format. |

## Databricks

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Catalog** | `catalog` | Databricks Unity Catalog has a three-level namespace. Catalog is the first layer of the object hierarchy, used to organize you data assets. Provide a catalog name. |
| **Schema** | `schema` | Name of the schema which is the second layer of the object hierarchy. It contains tables and views, or volumes. |
| **Object Type** | `objectType` | Depending on the object type a user selects which type of data to work with. Use Table to access tabular data or Volume to work with non-tabular data stored in cloud object storage. |
| **Table** | `tableRead` | Name of a table or a view that resides in the third layer of Unity Catalog's namespace. |
| **Merge schema** | `mergeSchema` | Columns that are present in the DataFrame but missing from the table are automatically added as part of a write transaction when mergeSchema is true. |
| **Overwrite schema** | `overwriteSchema` | By default, overwriting the data in a table does not overwrite the schema. When overwriting a table using mode('overwrite') without replaceWhere, you may still want to overwrite the schema of the data being written. You replace the schema and partitioning of the table by setting the overwriteSchema option to true. |
| **Table version timestamp** | `tableVersionTimestamp` | Delta time travel to specific timestamp. Read version of the data at specific timestamp. |
| **Table version** | `tableVersion` | Read specific version of the data. |
| **Replace where** | `replaceWhere` | Overwrite data matching a predicate over partition columns only. |
| **Max records per file** | `maxRecordPerFile` | Specify the maximum number of records to write to a single file for a Delta Lake table. |
| **Table** | `tableWrite` | Name of a table that resides in the third layer of Unity Catalog's namespace. |
| **Path** | `path` | A volume resides in the third layer of Unity Catalog's namespace. Volumes are siblings to tables, views, and other objects organized under a schema. They contain directories and files for data stored in numerous formats. Provide a path to a volume including its name and file name (<volume-name>/<file-name>). |
| **Volume** | `volume` | Volume name. |
| **File format** | `format` | Spark DataFrame format.<br><br>For CSV, please, specify Header and Delimiter. |
| **avroSchema** | `avroSchema` | Avro can be used to define the data schema for a record's value.<br><br>This schema describes the fields allowed in the value, along with their data types. |
| **Partition by** | `partitionBy` | Partitions the output by the given columns on the file system. If specified, the output is laid out on the file system similar to Hive's partitioning scheme. As an example, when we partition a dataset by year and then month, the directory layout would look like:<br><br>- year=2016/month=01/<br><br>- year=2016/month=02/ |

## Databricksjdbc

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **JDBC URL** | `JDBCURL` | A database connection URL is a string that your DBMS JDBC driver uses to connect to a database.<br><br>The connection URL format for the driver is:<br><br>jdbc:database-type://hostname:port[;property=value[;...]]. |
| **User** | `user` | User name for a JDBC connection. |
| **Password** | `password` | Password for a JDBC connection. |
| **Catalog** | `catalog` | Databricks Unity Catalog has a three-level namespace. Catalog is the first layer of the object hierarchy, used to organize you data assets. Provide a catalog name. |
| **Schema** | `schema` | Name of the schema which is the second layer of the object hierarchy. It contains tables and views, or volumes. |
| **Table** | `tableRead` | Name of a table or a view that resides in the third layer of Unity Catalog's namespace. |
| **Table** | `tableWrite` | Name of a table that resides in the third layer of Unity Catalog's namespace. |
| **Session init statement** | `sessionInitStatement` | After each database session is opened to the remote DB and before starting to read data, this option executes a custom SQL statement (or a PL/SQL block). Use this to implement session initialization code. Example: option("sessionInitStatement", """BEGIN execute immediate "alter session set "_serial_direct_read"=true"; END;'"') |
| **Partition column, Lower bound, Upper bound** | `partitionColumn` | These options must all be specified if any of them is specified. In addition, numPartitions must be specified. They describe how to partition the table when reading in parallel from multiple workers. partitionColumn must be a numeric, date, or timestamp column from the table in question. Notice that lowerBound and upperBound are just used to decide the partition stride, not for filtering the rows in table. So all rows in the table will be partitioned and returned. This option applies only to reading. |
| **Number of partitions** | `numberOfpartitions` | The maximum number of partitions that can be used for parallelism in table reading and writing. This also determines the maximum number of concurrent JDBC connections. If the number of partitions to write exceeds this limit, we decrease it to this limit by calling coalesce(numPartitions) before writing. |
| **Fetch size** | `fetchSize` | The JDBC fetch size, which determines how many rows to fetch per round trip. This can help performance on JDBC drivers which default to low fetch size (e.g. Oracle with 10 rows). |
| **Batch size** | `batchSize` | The JDBC batch size, which determines how many rows to insert per round trip. This can help performance on JDBC drivers. This option applies only to writing. |
| **Create table options** | `createTableOptions` | This is a JDBC writer related option. If specified, this option allows setting of database-specific table and partition options when creating a table (e.g., CREATE TABLE t (name string) ENGINE=InnoDB.). |
| **Create table column types** | `createTableColumnTypes` | The database column data types to use instead of the defaults, when creating the table. Data type information should be specified in the same format as CREATE TABLE columns syntax (e.g: "name CHAR(64), comments VARCHAR(1024)"). The specified types should be valid spark sql data types. |
| **Custom schema** | `customSchema` | The custom schema to use for reading data from JDBC connectors. For example, "id DECIMAL(38, 0), name STRING". You can also specify partial fields, and the others use the default type mapping. For example, "id DECIMAL(38, 0)". The column names should be identical to the corresponding column names of JDBC table. Users can specify the corresponding data types of Spark SQL instead of using the defaults. |
| **SQL statement** | `sqlStatement` | Displays the schema and the table fields, if you choose false. If you choose true, you will be able to write your own SQL code in the provided field. |

