# Movie-Recommendation-Model

## Overview

This Airflow workflow automates the process of setting up and running an Amazon EMR cluster for movie recommendation. It includes the following steps:
- Create EMR Cluster: Initiates the creation of an EMR cluster with specified configurations and applications, such as Spark and Hive.
- Ingest Layer: Submits a Spark job to ingest movie data into the EMR cluster, leveraging the script located at s3://airflowemr/scripts/ingest.py.
- Poll Ingest Layer: Monitors the status of the ingest layer Spark job and waits for completion before proceeding.
- Transform Layer: Submits a Spark job for transforming movie data, utilizing the script at s3://airflowemr/scripts/Movie_Recommendation.py.
- Poll Transform Layer: Monitors the status of the transform layer Spark job and waits for completion before terminating the EMR cluster.
- Terminate EMR Cluster: Terminates the running EMR cluster to ensure cost efficiency.

## Architecture Diagram
![image](https://github.com/YuktaMuthreja/Movie-Recommendation-Model/assets/145282953/cf495c5c-1458-458c-ab00-704a41e4525e)
