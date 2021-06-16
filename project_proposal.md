# Andrei's EDA Project Proposal

## Question

For my exploratory data analysis project, I would like to see if the exit/entry data for the New York City MTA turnstile data can be used to predict the relative population density of different NYC neighborhoods. My hypothesis is that more populous neighborhoods will have higher MTA outflow traffic (entries minus exits) on weekday mornings, as well as higher inflow traffic (exits minus entries) in the evenings, due to residents leaving for work and returning home.

## Data Description

I plan to use SQLAlchemy to ingest the relevant turnstile data. I will use weekday data since that is when most people go to work, and focus on 2019 data to ignore Covid-related effects. Since the turnstile counts are updated every 4 hours, I will use the 4-8am and 8-12am counts for my morning data and 4-8pm counts for my evening data. I will limit my analysis to Manhattan for simplicity. I will also need to find an online source of NYC housing data in order to correlate the population density with the turnstile data.

## Tools

I'll be using SQLAlchemy to ingest the turnstile data and pandas for the data analysis. I will also need a geospatial mapping library such as folium for the city map visualizations.

## MVP Goal

An MinVP goal would be a bar graph of the stations with the highest morning outflows and evening inflows, together with their neighborhoods. A MaxVP goal would be a heat map of station inflow/outflows overlaid on a city map, as well as a similar heat map of population density.