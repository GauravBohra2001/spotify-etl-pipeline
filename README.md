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

The data transformation
