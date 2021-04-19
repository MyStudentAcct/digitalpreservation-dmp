# Investigate the Effects of Lockdowns on COVID-19 Cases
This experiment aims to show which locations are the major reasons for increasing COVID-19 cases in Austria.

## Prerequisites

Prior to running the experiment make sure that the following folders exist in the same folder like the notebook *main_file.ipynb*:

* *raw_data* - Folder to store the external datasets
* *figures* - Target folder for generated plots

## Data Sources

* Entwicklung der täglich neu gemeldeten Fallzahl des Coronavirus (COVID-19) in Österreich seit 25. Februar 2020 (Accessed on 14 April 2021) downloaded from the webpage https://de.statista.com/statistik/daten/studie/1150777/umfrage/entwicklung-der-taeglichen-fallzahl-des-coronavirus-in-oesterreich/
* COVID-19: Google Mobility TrendsCOVID-19: Google Mobility Trends (Accessed on 14 April 2021) downloaded from the webpage https://ourworldindata.org/covid-google-mobility-trends

Download these files to the folder *raw_data*

## Running the code

To run the code in this repository you will need to have access to a machine running python (at least version 3.5) and pip.

Run *pip install -r requirements.txt* to install the required dependencies.

Once the dependencies have been installed, start the jupyter notebook server via jupyter notebook and open http://localhost:8888.

In the notebooks folder you'll find the following notebook:

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
