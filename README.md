# Classification into Categories - by bedrooms
### Impact
Real estate platforms can enhance user experience by integrating this model to better understand their users preferences and constraints. Furthermore, governments can increase access to affordable houses by studying the demand and supply of specific areas. This way helping people have homes which in turn helps the government in many ways.

<hr>
I've built a classification model to classify data into one of the set categories, which is the number of bedrooms. Given other features like price, bathrooms, acre lot size, house size, city, and state.
Essentially, the model can predict what number of bedrooms will you be able to get given these criteria aka features.

## Visualization and Pre-processing
Firstly, I removed all the rows with null values from our dataset. Then I encoded the city and state columns as they were strings. 
Now I checked the correlation between average price and number of bedrooms. However, we found a lot of outliers as can be seen below.
![vis1](https://github.com/HarshaBeth/Machine-Learning-Classification/blob/main/vis_class/vis1.png)

After further zooming into our data by only choosing to see data from 0 to 15 bedrooms, we get the following. From here it is clear that the data starts to go off trend after 7 bedrooms thus we remove all data after that.
![vis2](https://github.com/HarshaBeth/Machine-Learning-Classification/blob/main/vis_class/vis2.png)

Next, we check the correlation between bedrooms and bathrooms without filtering, we get a scatter plot as seen below. However, we have too much noisy data.
![vis3](https://github.com/HarshaBeth/Machine-Learning-Classification/blob/main/vis_class/vis3.png)

After zooming in to only 0 to 7 bedrooms, we get the average number of bathrooms for each "number of bedrooms". And we get 5, I thought 5 would be a good checkpoint and to remove everything after, but the line plot we will see next to say otherwise.
![vis4](https://github.com/HarshaBeth/Machine-Learning-Classification/blob/main/vis_class/vis4.png)

Here we make a line plot of bathrooms and their average prices, this way we can truly see whether the noisy data is after 5 or some other checkpoint. And as expected there will be a lot of outliers and we must zoom in further to see in detail.
![vis5](https://github.com/HarshaBeth/Machine-Learning-Classification/blob/main/vis_class/vis5.png)

After zooming in to 0 to 15 bathrooms, we get the following. After noticing the trend here, we can easily say that the real outliers are the one that break the trend aka above 11. These rows are removed from our dataset.
![vis6](https://github.com/HarshaBeth/Machine-Learning-Classification/blob/main/vis_class/vis6.png)

Lastly, I removed all the duplicate rows that would play a hand in giving wrong predictions. Moreover, I shuffled the dataset to eliminate bias.


## Training and Testing Classification Models
Starting with the Gaussian Naive Bayes, after the pre-processing steps I trained and tested this model and it got an accuracy score of 47.8%. This model is known for its categorization abilities.
It is always better to check other models to ensure we get the best result.

So I checked the <b>Random Forest Classifier</b>, and after training and testing, I got an accuracy of 64.3%. Much better than the GaussianNB.

Just to make sure I'm not missing out on a better opportunity I tested the Decision Tree Classifier too. But, it got an accuracy score of 53.6% which is, although higher than the GaussianNB, still not better than the Random Forest.
