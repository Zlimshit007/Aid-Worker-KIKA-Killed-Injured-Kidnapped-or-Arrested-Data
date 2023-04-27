# Aid Worker KIKA(Killed, Injured, Kidnapped, or Arrested) Data set
This dataset contains agency- and publicly-reported data for events in which an aid worker was killed, injured, kidnapped, or arrested, Categorized by country.
# Methodology
The Insecurity Insight data resource includes incidents where an aid worker was reportedly killed or injured by the use of violence (but not by illness or in an accident), kidnapped, or arrested for any reason (KIKA).
It is compiled from two categories of sources:
- verified security incidents submitted to Insecurity Insight by Aid in Danger partner agencies; and
- open-source-reported incidents identified by Insecurity Insight and published in the Aid in Danger News Brief.

Incidents are categorised by date, geographical location (including geocodes), number of aid workers affected, who they worked for and, if available, what type of programme their aid agency provided, as well as available information on the reported perpetrator(s)/actor(s) and weapon(s) used.
It does not include information on the actor(s) intentions or assign a classification indicating the nature of an attack, such as whether it was an ambush or aerial bombardment, for example.
## Codebook
Each row represents information on an individual incident. For cases where the number of aid workers is unspecified, one is counted.
- Date: The reported date on which the incident occurred.
- Country: The country in which the incident occurred.
- Country ISO3: The ISO country code for the country in which the incident occurred.
- Admin 1: The admin 1 name of the place where the incident occurred. This is automatically generated based on the incident’s geocoding and geoprecision information.
- Incident description: A generic and brief description of the incident.
- Latitude: The latitude code for the place where the incident occurred. This is automatically generated based on the incident’s geocoding and geoprecision information.
- Longitude: The longitude code for the place where the incident occurred.
- Location of incident: The type of location where the incident occurred.
- Actor: The classification of the perpetrator(s) reportedly responsible for the incident.
- Actor name: The name of the actor reportedly responsible for the incident.
- Weapon carried/used: The type of weapon carried or used by the perpetrator when the incident occurred.
- Organisation affected: The classification of the organisation(s) affected in the incident.
- Programme focus: The category to describe the type of programme affected by the incident.
- Aid workers killed: Sum of aid workers reportedly killed in the incident. Note: This count includes kidnapped aid workers killed while in captivity.
- Aid workers killed in captivity: Sum of aid workers reportedly killed while in captivity, or during a rescue mission or an attempted escape.
- International aid workers killed: Sum of international aid workers reportedly killed in the incident.
- International aid workers killed in captivity: Sum of international aid workers reportedly killed while in captivity, or during a rescue mission or an attempted escape.
- National aid workers killed: Sum of national aid workers reportedly killed in the incident.
- National aid workers killed in captivity: Sum of national aid workers reportedly killed while in captivity, during a rescue mission or during an attempted escape.
- Male aid workers killed: Sum of male aid workers reportedly killed in the incident.
- Male aid workers killed in captivity: Sum of male aid workers reportedly killed while in captivity, or during a rescue mission or an attempted escape.
- Female aid workers killed: Sum of female aid workers reportedly killed in the incident.
- Female aid workers killed in captivity: Sum of female aid workers reportedly killed while in captivity, or during a rescue mission or an attempted escape.
- Aid workers kidnapped: Sum of aid workers reportedly kidnapped in the incident.
- Known kidnapping/arrest outcome: The known status of aid workers reportedly kidnapped or arrested.
- International aid workers kidnapped: Sum of international aid workers reportedly kidnapped in the incident.
- National aid workers kidnapped: Sum of national aid workers reportedly kidnapped in the incident.
- Male aid workers kidnapped: Sum of male aid workers reportedly kidnapped in the incident.
- Female aid workers kidnapped: Sum of female aid workers reportedly kidnapped in the incident.
- Aid workers arrested: Sum of aid workers reportedly arrested in the incident. Includes: arrested, charged, detained, fined or imprisoned.
- International aid workers arrested: Sum of international aid workers reportedly arrested in the incident.
- National aid workers arrested: Sum of national aid workers reportedly arrested in the incident.
- Male aid workers arrested: Sum of male aid workers reportedly arrested in the incident.
- Female aid workers arrested: Sum of female aid workers reportedly arrested in the incident.
- Aid workers injured: Sum of aid workers reportedly injured in the incident.
- International aid workers injured: Sum of international aid workers reportedly injured in the incident.
- National aid workers injured: Sum of national aid workers reportedly injured in the incident.
- Male aid workers injured: Sum of male aid workers reportedly injured in the incident.
- Female aid workers injured: Sum of female aid workers reportedly injured in the incident.
- SiND incident ID: The incident number in the Security in Numbers Database (SiND).

# Tools Used

The following tools were used for this project:

- Excel worksheet
- Python
- Mysql
- Power BI

***
# PYTHON FOR EXPLORATORY DATA ANALYSIS (EDA), DATA CLEANING, AND SORTING
The dataset used for the analysis contained 929 rows × 45 columns. Exploratory Data Analysis (EDA) was done on the data to get a better understanding and insight of the dataset, We need to perform some data cleaning before we can start analyzing the dataset. This involves dropping irrelevant columns, renaming columns, handling missing values, and converting data types, the result was written back to a csv file named 'aid_workers_kika_df'.
below is the code and dataset done using python.

https://github.com/Zlimshit007/Aid-Worker-KIKA-Killed-Injured-Kidnapped-or-Arrested-Data/blob/zlimshitmain/aid-worker-kika-data.ipynb

***
# DATA ANALYSIS USING MySQL SERVER
For my analysis phase, i connectted dataset to mysql using python and import the csv file into mysql and create a table?
## Here are the steps i used in importing my dataset to mysql server.

- I connected to MySQL using the mysql.connector module:

![connector](https://user-images.githubusercontent.com/114537955/233411788-7085a2b9-475d-4b01-9a80-330057c974bd.png)

- I created a new database for the aid_workers_kika.csv data:

![connect 2](https://user-images.githubusercontent.com/114537955/233412813-97779844-99bc-45a3-80a6-597c567961b4.png)

- I connected to the new database:

![connect 3](https://user-images.githubusercontent.com/114537955/234837670-2d16c4b9-341d-4fdd-8334-beb6ca0bbd44.png)

- I created a table with the desired columns:

![connect 4](https://user-images.githubusercontent.com/114537955/233414168-84b9f899-8bd5-4845-85ef-352d4219e9d1.png)

- I read the CSV file into a pandas dataframe:

![connect 5](https://user-images.githubusercontent.com/114537955/233414695-af22a616-72ef-4b38-a447-1c9bd12e8d0e.png)

- I used a loop to iterate over each row in the dataframe and insert into MySQL table

![connect 6](https://user-images.githubusercontent.com/114537955/233415998-b7c8cf9c-5b23-41b8-8f4a-354da772231f.png)

My dataset is then read and imported to mysql server
After Importing the tables, I explored the data and asked several questions to gain more insight and knowledge from the data, detect patterns, and establish connections between different variables. The questions asked were:

Data Analysis Quaries:

- Retrieve the Number of incidents by country:
- Retrieve the locations of the incidents:
- Retrieve the actors of the incident:
- Retrieve the weapons used:
- Retrieve the organization mostly involved:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by organisation:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:

you can find the solution here:  https://github.com/Zlimshit007/Aid-Worker-KIKA-Killed-Injured-Kidnapped-or-Arrested-Data/blob/zlimshitmain/Mysql%20Aid%20workers%20Kika%20data%20quary



