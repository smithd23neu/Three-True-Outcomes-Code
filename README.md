Credits: Daniel Smith (smith.daniel3@northeastern.edu), Maya Ellis (ellis.may@northeastern.edu), Julianne Conlee (conlee.j@northeastern.edu), Lucas Rouaix (rouaix.l@northeastern.edu)

Introduction to Data
	The data that we decided to utilize came from Baseball Reference, one of the most respected data tracking companies in baseball. 
From their website, we were able to access the players’ data, where we honed in on hitter data from the 2014 to 2024 seasons, excluding the 2020 season, 
which was shortened due to Covid-19. The data was collected ethically, as it is collected with the consent of the players and is widely accessible within the public domain. 
Given that all players sign contracts and these data affect their salaries on these contracts, we see no issue with the MLB’s usage or collection of this data as it is central to the sport’s operations. 
  However, some biases are present in our analysis. First, by excluding the 2020 season, we may have missed out on certain trends specific to that year. 
Additionally, our focus on hitter data means we do not account for pitcher performance, which could be a key factor in understanding the overall effectiveness of Three True Outcome batters. 
We also acknowledge the influence of external factors; there are many confounding variables which make it hard to come to a causal conclusion. 
For instance, over different seasons of baseball, the consistency of the ball has been changed, with seasons such as 2019 having a bouncier ball, which likely increased home run rates.
The rise of sticky tack, a substance used by pitchers to increase their control around 2021 similarly led to an increase in strikeouts. 

Data Science Approaches
	Our project consists of a variety of techniques and processes. The first notable algorithm applied was Principal Component Analysis. PCA is applied in order to transform the original features of the dataset into components that capture the variance in the data. We decided on strikeout percentage, walk percentage, and home run percentage as our features, given these stats determine whether the player is a “Three True Outcome Batter”. Along with PCA components, we calculated the PCA loadings for our three features for each year in the dataset. The PCA loadings tell us the weight that each feature has on each of the PCA components, which allows us to better understand what PC1 and PC2 represent. In our project, we found that PC1 was heavily determined by strikeout percentage, while walk percentage was heavily weighted for PC2. This trend continued across all ten years in our dataset.
The next important algorithm we conducted was KMeans Clustering. KMeans Clustering is an efficient way to group data into clusters of similar observations. This allows us to understand the spread of our dataset and identifies categories and potential outliers. In the case of our project, KMeans Clustering is essential in grouping the different types of hitters into their respective categories, allowing for the identification of 3OBs. We started by finding the optimal K by plotting inertia values and pinpointing the value at the elbow, which turned out to be 5. Using this K value, we plotted the clusters for each year in our dataset. The 2014 graph is included below for reference.

	This graph shows the five clusters of hitters in 2014. Using these clusters, we calculated the cluster mean and subsequently identified the player closest to the center using Euclidean distance, which measures the difference between a player’s performance and the average performance of their cluster. From there, we were able to determine which cluster’s average player had the highest sum of stats (SO% + BB% + HR%), which showed which cluster contained the 3OBs. This made way for us to figure out the number of 3OBs per year and finally make our conclusion.
	Overall, the algorithms discussed above were instrumental to finding and visualizing the answer to our problem statement. To support these analyses we created a dataframe from our dataset and updated it throughout the duration of our project by adding columns to show additional stats. We also created new dataframes using components of the original dataframe. In order to visualize our data, we created several plots and graphs to display potential trends and clarify our results. Furthermore, most of the non discussed calculations executed in our project were in relation to finding percentages and mean values, as well as normalizing player stats to account for differing numbers of plate appearances. 

Results and Conclusions

The results show that the amount of 3 outcome batters does increase overall, but there have been several years which brought the number of 3 outcome batters down. 
The first major drop was in 2018, due to the introduction of deadened baseballs. In the years leading up to 2018, there was an increase in the amount of home runs, with the 2017 season setting the record for the amount of home runs. The MLB sought to reduce the amount of home runs by reducing the ball’s bounciness. The MLB continued to experiment with the ball until they were fully implemented in 2021. The drop in 2018 can only be partially attributed to deadened balls, as pitching strategy did change this year as there were a record number of strikeouts. In 2021 there was a league-wide adaptation to deadened balls, with hitters focusing on putting the ball in play,  which explains the second major cliff in the graph. 
While the deadened balls did temporarily decrease the number of 3 outcome batters, they still gradually increased year by year. The shift in 2023 can be attributed to yet another rules change, where the MLB limited the possibility of defensive shifts. These are ways players can adjust their positions to a specific batter to target their weaknesses. By limiting what players can do for defensive shifts, it encourages more balls in play which disincentivizes 3 outcome batters. The drops in 3OBs are primarily due to regulatory changes, and unless new rules come out for the 2025 season, we predict an increase in this style of play. 
It is crucial to look at the impact 3OBs have made in terms of runs.

This data is not suitable for linear regression because of many regulatory changes in the MLB since 2014. It does however show an overall struggle between the increasing efficiency of batting versus the viewership oriented MLB who is trying to reduce the amount of 3OBs, which many viewers find boring to watch. We believe that these batters will continue to chase optimization and the MLB will respond in suit.