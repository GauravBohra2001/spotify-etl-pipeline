# spotify-etl-pipeline
A data engineering project that extracts data from the Spotify Top 50 playlist, stores it in S3 buckets, and performs analysis using Athena.

# Architecture
![etl_spotify](https://github.com/GauravBohra2001/spotify-etl-pipeline/assets/113661738/b75b0fdf-8e00-4234-bbf5-45b079b6adef)


## Project Overview

The goal of this project is to extract data from the Spotify Top 50 playlist and perform various transformations on the data. The extracted data is stored in S3 buckets, and the transformed data is used to build analytics tables using Glue and Athena.

## Technologies Used

- Python
- Spotipy (Python library for the Spotify Web API)
- AWS Lambda
- AWS S3
- AWS Glue
- AWS Athena

## Project Structure

The project is divided into two main parts: data extraction and data transformation.

### Data Extraction

The data extraction code is implemented using Python and the Spotipy library. It connects to the Spotify Web API, retrieves the top 50 songs from the playlist, and extracts relevant information such as album name, release date, total tracks, external URL, song name, and artist name. The extracted data is then stored in JSON format in an S3 bucket.

### Data Transformation

The data transformation code is implemented using AWS Lambda. It retrieves the extracted data from the S3 bucket, performs necessary transformations, and creates a DataFrame. The transformed data is then stored in CSV format in another S3 bucket. Additionally, the code moves the processed data to a "processed" folder and deletes the original files from the "to_processed" folder.

## Project Flow

The Spotify ETL Pipeline follows the following flow:

1. Data Extraction:
   - The data extraction code, implemented in Python using the Spotipy library, connects to the Spotify Web API and retrieves the top 50 songs from the playlist.
   - Relevant information such as album name, release date, total tracks, external URL, song name, and artist name is extracted from the Spotify API response.
   - The extracted data is then stored in JSON format in an AWS S3 bucket.

2. Data Transformation:
   - The data transformation code is implemented using AWS Lambda functions.
   - The extracted data from the S3 bucket is retrieved and transformed using Python code.
   - The transformed data is organized into a DataFrame for further processing and analysis.
   - The transformed data is then stored in CSV format in a separate AWS S3 bucket.

3. Analytics Tables Setup:
   - AWS Glue is used to create a data catalog and define the schema for the transformed data stored in the S3 bucket.
   - AWS Glue crawlers are used to automatically discover and catalog the transformed data.
   - Analytics tables are created in AWS Athena, which allows for easy querying and analysis of the transformed data.

