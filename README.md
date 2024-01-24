# Airflow-MySQL-To-BigQuery


Airflow-MySQL-To-BigQuery
How to use
This guide is designed to help you move data from a MySQL database to Google BigQuery using Apache Airflow. 

Follow these steps to set up and execute the process:

Install Required Libraries: Begin by installing the necessary libraries. Open your terminal and run the following command:

pip install -r requirements.txt
This command will install all the dependencies listed in the requirements.txt file.

Configure Airflow Connections: In Apache Airflow, you need to set up two connections:

GCP Connection: Create a connection for Google Cloud Platform. This is referred to as gcp_conn_id in the scripts.
MySQL Connection: Set up a connection to your MySQL database. This is the mysql_conn_id.
These connections are crucial for enabling Airflow to access your MySQL database and Google Cloud Storage.

Set Up ETL Script: In the etl.py file, you will need to specify several parameters:

BUCKET_NAME: The name of the Google Cloud Storage bucket where the data will be temporarily stored.
SQL_QUERY: The SQL query to extract data from the MySQL database.
FILENAME: Name of the file that will be created in the GCS bucket.
gcp_conn_id: Your GCP connection ID as set in Airflow.
mysql_conn_id: Your MySQL connection ID as set in Airflow.
schema: The schema of your data. This should match the schema in BigQuery.
destination_dataset_table: The dataset and table in BigQuery where you want to load the data.

Fill these details accurately to ensure smooth data transfer.

Run the Airflow DAGs: With everything set up, you can now run your Airflow DAGs. 

This will trigger the ETL process you've configured, extracting data from MySQL, storing it temporarily in GCS, and finally loading it into BigQuery.

After completing these steps, your data will be successfully transferred from a MySQL database into Google BigQuery. 
This process automates the data pipeline, making it efficient and reliable for repeated use.
























## How to use

1. Install requirements libraries using this command ```pip install -r requirements.txt```
2. In Airflow you need to add connection for ```gcp_conn_id``` and ```mysql_conn_id```. 
3. in [etl.py](etl.py), filled ```BUCKET_NAME```, ```SQL_QUERY```, ```FILENAME```, ```gcp_conn_id```, ```mysql_conn_id```, ```schema```, ```destination_dataset_table```
4. Then you can just run the airflow and the dags

Then finally, you have moved your data from MySQL into BigQuery.