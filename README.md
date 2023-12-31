# project-1

UCSD Project 1

## Data Analysis

### **Census**

#### Question: Is there a relationship between migration and  employment rate/poverty for the years 2016 to 2021?

#### API: The reason I choose the ACS API is because it covers a broad range of topics about the social, economic, demographic, and housing characteristics of the U.S. population.

#### The variables used for the table are:   
- employed civilians(B23025_004E), unemployed civilians(B23025_005E), employable civilians(B23025_003E)   
- median household income(B19013_001E), per capita income(B19301_001E)   
- total population(B01003_001E)
- total amount of people moved from different states (B07001_065E)

#### Note: Since DC and Puerto Rico are not states, they are droped

#### Draws a scatter plot with linear regression to find the correlation between the total migration and employment rate from 2016 to 2021
[Average Total Migration VS Average Employed Rate](https://github.com/dumidunipg/project-1/blob/main/Census/Output/Average%20Total%20Migration%20VS%20Average%20Employed%20Rate.png)
- The r-value is: -0.18522171871992268   
- The p-value is: 0.19782779538438497   

From the plot, see that the average employment rate jumps around 40 to 50% while the average total migration from other states changes. Also, since the r-value is -0.18522171871992268, it is pretty close to 0. Conclude total migration and employment rate has no correlation. But the p_value is 0.19782779538438497, it is greater than 0.05. Therefore this data does not provide strong evidence to support the conclusion total migration and employment rate have no correlation.

#### Draws a scatter plot with linear regression to find the correlation between the total migration and median household income from 2016 to 2021
[Average Total Migration VS Average Median Household Income](https://github.com/dumidunipg/project-1/blob/main/Census/Output/Average%20Total%20Migration%20VS%20Average%20Median%20Household%20Income.png)
- The r-value is: 0.0593554745173882   
- The p-value is: 0.6822077337202334     

From the plot, see that the average median household income jumps around while the average total migration from other states changes. Also, since the r-value is 0.0593554745173882, it is pretty close to 0. Conclude total migration and median household income has no correlation. But the p_value is 0.6822077337202334, it is greater than 0.05. Therefore this data does not provide strong evidence to support the conclusion total migration and median household income have no correlation.


### **Crime**

#### Question: Is there a relationship between crime and migration?

#### API: The API used to compile the crime data comes from the FBI Uniform Crime Reporting (UCR) program. Different agencies submit data which is compiled into counts of crime offenses by location.

#### While parsing through the parameters offered by API and looking at the data for one state, there were a few types of crimes that were reported which in the earlier years of the period from 2016-2021 that stopped being reported in the later years, for example drunkenness. There were also a few categories of crimes where it seemed very specific and most of the data within the period for all states was 0. These categories were dropped when choosing the types of crimes to delve into. 

#### Looking into the Crime trends for the United States within 2016-2021 compared to Migration trends [figure](Crime/Output/Migrations_Crimes_Trends.png), we are able to see that migration is stead throughout the years but there is a sudden drop in 2020 (possibly due to the pandemic). However, crime has been dramatically decreasing in numbers according to this data. 

#### The year with the most migration was 2019. When we look at the [bar graph](Crime/Output/2019_Crime_Migration_Bar.png) comparing crimes and migration for each state in 2019, it appears that the larger states have higher crime. The state with the highest crime being California compared to the migration in and out of California for that year.

#### The year with the most crime was 2016. When we compare the years of 2016 and 2019 as displayed in this [figure](Crime/Output/2016_2019_Crime_Migration_Bar_Comparison.png), we see a trend of mostly  crimes decreasing  as migration increases, some states where this is an exception are Iowa, Kentucky. In these states migration stayed consistent between 2016 and 2019, but crime increased. 

#### An interesting visual to look into is the total crime per total migration ratio per state over 2016-2021, plotted on the U.S. map. From this visual we are able to see that based on the crime to migration ratio, it is not just the large states that experience higher crime rates. 

#### But is there a relationship between crime and migration?

- From regression analysis, we see that there is a strong positive correlation between crime and migration with the correlation betweeen crime and migration from 2016-2021 being 0.89. When we observe the correlation between crime and migration for each year, we see 2016-2018 starting off with a very strong correlations of 0.9. However, we see the correlation between the two factors dipping in 2019 to 2021 with 2021 having a very weak correlation of 0.68 between crime and migration. 

- [Reference figure 2016](2016_Crime_v_Migration.png)
- [Reference figure 2018](2017_Crime_v_Migration.png)
- [Reference figure 2018](2018_Crime_v_Migration.png)
- [Reference figure 2019](2019_Crime_v_Migration.png)
- [Reference figure 2020](2020_Crime_v_Migration.png)
- [Reference figure 2021](2021_Crime_v_Migration.png)

The p-values for each year as well as all years are well below the 0.05 threshold which indicates that these results are statistically significant.

- p-value for the total period (2016-2021): 1.12e-17
- p-value for 2016: 1.98e-18
- p-value for 2017: 2.24e-18
- p-value for 2018: 3.41e-18
- p-value for 2019: 9.63e-14
- p-value for 2020: 6.47e-12
- p-value for 2021: 6.97e-08

- Looking at the standard of error, we see for the most part that these values are close to 0 which indicates that there is low deviation of the error of the regression models. Most of the observed values for each year between 2016 and 2021 fall between 0.08 and 0.12 from the regression line. 

#### Overall, there seems to be a strong positive correlation between crime and migration, however this relationship seems to be weakening over the years. We can conclude that there is a relationship between crime and migration. 

### **Services**

#### Question: Is there a relationship between popularity and migration in the US between 2016 and 2021?

#### As a short, but important, note, I want to clarify the *popularity index* that I use for this analysis.

- It is not documented in `apidocs.geoapify.com`, but some of the results from the Geocoding API include a keyword called *popularity*.
- As highlighted in `www.avuxi.com/what-is-geopopularity`, this [figure](Services/Figures/popularity_index.png) illustrates that the popularity of a place or service is influenced by social media posts, photos, reviews, public APIs, and online crawling through informative websites related to it.
- It could also be summarized as the amount of *buzz* or number of *keyword* searches on the internet.
- This is not the exact index included in the Geocoding API responses, but it is a fair reference to its meaning to understand the results of this data.

#### 

#### The categories were chosen based mostly on the number of usable data, as *childcare*, *education*, and *healthcare* would have been my top categories if not for the lack of usable data from the responses. I added *beach* to my search, but data was missing for more than half of the states, so it was dropped from the Dataframe. Here is the list of categories and descriptions for reference: [Category Descriptions](Services/category_descriptions.md)

#### After viewing the [Popularity Indices by State bar graphs](Services/Figures/popularity_by_state.png), we can generally conclude that:

- Maryland has the highest popularity index in the commercial, religion, and production categories and is not far off from the top in the service category.
- Similarly, New Jersey has the highest popularity index in the service and tourism categories and is fairly popular in the leisure category as well.
- Florida has the highest popularity index in the leisure category and is consistenly above the 75th percentile in the religion and tourism categories.
- Alaska, Michigan, South Dakota, and Utah are below the 25th percentile in leisure, which indicate that those states are unpopular choices in terms of leisure.
- Texas is seemingly most popular in the religion category, then tourism, and is relatively unpopular in the production and leisure categories.

#### After viewing the [Popularity vs Average Total Migration scatter plots](Services/Figures/scatter_popularity_migration.png), we can generally conclude that:

- The popularity of service and leisure categories have a weakly negative relationship with the average total migration between states, so people who migrate do not consider or value the popularity of public services or parks in a given state. However, we cannot be confident in this conclusion as only 0.0037% and 0.0481% of the variability observed in the service and leisure categories, respectively, is explained by the linear regresion model.
- The popularity of commercial, religion, and tourism categories have a weakly positive relationship with the average total migration between states, so people who migrate weakly consider or value the popularity of, for example, supermarkets, religious institutions, or tourist attractions in a given state. However, we cannot be confident in this conclusion for the commercial and religion categories, as only 0.6362% and 2.1894%, respectively, of the variability observed in each category is explained by the linear regresion model. 
- In contrast, with the highest r-squared value of 0.07, the p-value for tourism is 0.0564, which is close to the value where it is considered statistically significant. With a slightly higher threshold for the p-value of 0.06, we can reject the null hypothesis and conclude that there is a statistically significant and positive relationship between the popularity of the tourism category and migration between states in the US.


### **Transportation**

- Write analysis here

## APIs Used:

### Census API

- https://www.census.gov/data/developers/data-sets/acs-5year.html

### Crime API

- https://www.justice.gov/developer

### Places API

- https://apidocs.geoapify.com/docs/places/#about

### Geocoding API

- https://apidocs.geoapify.com/docs/geocoding/forward-geocoding/#about

## Code Sources and Locations:

### **Census**

#### Find the Variables:
- https://api.census.gov/data/2019/acs/acs5/groups.html
- https://gist.github.com/afhaque/60558290d6efd892351c4b64e5c01e9b

### **Crime**

#### Unpacking Tuples: 

- https://www.geeksforgeeks.org/python-check-if-variable-is-tuple/#
- https://www.pythonmorsels.com/tuple-unpacking/

### **Services**

#### `iterrows()` Function and Loop Setup:

- `airports_solution.ipynb`

#### Break Multiple For Loops:

- https://stackoverflow.com/questions/6346492/how-to-stop-one-or-multiple-for-loops

#### `np.isnan()` Variable and Logic with NaN Boolean Values:

- https://stackoverflow.com/questions/41342609/the-difference-between-comparison-to-np-nan-and-isnull

#### `.at` Property for Dataframe Navigation:

- https://stackoverflow.com/questions/64682028/numpy-float64-object-has-no-attribute-fillna-when-filling-nan

#### `**font` Keyword Argument:

- https://stackoverflow.com/questions/21321670/how-to-change-fonts-in-matplotlib-python

#### Creating Subplots and Labeling Them:

- https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html

#### Available Colors for Figures:

- https://matplotlib.org/stable/gallery/color/named_colors.html

#### Adding Links in Markdown File:

- https://www.markdownguide.org/basic-syntax/

### **Transportation**

#### WRITE DESCRIPTION HERE

- Write sources here
