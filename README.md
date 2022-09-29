
# Cyclistic Case Study

This case study is the capstone project of the [Google Data Analytics Professional Certificate](https://www.coursera.org/professional-certificates/google-data-analytics) from Coursera.

In this GitHub repository, I'll be going through the technicalities of this project, and I'll share the code I used for each step of the data analysis process (ask, prepare, process, analyze, share and act). For a non-technical article where I present my insights, I invite you to visit my [Medium article](https://github.com/omorales12/Cyclistic).

## Introduction and context

For this case study, I'll be impersonating a junior data analyst at the marketing department of a fictional bike-share company called Cyclistic, which is based in Chicago. Cyclistic has more than 5,800 bikes distributed among 600+ docking stations. The users of Cyclistic services can be divided into two groups:

- **Casual riders**: those customers who purchase single rides or full-day passes.
- **Annual subscribers**: those customers who purchase annual memberships.

My manager is Lily Moreno, the director of marketing. She believes that having a higher number of annual subscribers is key in the company's success, therefore she tasked our team with understanding our current users and with helping her design a marketing campaign to turn casual riders into members, so that she can later pitch it to the company's executive team. That being said, the purpose of this case study is to better understand how casual riders and members differ.

  

## Data collection

Cyclistic is a fictional company, but, for the purpose of this case study, it is inferred the data used in this case is first-party data, collected by Cyclistic itself with its own resources. Reality is the data I will use throughout this case study was collected by an actual bike-sharing company called Divvy, this data is made publicly available under [this](https://ride.divvybikes.com/data-license-agreement) license. It is important to consider that due to privacy protection regulations, no personally identifiable information (PII) is made available, this suggest the published datasets have already gone through a de-identification process.

  

## Exploring data

The files used for this case study can be found [here](https://divvy-tripdata.s3.amazonaws.com/index.html). I will be using data from the last 12 months. I’m writing this report in August 2022, therefore the latest available data to me is from August 2021 to July 2022. The naming convention of these files is the following: **YYYYMM-divvy-tripdata**.

After downloading the ZIP files, I created a common directory so all data lives in one place within my system. I will also create a backup of the original files as I’ll be processing them as I make progress with the project.

By looking at the CSV files for the last 12 months, we can find the following attributes within them:

- **ride_id**: this seems to be a unique ID that identifies each ride.
- **rideably_type**: this identifies the bike type of each one of the rides.
- **started_at**: date and time at which the ride started.
- **ended_at**: date and time at which the ride ended.
- **start_station_name**: name of the station where the ride started.
- **start_station_id**: id of the station where the ride started.
- **end_station_name**: name of the station where the ride ended.
- **end_station_id**: id of the station where the ride ended.
- **start_lat**: latitude where ride started.
- **start_lng**: longitude where ride started.
- **end_lat**: latitude where ride ended.
- **end_lng**: longitude where ride ended.
- **member_casual**: identifies rider as either casual or member.

To make our analysis more robust, I can decide whether to make some data pre-processing. This represents the addition of two more attributes:

-   **ride_length**: calculate the difference between the ended_at and started_at dates.
-   **day_of_week**: calculate the day of the week at which the ride started, the assigned values will go from 1 (Sunday) to 7 (Saturday).

## Asking S.M.A.R.T. questions

Knowing the nature of the available data, I formulated some questions to guide my analysis:

 - How is the number of rides of members compared to that of casual riders from August 2021 to July 2022?

## Importing data to SSMS

I'll be using Microsoft's SQL Server Management Studio to manage my local SQL Server. For this project, I'll create a database called **Cyclistic_Case_Study**, where I'll be creating the necessary tables and schemas.

