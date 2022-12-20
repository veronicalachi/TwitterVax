# TwitterVax
TwitterVax is a collection of 9'068'389 italian tweets on vaccines tweeted from 1st January 2019 to 1st June 2022. TwitterVax contains three folders: 

-TweetsTexts contains 41 files .csv, one for each month in the period from January 2019 to June 2022. In each file, each row represents a tweet that has been tweeted in the month under consideration. Each file has the followwing 10 columns:

	-id: is the id of the tweet.
	-author.id: is the id of the user that has tweeted the corresponding tweet.
	-referenced_tweets: is empty if the tweet is an original one; if the tweet is a retweet or a quote or a reply, this column contains a dictionary with        keys “type” and “id”; the value of “type” can be “retweet”, “quoted” or “replied_to” whereas the value of “id” is the id of the original tweet of which    the corresponding tweet is a retweet, a quote or a reply. 
	-type: is “retweeted” if the corresponding tweet has been retweeted at least one, empty otherwise.
	-author.username: is the username of the user that has tweeted the corresponding tweet.
	-author.public_metrics.followers_count: number of followers of the user.
	-author.public_metrics.following_count: number of users followed by the user.
	-author.public_metrics.tweet_count: number of tweets tweeted by the user.
	-author.verified: is False if the user is not verified, True if the user is verified.
	-text: text of the tweet.

-RetweetNetworks contains 41 files .csv one for each month in the period from January 2019 to June 2022. Each file is an edgelist of a graph. In each graph, the nodes represent the active users of the platform in that period, while edges connect users that have retweeted each other at least once. Every row of the file represents an edge of the graph. For each row, the first column is the author.id of the user that has retweeted at least once the user whose author.id is in the second column. 

-Communities contains 41 files .csv one for each month in the period from January 2019 to June 2022. Each file .csv results from a community detection procedure applied to the corresponding graph in RetweetNetwork. Each file has 2 columns. The first column contains the author.id of the users that correspond to the nodes of the largest connects component of the graph. In the second column there is 1 if the corresponding user has been classified as No-Vax, 0 if the user has been classified as Pro-Vax.

