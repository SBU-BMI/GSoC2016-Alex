# Google Summer of Code 2016 | Open Health: SPARCS data interactive visualization

Sourcecode: https://github.com/SBU-BMI/GSoC2016-Andrey

Live app: https://sbu-bmi.github.io/GSoC2016-Andrey

Report: https://goo.gl/iXxzJ4

### Goal
This app is interactive visualisation of SPARCS data.
> SPARCS is short for Statewide Planning and Research Cooperative System, a system collecting patient level data from hospitals. 
Visualization presents inpatient deidentified dataset of discharge level detail on patient characteristics, diagnoses, treatments, services and charges. Does not contain protected health information. Data sources: 2009, 2010, 2011, 2012, 2013, 2014. Currently presented data sources contains contains sample data. Actual datasets contain more than million records for each year, and are subject for further development. 

### Technologies
Main technologies used are:
- [dc.js](https://dc-js.github.io/dc.js/) - dimensional charting javascript library 
- which relies on [d3.js](https://d3js.org/), data processing and visualization library
- and [crossfilter.js](http://square.github.io/crossfilter/), which provides multidemensional filtering of datasets.
- of course, standard HTML/CSS/Javascript used
- Javascript's [Promises](https://www.promisejs.org/) are worth separate mention because of their significant role in this app

### Usage
##### Parameter input from UI
User selects county and limit (amount of records to load from each year) in appropriate dropdowns, 
and presses "Load" button, then download requests are being sent to health.data.ny.gov server.
After successfull download, data are represented in charts.
##### Parameter input from URL
Desired county can be enetered not only from UI, in dropdown,
but also in URL - appending app address with ````"?county=<YOUR_COUNTY>"```` parameter,
for instance, 

````https://sbu-bmi.github.io/GSoC2016-Andrey/?county=Suffolk````

Then data for just Sufolk county will be downloaded.
Selection in dropdown will be upated as well to show "Suffolk".
##### Interactive and synchronised filtering
Charts are interactive - user can filter out required subset by just selecting any bar in barchart, or sector in pie-chart;
in barcharts range can be selected. After enabling filter in one chart (selecting something in one chart), 
this filter is being aplied to all other charts too - they show just data for selected subset.

