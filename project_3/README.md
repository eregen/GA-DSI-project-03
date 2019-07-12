# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & Classification

### Executive Summary

### Problem Statement

Reddit hosts threads on a massive variety of topics within their own categories.  I'm proposing
to train a classifier to distinguish between two wildly popular yet very different video game franchises:
God of War and The Legend of Zelda.  Both have enjoyed massive success and critical acclaim,
but the former is well known for violent enough to warrant an M-rating for every one of it's titles,
and the latter is whimsical and child-friendly.  Both also have their own lore and words unique to their
respective series.  I have selected two subrredits devoted to these series that consist mostly of text, 
as some subreddits consist mostly of pictures and video clips. 
	Before I start building models howeverI have to: first, scrape reddit for the data; second, clean
and format the data; and third, vectorize the cleaned text columns. I will use CountVectorize for this.
	After retrieving, cleaning, and processing the data, I will remove certain columns,
including the 'target' column, of course, from a 'features' list. The 'target' column, 
which contains a 1 or 0 (1 representing that the post came from theGod of War subreddit and 0 
representing that the post came from the Zelda subreddit), will be used as our y.
	Next, we will split the dataset into two: a training set, and a testing set.  By using
sklearn's train_test_split, we can check the results of our model when run on 'unseen' data,
giving us a more realistic test of the model's predictive power.
	Finally, we will run our data through the modeling process.  We will use four different
classification models: Logistic Regression, K Nearest Neighbors, Random Forests
and Naive Bayes.  I will also run the first three models through a gridsearch,
to tune hyper paramaters for each model to get a better feel for how well individual models may perform.
	Once all models have fitted, I will evaluate their accuracy scorings, find the strongest
performing model and declare it the model most worth pursuing further.


What I found was that the best performing model was Logistic Regression.  I Gridsearched
it and some of the parameters were: C = 1.3, penalty = L1.
	As I hypothesized these two subrredits don't have much overlap.  Since they are so different,
they were fairly easy to classify. In light of this I decided to remove certain words 
With this being the case, we decided to handicap the model, in a sense, by removing certain
words from the features.  This includes: Zelda, Legend, Kratos, God, and War.  
	After penalizing the model I still got very good accuracy for my models.  Logistic Regression did 
best with a Traning accuracy of 1.0 and a Test accuracy of 0.93. I also got a strong performance from
Random Forrests and Naive Bayes.  The former had 0.999 accuracy on the training set and 0.914 for the 
testing set, while the latter got 0.998 for the training set and 0.911 for the testing set.
having a Train Set Accuracy Score of .999 and a Test Set Accuracy Score of .950. The K Nearest Neighbors 
performed poorly, with a Train set accuracy of 0.709 and a Test set accuracy of 0.637. 
	In the future I'd like to see how these models work on different pairs of subreddits and
compare results.  Does the model work well on the GodofWar/Zelda subreddits,
or does it also work well on other subreddit pairs?

We recommend that reddit use my model to differentiate God of War reddit posts and Legend of Zelda posts.
The model works fairly well, but it will still misclassify 7 out of 100 posts. There is still room for 
improvement and I'd like to see how a Logistic Regression model would perfrom on a term frequency-inverse document frequency
vectorized dataset. 