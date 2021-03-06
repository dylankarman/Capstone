# SF Crime Analysis and PdDistrict Classification 

## Data Analysis For the Year 2016


**Author**: Dylan Karman

The contents of this repository detail an analysis of crime data from San Francisco, in 2016. This analysis is detailed in hopes of making the work accessible and replicable.

### Business problem:

Analyzing the crime data from 2016 and seeing where to better allocate resources within the SF Police Department in oder to fight crime more efficiently in the future.

### Data:

https://www.kaggle.com/roshansharma/sanfranciso-crime-dataset

### Column Descriptions:

Category: the category that the crime fits under

Description: A description of the crime

DayOfWeek: the day of the week that the crime was committed 

Date: the date that the crime was committed

Time: the time that the crime was committed

PdDistrict: the district in which the crime was committed

Resolution: what legal action was taken against the person that committed the crime

X: Latitude

Y: Longitude

## Results:

I first performed an analysis of the data using pandas, a built in data analysis library within Python. There was only one missing data point in the entire DataFrame, so I was able to fill that easily and begin the analysis. By graphing the data by their value_counts, I was easily able to see what the data represented visually, and make some assumptions: In the year 2016, San Francisco saw 150,000 reported crimes. 27% (40409/150000) of the crimes reported were in the larceny/theft category. Not surprisingly, the weekend (Friday and Saturday) saw the most amount of crime, accounting for 30% of the crime in these 2 days. New Years Day is the single day with the most amount of crimes by a large margin. New Years Day accounts for 0.3% (558 crimes) of all crimes throughout the entire year, which is quite a lot considering that if you averaged out the 150000 crimes by 366 days (leap year), it equals 0.2% (409 crimes). Almost 150 more! 12:00 (noon) saw the most amount of crime happening. "Most crimes commited in big cities occur during the day, while more violent offenses happen more frequently at night, according to a new study." This makes sense seeing that the vast majority of crimes are minor larceny/theft. This study can be found here: https://www.usnews.com/news/cities/articles/2019-06-12/study-finds-crime-in-big-cities-is-more-likely-during-the-day. When it comes to the resolution, or what the officer does when they get to the scene, is very one sided. Out of 150000 crimes reported in the year, over 100000 of them end up in the 'None' column. Officers are called to the scene and are sent away without having done anything with a legal outcome. October is the month that has the most reported crimes. 

A seasonal decompose algorithm was used on the data to see if there was any seasonality to it. I calculated the rolling mean in order to capture the trend of the data which is very flat. An 'additive' model was used in the seasonal decompose algorithm, because the data was not trending in an upwards or downwards fashion. When the seasonal decomposition was finished, there was a very high seasonal trend.

Classification is a way to predict what may happen in the future based on the correlations made between your data and a target variable. This can be useful knowledge when trying to predict where crimes might happen and placing necessary resources there before it happens. The classification was done on the PdDistrict and the, 'Category', 'DayOfWeek', 'Date', 'Time', 'Resolution', 'X', and 'Y' columns were used as the variables. The categorical values (data represented with words) had to be changed into numbers so that they can be graphed, using a LabelEncoder. The data was then seperated into two DataFrames. One DataFrame only had the target variable (PdDistrict), and the other DataFrame contained the variables. The data is then run through a train test split where 70% of the data was trained on a logistic regression model and 30% was tested on it. When that is complete, the training data is compared with the testing data and a classification report is produced. The accuracy of the model was 87%.

## Limitations and Next Steps:

This data set only included the crime data for 2016, and obviously this limits the data to only that year. Gathering data from previous years would help to be able to predict more outcomes because there is more data for the model to be trained on. 

### For further information
Please review the narrative of our analysis in the Jupyter Notebook and review the presentation.

For any additional questions, please contact **Dylan.Karman@yahoo.com

