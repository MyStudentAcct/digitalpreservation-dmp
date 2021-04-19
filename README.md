# Investigate the Effects of Lockdowns on COVID-19 Cases
This experiment aims to show which locations are the major reasons for increasing COVID-19 cases in Austria.

## Prerequisites

Prior to running the experiment make sure that the following folders exist in the same folder like the notebook *main_file.ipynb*:

* *raw_data* - Folder to store the external datasets
* *figures* - Target folder for generated plots

## Data Sources

* Entwicklung der täglich neu gemeldeten Fallzahl des Coronavirus (COVID-19) in Österreich seit 25. Februar 2020 (Accessed on 14 April 2021) downloaded from the webpage https://de.statista.com/statistik/daten/studie/1150777/umfrage/entwicklung-der-taeglichen-fallzahl-des-coronavirus-in-oesterreich/
* COVID-19: Google Mobility TrendsCOVID-19: Google Mobility Trends (Accessed on 14 April 2021) downloaded from the webpage https://ourworldindata.org/covid-google-mobility-trends

The cited datasource 'COVID-19: Google Mobility TrendsCOVID-19' has already been added to this repository.

Due the fact that I haven't a Corporate- or Enterprise-Account on https://de.statista.com/, I'm not able to share this datasource. But in order to get this datasoure, please follow these instructions:

1. Go to https://de.statista.com/ an create a free basic account.
2. Use the URL https://de.statista.com/statistik/daten/studie/1150777/umfrage/entwicklung-der-taeglichen-fallzahl-des-coronavirus-in-oesterreich/ to find the regarding dataset (status as of 14th April 2021; it's irrelevant if there is a newer version with a longer time series available, because if you run the code, it will be cut, in order to replicate the results in the documentation).
3. Download the dataset as an excel file into the folder *raw_data* and rename it to 'statistic_id1150777.xlsx'

## Running the code

To run the code in this repository you will need to have access to a machine running python (at least version 3.5) and pip.

Run *pip install -r requirements.txt* to install the required dependencies.

Once the dependencies have been installed, start the jupyter notebook server via jupyter notebook and open http://localhost:8888.

In this repository you'll find the following notebook:

* *main_file.ipynb*: This notebook takes the raw data as input and generates two plots to visualize the time series data and the correlations.

The resulting plots are stored at:

* *figures/covid_19_cases_with_mobility_trends_of_austria.png*
* *figures/correlation_heatmap.png*

## Docker

Run docker *build .* to create a docker image of this repository. The resulting image exposes the jupyter notebook on port 8888.

Boot a docker container via *docker run -i -p 8888:8888 <IMAGE_ID>* to start a jupyter instance. The resulting console output will show the url you can open in your browser to take a look at the code, e.g.

    Copy/paste this URL into your browser when you connect for the first time,
        to login with a token:
            http://0.0.0.0:8888/?token=<SOME_TOKEN>
