# AWS S3 to Salesforce ETL Pipeline 
## Overview 
This project automates the process of extracting, transforming, and loading (ETL) data from AWS S3 into Salesforce objects using AWS AppFlow. The pipeline includes data transformation, format conversion to JSON, and UPSERT logic to ensure no duplicate entries in Salesforce
## Key Features 
### 1. Seamless Data Transformation 
- Converts Parquet data into JSON format for compatibility with Salesforce 
- Transforms raw data to match Salesforce object schema 
### 2. Automated Data Integration 
- Infrastructure-as-Code (IaC) implementation for creating flows with boto3 
- UPSERT logic ensures data integrity 
### 3. Real-Time Triggering 
- Designed to trigger on-demand data flow via AWS AppFlow 
## Technologies Used 
- **AWS Glue**: For data transformation and schema mapping 
- **AWS AppFlow**: For connecting S3 with Salesforce 
- **Boto3**: AWS SDK for programmatic interaction 
- **Spark (PySpark)**: For data manipulation and format conversion 
- **Salesforce API**: For data integration 
## Architecture 
The ETL pipeline is structured as follows:
1. **Raw Data**: Read from an S3 bucket
2. **Data Transformation**: Processed using PySpark in AWS Glue to match Salesforce schema
3. **Data Conversion**: Parquet files are converted to JSON format
4. **Data Flow**: AWS AppFlow maps and uploads data to Salesforce objects

*(Include the architecture diagram under this section if available.)*
## Setup Instructions 
### 1. Prerequisites 
- AWS CLI configured with access to S3 and AppFlow 
- Salesforce credentials and API setup 
- Python 3.9+ with boto3 and PySpark installed 
### 2. Steps to Run 
1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/aws-s3-salesforce-etl.git
    cd aws-s3-salesforce-etl
    ```
2. **Set up environment variables in a .env file:**
    ```env
    S3_BUCKET_NAME=<Your S3 bucket>
    SALESFORCE_CLIENT_ID=<Your Salesforce Client ID>
    SALESFORCE_CLIENT_SECRET=<Your Salesforce Secret>
    ```
3. **Run the ETL script:**
    ```bash
    python s3_to_salesforce_etl.py
    ```
## Future Enhancements 
1. Automate the triggering of data flows based on events
2. Integrate monitoring and logging for error tracking
3. Expand support for additional Salesforce objects
