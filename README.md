# Poetry-Clustering

Problem is we have to make a dataset of poems and try categorizing them in 4 genres using two different classifiers. Training data shall not exceed 1000 poems and 50,000 words in total.
The dataset I have take is from kaggle datasets.
Link of the dataset - https://www.kaggle.com/ultrajack/modern-renaissance-poetry.
The data set have 573 poetry. The total words is about 42 thousands.
Different python libraries have been imported for different purposes.
Libraries used - numpy, pandas, sklearn, nltk, matplotlib, seaborn, subprocess, wordcloud.
There are total 573 rows and 5 columns in the dataset. As we are doing the text analysis of the poetry. We will focus on only one column named 'content' which contains the poetry.

Preprocessing :- 
I have looked at the most appearing words. Love, day, night, dark, etc these were some of the most appearing words.
Some of the words start from capital letter and some with small but the meaning is same. So, I converted all the words to lowercase. So that the model can interpret for example -'HAPPY' and 'happy' as the same words.
Also the punctuations and numbers are not important for the text analysis, so it is better to remove them.
Tokenization - This process splits the strings into individual words called tokens.
Now there are many words which may not be so important but appears a lots of times. For example - a, an, the, don't, won't, there, etc. We want to get rid of these words.
Now I converted the dense data into a sparse data.
Now we need to convert the text data into features. There are 2 methods to do this, bag of words and tf-idf. I have used TF-IDF. TF-IDF works by penalizing the common words by assigning them lower weights while giving importance to words which are rare in the entire corpus but appear in good numbers in few documents.

Training and Classifying¶:-
As asked in the question to try to classify the poems into 4 genre. So, I have applied two clustering algorithms to classify into 4 clusters.
Using K-Means Clustering:
Selecting N Clusters based in Inertia (Squared Distance between Centroids and data points, should be less)¶ After plotting the above plot it is found out that 5 could be an ideal number of clusters. I have used 4 clusters.
Now training is done. 4 clusters are formed. So, we need to give these clusters some name by visualizing the words they contains.
For the cluster number 0 as classified by k-means we see that in the top 25 words there are words like Spring, mountaion, tree, night, eye, ladi etc. So, we can classify this cluster as 'Nature or Beauty' gnere.
Similarly other clusters 1,2 and 3 are named as 'Love', 'Mythology' and 'Others' gnere respectively.
Using Birch Clustering :-
Using this algorithm and visualizing the wordclouds I was able to name the clusters formed as 'beauty & love','nature','miscellaneous' and 'mythology'.
I have tried to classify using both the algorithms. Both the algorithms gave a little different results than one another. But overall, we were able to differentiate between different clusters and named thosed clusters visualizing the wordclouds.¶
At last I have plotted the countplot of the clusters. It was seen that both the algorithms have nearly same type of performance i.e., in both the algorithms' results Love gnere were highest and mythology gnere were lowest.
