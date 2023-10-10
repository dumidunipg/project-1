# project-1

UCSD Project 1

## Data Analysis

### **Census**

- Write analysis here

### **Crime**

- Write analysis here

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
- Simply put, an increase in popularity of tourist attractions in a given state increases the average number of migrations into that state between 2016 and 2021.

### **Transportation**

- Write analysis here

## APIs Used:

### Crime API

- https://www.justice.gov/developer

### Places API

- https://apidocs.geoapify.com/docs/places/#about

### Geocoding API

- https://apidocs.geoapify.com/docs/geocoding/forward-geocoding/#about

## Code Sources and Locations:

### **Census**

#### WRITE DESCRIPTION HERE

- Write sources here

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

### **Transportation**

#### WRITE DESCRIPTION HERE

- Write sources here
