# Movie-Recommendation-Model

## Recommendation System Overview
The recommendation system employs various strategies, including popularity-based, association rule mining, content-based filtering, and collaborative filtering. Additionally, it utilizes advanced techniques like Matrix Factorization and ALS to provide accurate and personalized suggestions based on user interactions. The system aims to enhance user satisfaction and loyalty by delivering tailored recommendations aligned with individual preferences.

## Airflow Overview

This Airflow workflow automates the process of setting up and running an Amazon EMR cluster for movie recommendation. It includes the following steps:
- Create EMR Cluster: Initiates the creation of an EMR cluster with specified configurations and applications, such as Spark and Hive.
- Ingest Layer: Submits a Spark job to ingest movie data into the EMR cluster, leveraging the script located at s3://airflowemr/scripts/ingest.py.
- Poll Ingest Layer: Monitors the status of the ingest layer Spark job and waits for completion before proceeding.
- Transform Layer: Submits a Spark job for transforming movie data, utilizing the script at s3://airflowemr/scripts/Movie_Recommendation.py.
- Poll Transform Layer: Monitors the status of the transform layer Spark job and waits for completion before terminating the EMR cluster.
- Terminate EMR Cluster: Terminates the running EMR cluster to ensure cost efficiency.

## Architecture Diagram
![image](https://github.com/YuktaMuthreja/Movie-Recommendation-Model/assets/145282953/cf495c5c-1458-458c-ab00-704a41e4525e)
