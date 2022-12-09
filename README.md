# King County Housing

# **Author**: Josh Palgon

## Overview

Hugh Honey and Vic Vinegar have decided to expand Honey and Vinegar Real Estate into King County. I have been tasked with helping Hugh and Vic navagate the King County market and maximize profits. In order to maximize profits I am going to look at which features impact the price of a King County home the most. The data source provided is from Kaggle and contains King County housing data from May 2014 until May 2015.

The two main issues for cleaning the data set was converting all the object data types into a numeric data type and imputing or removing missing data. My goal was to remove as little data as possible and carefully imputing data in the most accurate way.

Sqft_living had the highest correlation with price. Waterfront: $608,976, grade_value: $99,787 and view: $68,547 were three of the highest coefficients in my baseline model. After running my model, I compared the actual price vs my predicted price. I looked at the highest values of my predicted price subtracted by the actual price to find what actual prices may be undervalued. Waterfront, view, and the zipcodes: 98010, 98118, 98146, 98122, 98033 were the most undervalued. My recommendation for Honey and Vinegar real estate would be to focus on houses that maximize sqft_living, have high grade_values, and have a waterfront, view, or are in the 5 undervalued zipcodes.

## Business Problem

Hugh Honey and Vic Vinegar want to take their real estate prowess to King County. However, as Philadelphia residents they are not familiar with the area and would like guidance on how to conquer King County and maximize their profits for their newly founded western branch.

In order to maximize profits, Hugh and Vic need to sell as many houses as they can. Additionally, if they accurately provide their customers with homes that grow in value, they can build a reputation of making their customers happy in both the short and long term. This will help drive more customers to choose Honey and Vinegar Real Estate.

## Data

The Kaggle dataset provided was the King County Housing Data (`kc_house_data.csv`) from May 2014 until May 2015.

Cleaning the data came with two main tasks: converting all of the object data types to a numeric data type and imputing or removing missing data. All but one feature were converted to a binary or ordinal scale and some were converted both ways (ex view) to see if the binary or ordinal scale of having a view mattered more.

In order to imputing the missing data in the best possible way I dug into each of the columns to determine the best course of action. For some features, I took the most common value (yr_renovated), for others I used a scale of a correlated ordinal or binary scaled feature to best impute the missing values, and another I was able to replace the entire column of values by making a calculation from two other features (sqft_living - sqft_above = sqft_basement).

In the end I only had to remove one outlier row where bedrooms was equal to 33. Other than that single row I was able to impute for all missing values and keep all existing rows.

## Methods

After merging our data and performing initial analysis, we realized that there were signficant outliers within the horror genre. The titles 'The Devil Inside' and 'The Gallows' had small budgets with relatively large revenue, but after researching these two films, we learned both films made all of their money during the first week at the box office and then were complete failures. We decided these movies were atypical and not representative of our data as a whole. In a similar fashion, we discovered that the 3 movies in our data set from 2020 had no revenue information, despite a cursory web search revealing that these movies had indeed made money. Presumably, our data was missing this information, so we decided to drop the few titles that we had from 2020.

As part of our analysis, we grouped our data along each of our categorical variables. We began by analyzing Median/Mean ROI with respect to genre, director, and writer individually. We then analyzed the distribution of ROI by genre, as well as a breakdown of successful directors and writers by genre. We also looked at how median ROI by genre changed from year to year to analyze the trend of each genre across time.


## Results

### Median ROI by Genre
![Median ROI by Genre](./images/median_roi_by_genre.png)

Animation, mystery and sci-fi are the top performing genres from 2010-2019.

### Top Genres by ROI Over Time
![Change in ROI by Genre](./images/change_in_roi_by_genre.png)

However animation has not been trending well, while mystery and sci-fi are still performing strong at the end of the timeframe. 

Horror and thriller are trending upward despite not being top 5. 

### Top Directors
![Top Directors by Genre](./images/top_directors_by_genre.png)

David Lowery is the top performing director and writer, despite being in the fantasy genre, which is not top 5.


If any of these graphs are hard to look at due to the web browers settings please look at our full analysis in [our Jupyter Notebook](./notebooks) or our [presentation](./Movie_Presentation.pdf).

## Conclusions

Microsoft should invest in mystery and sci-fi movies due to their high median ROI and recent upward trend. Although animation has been doing well, it appears to be on a downward trend, so we do not recommend that Microsoft invests in this genre at the point.

Horror and thriller movies should be monitored due to their recent growth, if they continue to show growth, Microsoft should consider investing in these genres.

David Lowery is the highest performing director and writer, so Microsoft should consider making a fantasy movie spearheaded by David Lowery.

For the future, we would like to gather more data to fill in some of the gaps in our data set. Our data has many different naming conventions that made merging difficult, and it would be prudent to look into the `FuzzyWuzzy` Python package to utilize fuzzy logic to increase title match rates. We would also like to get the most recent years of data as our data only contained entries up to 2019.

Other variables we would investigate include parental guideline ratings and user ratings. One of our data sources had parental guidelines but no titles, making it impossible to merge to our overall dataset. Parental guidelines may determine overall viewership population, while user ratings could help determine the popularity of a genre and the current trend of which genres hold the most public favor.


## For More Information

Please look at our full analysis in [our Jupyter Notebooks](./notebooks) or our [presentation](./Movie_Presentation.pdf).

For any additional questions, please contact:

<ul>
    <li>Josh Palgon (jopalgon@gmail.com)</li>
