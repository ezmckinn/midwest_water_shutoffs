## Summary 

Primary data analysis for this project was carried out in May 2020. Results of this analysis can be viewed in a Carto map at [bit.ly/midwest_H20](https://mit.carto.com/u/ezmckinn-mit-webmap/builder/ffb88b57-39be-41b0-af63-614b9f3c8b64/embed). This file explains the data analyses and file formats for each of the data outputs for the project on water shutoffs across cities in the midwest. The filename endings listed below would be appended to the name of a city (e.g. — the shutoffs file for Chicago will read 'chicago_zip_year_shutoffs.csv').

# Files

*<cityname>_shutoffs_summary.geojson* 

a geojson with the total number of shutoffs, by zip code, over the entire range. The shutoffs count (SHUT) is a SUM over the date range.The ACS estimates are a mean of the 5-year acs estimates, for each zip code, for each year. The way to interpret this data is to say the total number of shutoffs over the period vs. the mean of ACS value x. 

*<cityname>_zip_year_shutoffs.csv* 
 
A .csv with the the number of shutoffs and 5-year ACS estimate value for each zip code, in each year. This was used to make the shutoffs_summary.geojson file by grouping by zip code and averaging across years.

*<cityname>_data_clean.rmd* 

The R script used to get ACS data, clean it, a well as upload the raw shutoffs data and clean it, to produce the two files above.

*<cityname>_analysis.rmd*

The Red file used to analyze the geojson and produce the contents of the results folder. 

**Results**

Outputs include: 

*<city>_AIC_comparison.csv*

This file compares the spatial lag models, spatial error models, and OLS regression. The lowest AIC is the most effective model. 

*<city>_err_1.html*

This is the summary output for the spatial error model. 

*<city>_lag_1.html*

This is the summary output for the spatial lag model. 

*<city>_majmin_t_test.csv*

This is the summary output for the t-test, testing whether the difference in mean between majority white and majority non-white zip codes is significant

*<city>_ols_1.html*

This is the summary output for the ordinary least squares regression model, regressing % non-white population and median household income on the number of shutoffs. 

*<city>_shutoffs__hist.png*

This is a visualization of the log-adjusted number of shutoffs, by zip code, comparing majority white to majority non-white districts.

*<city>_summary_stats.csv*

This is a summary table of the number of shutoffs by zip code, across majority white, non-white, and all zip codes.

<city>_interpretation.txt 

This is a text file analyzing the model results. 
