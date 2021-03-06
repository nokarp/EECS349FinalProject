# Instagram Popularity Predictor
### By: Noah Karpinski and Timothy Mwiti
#### Contact: noahkarpinski2019(at)u.northwestern.edu, timothymwiti2019(at)u.northwestern.edu
#### EECS 349 Northwestern University

#### Abstract
Our task was to predict if an Instagram Post will successfully reach and interest the audience it is meant for. We define the specification ‘successfully reach and interest the audience it is meant for’ in relation to how many likes a post gets relative to the number of followers. This means that if a post gets a given ratio of likes to followers. This ratio depends on what performance the user need and can change. Our inputs were components of an Instagram posts such as the caption length, is the post a video or photo, hashtags, tags (mentions) and the number of followers the account holds. Our output was whether a post will successfully engage the audience or not. For our task we took the ratios as 0.02 for photos and 0.038 for videos. We chose these number since posts with this performance were in the top quartile of the data. The algorithms that we ran our data on and will be reporting on are Zero R, J-48 (Decision Trees), K-Star, and Random Forest.
The relevance of our task arises from the fact that social media platforms are turning into lucrative advertising channels for businesses. It is therefore important to figure out what features go into making a post that a lot of people respond positively to. The results of this project help identify how to design a post that will go ‘viral’. Over the time we spent understanding the data and the models themselves, we were able to structure our models differently to perform better. For instance, we previously trained the video and photo models as one model. With time however, we learnt that separating the two actually provided better accuracy. Our photo models performed better than the video model. Algorithms such as random forest and J-48 performed   best for the photo model while k-star is the only algorithm that performed well for the video model. The number of hashtags was the most important feature in both models. This was as we expected since it greatly influences how many people see a given post.
Below are two graphs that show the performance of the algorithms for both models. The graphs include the performances on the training data as well as the test data.

![](https://github.com/nokarp/EECS349FinalProject/blob/master/Video%20chart.jpg?raw=true)


Figure 1: Video Data

![](https://github.com/nokarp/EECS349FinalProject/blob/master/Photo%20chart.jpg?raw=true)

Figure 2: Photo Data

## Detailed Analysis
#### Data collection and pre-processing:
This was one of the challenging parts of our project. Given that we couldn’t find any existing Instagram data that we needed, we had to find a way to collect the data ourselves. We couldn’t use web scrapers such as Scrapy due to Instagram restrictions on the access of user data. We therefore resulted to manual collection of the data. We were able to collect data from about 1200 posts spread across 120 Instagram accounts belonging to companies in the US. We also later on collected about 300 data points for testing. 
Our data was collected in the format of the number of likes a post has, the number of followers of the account and the caption. We therefore had to write our own code to process  a text document containing the captions and output features such as the caption length, number of hashtags and number of mentions. This was enough for us to create accurate models of our data and still have enough data to test our models.

#### First Models and Experiments:

When we first run our initial experiments and created our first models we did not include features such as the number of tags and the caption length. Moreover we created one model to predict the performances of both the photo and instagram data. When we ran these models we noticed that the number of hashtags was the most important feature. However, our performance we still not as good as wanted. After this and the initial meetings with our professor, we decided to extract the captions and process them to include more attributes (number of tags and caption length). 

#### Final models and Experiments:
 
Through the quarter we iterated on our models and data throughout the quarter to try and find the most accurate and appropriate models possible. Through this process we came to learn that having two different models for the photographs and videos increased their performances immensely. Furthermore, the two models performed very differently for different algorithms. This is something we did not expect.
The KStar performed the best on both the training data and the test data for video posts. Though the Random Forest had great results for the training data, it performed very poorly for the test data most likely because the tree was very complex and probably overfit the data and therefore did not generalize well. J-48 had good results but they weren’t quiet has good as KStar’s. This was most likely due to the complexity of the training model again. The graphs for these results can be referred to in figure 1. For the photo posts, the J-48, KStar, and Random Forest all performed well. Though J-48 performed the best of the testing data, with an accuracy of 73.42%, KStar and Random Forest both performed well with 65.82% accuracy. Figure 2 shows these results. Overall, our models worked much better with the photo posts than the video posts. 
In both data types, though, number of hashtags was by far the most important feature in determining whether the post would be popular. We also learnt that the number of tags (mentions) was also an important feature in the models thus the improved performance when we included it as a feature. One surprise we had was that the caption length was the least important feature. With these results, our models suggest that varying the number of hashtags and number of tags(mentions) to a given number will vary the performance. However, the advertiser has the chance to write the caption as they need since that will not influence the post’s performance a lot.

#### Roles:

We worked on almost everything together and relatively evenly but there were a couple of differences in what we did. First off, we both spent a lot of time trying to figure out the attributes that we wanted; this was in an effort to increase out attribute features. We also took time trying to find ways to efficiently collect posts from Instagram, unfortunately this effort was unsuccessful. Noah and Timothy both collected 600 posts worth of data each, by hand. This took a very long time but we wanted a large enough data collection to be able to get a good model. Timothy focused on running the data in weka and recording the results for the different models for both training and testing.  Noah focused on writing the final report and website and making the charts for the models and results that Tim created. Overall, though we did work on some different things for this project, we did about the same amount of work in the end.

#### Suggestions for Future Work
We have some cool ideas for what we can do in the future. 
1.  Using NLP to analyze the information within the caption. This was an attribute that could be able to describe themes of posts that are popular. For people that want to increase the popularity of their Instagram posts, this could allow them to know how to write their posts. 
2. Using more robust methods for data collection. This would probably involve getting access codes from Instagram accounts so as to bypass the Instagram API restrictions. 
3. We could look at the time of year and days of the week and time of day when a post was made. With a larger dataset, this would help increase the attribute feature space. This could give insights as to when the best time to make an Instagram post is. 
4. Finding a way to analyze the relevance of a hashtag. It has been found that using hashtags with trending topics helps a post perform better. This would therefore need a way to actively keeping checking how a hashtag scores given the current trending topics. 

#### Final Remarks

Overall, we both feel as though we learned a lot from this project more so in our failures than our successes. We learned how different models work with data and when some can look good in training but bad in testing. We learned about different attributes that would help predict the popularity based on our initial attributes and testing. Last, we learned that manual data collection is very time consuming and boring. We also learnt that at times splitting the model of the learners given the data can at times perform better. To conclude, we were very happy with our results and hope to make the models even more accurate in the future. We greatly appreciate the help from the professor and TA’s, on our project and everything else, throughout the entire quarter. 
