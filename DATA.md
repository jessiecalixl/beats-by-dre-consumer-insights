# Data Description

## Data Sources

The dataset is composed of 1077 Amazon reviews where two products were Beats earbuds and then 9 competitor products. The dataset's columns were review ID, product ID, title of the review, author, the content of the review, the date posted, profile ID of the author, a boolean variable that indicated if the review was verified or not, a marked-as-helpful count, and product attributes.


## Data Collection

o collect reviews, we used Oxylabs, an efficient web scraping tool. Initially, our goal was to scrape reviews from one Beats by Dre product and four competitor brands. However, Oxylabs had a limitation of scraping only 100 reviews per product and we needed more data for a robust analysis. To overcome this limitation, we expanded our scope to include an additional Beats product and five more competitor products, resulting in reviews from a total of 11 products.

We scraped a total of 1,077 reviews, which were saved in JSON format, with each product's reviews stored in a separate file. To prepare the data for analysis, we converted each JSON file into a dataframe. Then, we merged all the individual dataframes into one, combining all the reviews into a single, large dataset ready for further analysis.


## Data Cleaning

For cleaning and preprocessing the data, I followed a few steps:

1. Renamed the columns to have a name that gave a more clear representation of what they each display.

2. Checked for duplicates and deleted them. There were only 9 so my dataset went from 1086 cases to 1077 cases.

3. Missing values were only found in the column Product Attributes. After finding which product ID/Brands had missing values and how many they each had, I decided to impute. For the Apple product, I imputed manually the product attrbitute to be the products color because all the 100 reviews had it missing. For Raycon and Tozo, I decided to impute the most frequent product attribute value for each because they had only a few missing values.

4. Added the Product Price column because I thought it could lead to valuable insights. Also further in my analysis I wanted to divide my competitor products to premium products/brands with which I would compare Beats and more affordable products/brands with which I would find the features and qualities of earbuds that people value the most.

5. Transformed the Date column to datetime format for potential time series analysis.

6. In the numerical columns, looked for outliers. Helpful Count had the most outliers that could impact future analysis. The most frequent values were 0 but then some of them could reach up to 200 or more. To handle these outliers, I capped the variable to be displayed in a scale of 1 to 5.
