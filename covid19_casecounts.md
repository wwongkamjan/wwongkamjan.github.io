## Covid-19: Data Visualization and Forecasting

**Project description:** Covid-19 has been a big impact to our human since the start of 2020. Number of infected cases has been high and low overtime, never went to zero or lower than 10 since the start.  

With this data visualization, you will see the number of active and cumulative as of date (which you can select from parameter) by country. Also, you will see those number in time series graphs which you can select 2 countries to show as need.

Lastly, I have prediction over 10 days in the last of the dashboard. It was shown as a forecast line which Tableau automatically generate it from existing data.

<br>
### The Dashboard

<iframe seamless frameborder="0" src="https://public.tableau.com/views/Covidtableonly/Covid19countbyregions?:embed=yes&:display_count=yes&:showVizHome=no" width = '800' height = '800' scrolling='yes' ></iframe>  

<br><br>
### A Guide: How to use it?
Start at the first page, this page mainly presents 4 numbers:
* Active Cases Count
* Cumulative Cases Count
* New Death Count
* Cumulative Death Count

These numbers can be shown one at the time. With parameters in below pictures, you can specify which number you want to see.
<br>
<img src="images/covid19_page1_1.JPG?raw=true"/>

#### Parameters:
* By Measure (Cases Count, Death Count)
* Cumulative or Active/New
* Top (Integers as an input, this page will show only Top N regions of the number)
* Data As of Date (We dont want to sum of cumulative counts in different days, that's the reason why we can see data as of specific date) 

#### Example of using parameters
<img src="images/covid19_page1_4.JPG?raw=true"/>
<img src="images/covid19_page1_5.JPG?raw=true"/>
<br>
In this example, I selected "Top 2" (from Top) by number of "Cumulative" (from Cumulative or Active/New) "Death Count" (from By Measure) 
You can see that my selection has an effect to the table below the map. You can try using these paremeters, which tables will dynamically show data of Top N regions. 


<br>
Link to [Tableau](https://public.tableau.com/profile/wichayaporn.wongkamjan#!/vizhome/Covidtableonly/Covid19countbyregions).
