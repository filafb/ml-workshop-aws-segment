# AWS + Segmenet Machine Learning workshop
_Igor - Segment_
_Jams Jory - AWS_

AWS provides:
  - Low level: ML Framewokrs & infrastructure
  - ML services
  - AI services

*Amazon Personalize*
  How it works                          | \
  1) Activity stream                    |  \
    - views, signups, conversion, etc   |   \
  2) Inventory                          |     Amazon Personalize => API
    - videos, products, articles, etc   |   /
  3) Demographics (optional)            |  /
    - Name, age, location, etc          | /


Amazon Personalize Data ingestion with segment

*Offline data => Aws S3 => Amazon Personalize <= Segement <= Your sources*

## Exercise One _Taking historical data and bringing it to a aws S3 bucket_
  - Created Segment Sources (web - JS, android, ios, and personas event - python)
  - Set up Segment Personas - enabled all sources to connect to it
  - Created a Segment Destination - S3
  - Using Cloud9 (cloud-based integrated development environment) to run code and populate segment with data
  - Using Athena (interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL) to run DDL scrit and make queries to a json file as it was a db
  - Using aws Glue ETL (a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics) to transform JSON into CSV and write it to a S3 bucket
  -

## Exercise Two
  - Transformed CVS --[Amazon Personalize]--> Datasets --> Solutions (Recipes) --> Campaigns
  - Two ways to import data to AWS Personalize:
    1) Upload it from a s3;
    2) using aws sdk
  Steps:
  - Create a dataset group in Personalize;
  - Define the schema representing csv file;
  - Upload the csv file from a s3 bucket;
  - Create a personalized solution, or machine learning model
  - Create a personalized campaign (a deployed solution - able to make recommentation for users)

## Exercise three - Getting recommendations
  - REST API --> Amazon API Gataway --> AWS Lambda <-- Amazon Personalize Recommendations

  - Creating a function on AWS Lambda
  - Set up a Lambda trigger and see the API under the API Gateway
  - Make a API call through API gateway

## Exercise four - Getting data from sources, feeding the ML and getting back recommendations

  - Create a function on Lambda to be called by Segment destination
  - Configure a Tracker on Personalize. This way, any user action associated to it will be passed and considerided in the dataset for training models.
  - Using a source on Segment to receive updates
