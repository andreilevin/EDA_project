# Analysis of Local Work-from-home Trends from NYC Subway Turnstile Data 

Our client, Necessary Supplies For Work-from-home (NSFW Inc.) sells a range work-from-home supplies such as standing desks, external monitors, and lumbar support pillows. With the pandemic-related increase in work-from-home rates, they are interested in finding out which specific NYC neighborhoods have seen the largest work-from-home rate increases, in order to try to more precisely target those areas with NSFW product sales.

## Design

As a proxy for work-from-home rate increases, we looked at changes in weekday morning commuter rates on all stations in the MTA database.  By comparing two months of data from spring 2019 with the same two months in spring 2021, we were able to explore differences in morning weekday ridership and use that to infer potential neighborhoods with increased work-from-home rates.

## Data

We used the MTA turnstile dataset, publicly available at: http://web.mta.info/developers/turnstile.html   This dataset includes entry and exit counts for each turnstile in every station of the MTA, summed approximately every four hours and updated weekly.

## Algorithms

We performed a thorough exploratory data analysis of the MTA turnstile data, primarily using the python pandas library.

## Tools

* SQL for ingesting the turnstile data into a local database
* SQLAlchemy for extracting the database into Python
* Pandas for data cleaning, filtering and aggregation
* Matplotlib and Seaborn for plotting 

## Communication

After taking the daily averages for the pre-pandemic and post-pandemic ridership, we came up with a list of the top 20 stations by net decrease in daily turnstile entries:

However, one can see many commuter hubs in this list,  such as Penn Station and Port Authority.  In order to select primarily residential neighborhoods  we applied three filters on our station data:

* Removal of stations with an abnormally large number of daily entries  
* Removal of stations with an abnormally large number of MTA lines  
* Removal of stations where daily exits exceed daily entries.  

<img src="https://raw.githubusercontent.com/andreilevin/EDA_project/main/figures/fig5.png" 
      title="results_unfiltered" width="400"/>

After this filtering step, we sorted the stations on two metrics: net number decrease of daily entries and net percentage decrease of daily entries.  We found 7 stations that were in the Top 20 of both metrics, and we would recommend their immediate neighborhood as potential candidates for targeted NSFW sales:

<img src="https://raw.githubusercontent.com/andreilevin/EDA_project/main/figures/fig10.png" 
      title="results_filtered" width="400"/>

