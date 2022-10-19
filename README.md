# Amazon Vine Analysis

## Purpose of Analysis
The goal of this project was to utilize AWS, pgAdmin, postgresql, and pyspark to analyze amazon review data. Amazon Web Service is used to create a database which will be used to insert data into a local postgresql database. The inserted data will be dataframes created off of the original amazon review dataset. After this, the data will be used to find if there are differences in ratings between paid reviews and free reviews.

## Results of Analysis

To begin the analysis of the chosen review dataset, certain requirements had to be met. Products that were reviewed more than 20 times (so that there would be plenty of data) and where over 50% of the votes on the reviews said that the reviews were helpful. Once the dataframe was at this point, two separate frames were made for reviews where the paid vine review system was used and where it was not used. Images of these mentioned dataframes will be found below.

---
### Dataframes
#### Vine DF

<img src="https://github.com/sparrishmatt/Amazon_Vine_Analysis/blob/main/Resources/vine_df.png" width="800">

#### Vote count > 20

<img src="https://github.com/sparrishmatt/Amazon_Vine_Analysis/blob/main/Resources/high_votedf.png" width="800">

#### Positive helpful ratio

<img src="https://github.com/sparrishmatt/Amazon_Vine_Analysis/blob/main/Resources/vote_ratio.png" width="800">

#### Paid Review DF
<img src="https://github.com/sparrishmatt/Amazon_Vine_Analysis/blob/main/Resources/Vine_Y.png" width="800">

(The unpaid review df looks the same as the above paid reviews, but with Vine == 'N')

### Review Results

Do we have enough reviews that land in these categories for us to properly analyze? Let's take a look at some of the counts we find at the start of the analysis. 

<img src="https://github.com/sparrishmatt/Amazon_Vine_Analysis/blob/main/Resources/counts.png" width="800">

There are very few paid reviews, which is to be expected, but our goal is to find out if there is a notable difference in 5-star review percentages so that is what will be done. At first glance without doing any math it seems that the ratios between total votes and 5-star reviews is similar between the paid and unpaid reviews. Instead of breaking out the calculator, we will again use our knowledge of pyspark to find these percentages for use.

<img src="https://github.com/sparrishmatt/Amazon_Vine_Analysis/blob/main/Resources/percentages.png" width="800">

Surprisingly (or maybe not surprisingly?) the 5-star review percentage is actually lower for paid reviews than it is for unpaid reviews. However, the difference in percentages is only about .35%, which is not a lot given the context.

## Summary

To summarize project goals and findings, proper connections and data security were set up in AWS to allow us to connect and insert data into a postgres database through Google Colab and pgAdmin. Amazon review data was cleaned and used to create new dataframes, and then the vine review dataframe was used to build an understanding on review differences between paid and unpaid reviews.

The analysis showed that unpaid reviews have a marginally higher 5-star rating percentage than unpaid reviews. With more work, this analysis could be pushed further to develop some even greater insights into the differences between paid and unpaid reviews .
