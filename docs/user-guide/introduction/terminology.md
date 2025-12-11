# Terminology

## ETL (Extract, Transform, Load)

**ETL** is an abbreviation for extract, transform, load — three database functions combined into one tool to pull data out of one database, transform it and place into another.

*   **Extract** is the process of reading data from a database. In this stage, the data is collected, often from multiple and different types of sources.
*   **Transform** is the process of converting the extracted data from its previous form into the form needed to place it into another database.
*   **Load** is the process of writing the data into the target database.

## Job

A **job** is a chain of individual stages linked together. It describes the flow of data from its source to target. Usually, a job has a minimum of one data input and output.
However, some jobs can accept more than one data input and output it to more than one target.
In Visual Flow, the available stages are:

* Read
* Write
* Group By
* Remove duplicates
* Filter
* Transformer
* Sort
* Slice
* Pivot
* Add/Update Column
* String Functions
* Date/Time
* Drop/Fill Nulls
* Join
* Union
* Change Data Capture
* Cache
* Validate

## Pipeline

A **pipeline** is a compound of multiple jobs and can be run. In Visual Flow, the user can use such stages as:

* Job
* Container
* Notification
* Wait