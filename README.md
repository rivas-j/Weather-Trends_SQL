# Surfs Up Challenge

## Overview
Our good friend W. Avy lives in Oahu, Hawaii, and needs our help analyzing weather trends to help determine if the surf and ice cream shop business is sustainable year-round. We have already analyzed the precipitation level data to show that Oahu is the perfect place for surfers. The next objective is to analyze historical temperature data for June and December in Oahu. Our primary tools will be Jupyter Notebook and the SQLAlchemy depencency, which will enable us to perform the necessary queries for this analysis

## Analysis
Provide a bulleted list with three major points from the two analysis deliverables. Use images as support where needed.
There is a bulleted list that addresses the three key differences in weather between June and December.

Utilizing the SQLAlchemy depencency in Jupyter Notebook, we were able to import the data from our hawaii.sqlite file and run the following queries to isolate temperate data from every June and December:


```
session.query(Measurement.tobs).filter(func.strftime("%m", Measurement.date) == "06").all()
____________________________________________________________________________________________

session.query(Measurement.tobs).filter(func.strftime("%m", Measurement.date) == "12").all()
```

We then transferred the query results into the dataframes below with descriptive data:

![June Temperatures](https://github.com/rivas-j/surfs_up/blob/303177bd1df2f21eae7b9bb5c77a58a4824ba1ac/resources/june_temps.png)

![December Temperatures](https://github.com/rivas-j/surfs_up/blob/303177bd1df2f21eae7b9bb5c77a58a4824ba1ac/resources/dec_temps.png)

- Not surprisingly, the average temperature in June is warmer than December, by about 3 degrees.
- The minimum temperature in December is lower than June in Oahu, by about 8 degrees. Thankfully this is still feasible weather for winter surfing and ice cream.
- There are many more data points for June weather than December, meaning that we're more confident in the predictive power of the historical temperate data for June.

## Results
Provide a high-level summary of the results and two additional queries that you would perform to gather more weather data for June and December.
There is a high-level summary of the results and there are two additional queries to perform to gather more weather data for June and December

According to our findings, we think Oahu is a great year round setting for your Surf and Ice Cream Shop. There's isn't a lot of variation in Temperature from June to December, there's plenty of good weather to go around!

We recomment the following queries for further analysis:
- Expand the scope of the precipitation data to the last 5 years to gain additional insight into patterns.
- Use a groupby query to determine which months have the lowest precipitation and highest temperatures to determine peak season for the shop. We might need additional staff for that time of the year!
