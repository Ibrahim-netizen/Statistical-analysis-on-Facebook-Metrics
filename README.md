# Statistical-analysis-on-Facebook-Metrics

### Abstract
Linear regression analysis is incorporated to model how user engagement on the Facebook page of a renowned cosmetic brand can improve the brand's online presence and boost revenue. With this the Cosmetic brand is able to determine what type of post received more engagement whether it is a photo, link, status, or video, paid for or not, created by action, product, and inspiration, and what day of the week, month and time the post was made. Other statistical tests performed on the dataset features are the Hypothesis test, Shapiro Wilk test, Analysis of Variance, and scatterplot matrix.  The results demonstrated how the attributes of social media posts may be used to anticipate by providing information on user involvement with a brand's social media page, the best type of posts to make, and the best time to publish.

## Introduction
Upon the proliferation of the internet and the world as we know it becoming digital, product marketers and business owners have adopted the use of social media platforms such as Facebook, Twitter and so forth to promote their products and services, create online presence, beat market competiton, acquire feedback from new and existing customers as well as aid business partnership. An exploratory analysis on how the performance metrics of social media posts made by business stakeholders can influence brand building is essential. 
Linear regression analysis is incorporated to model how user engagement on the Facebook page of a renowned cosmetic brand can improve the brand's online presence and boost revenue. With this the Cosmetic brand is able to determine what type of post received more engagement whether it is a photo, link, status or video, paid for or not, created by action, product and inspiration and what day of the week, month and time the post was 
made.

![image](https://user-images.githubusercontent.com/76513466/137328361-d0205575-bf8c-4494-97c4-23b641a55635.png)

### Facebook Metrics
The dataset comprises of 7 independent variables namely: Post Type classified into photo, link, status and video,Category based on the type of campaign performed by this specific cosmetic brand created by action (1), product (2) and inspiration (3), Weekday, Month, hour, Paid and Page total likes as well as 12 continuous output variables of the 500 posts made on the Facebook page of the cosmetic brand. 
The seven inputted datasets were retrieved directly from the company’s Facebook page and the 11 output characteristics of these 500 posts were exported from Facebook which includes Lifetime people who have liked your page and engaged with your post, Lifetime post consumers, Lifetime engaged users, Lifetime post consumptions, Lifetime post reach by people who like your page, Likes, Lifetime post impressions by people who have liked your page, Lifetime post total reach, Lifetime post total impressions. The total interaction column was calculated from the summation of Posts’ comment, like and share.
The dataset was obtained from UCI Machine Learning Repository (Center for Machine Learning and Intelligent Systems) used by Sérgio Moro, Paulo Rita and Bernardo Vala (2016) Retrieved 20th November 2020 from http://archive.ics.uci.edu/ml/datasets/Facebook+metrics 

## Data Preprocessing
Initially, I imported the dataset as a csv (comma separated value) file and found missing data across the rows and columns of the uncleaned Facebook dataset. The summary() function was used to produce a brief result on the descriptive statistics of the dataset such as Mean, Median, Minimum and Maximum value, Type of data, Percentage quartiles and missing data which turned out to be 5 missing values in total. The complete.case() is called to remove rows of missing values which reduced the total number of variable 
data assigned to a new object. The new dataset is also then summarised to confirm it is free of missing quantities, NA with total posts of 495 saved as complete_data.
The Table below displays an overview of comprising of the 7 input variables and a dependent variable, Lifetime engaged users summary.

![image](https://user-images.githubusercontent.com/76513466/137337322-f24dacdd-13c6-4f19-8a68-554751a28d21.png)

Data visualization was performed using a scatterplot matrix after data preprocessing.

## Scatterplot Matrix
A scatterplot matrix was designed to show the correlation between the 7 inputted independent variables and the chosen output variable Lifetime Engaged Users. A pie chart displaying the percentage of the 7 input features of the cleaned dataset on the Lifetime of Engaged Users.

![Rplot](https://user-images.githubusercontent.com/76513466/137338672-4acdd65a-06a0-4894-826a-4880254283ab.png)


Scatterplot Matrix
• To show the linearity between the 7 input features and the chosen output characteristic, Lifetime Engaged Users.
• This is done using the pairs() function to plot the graph of Lifetime Engaged Users against the 7 input variables , Page total likes, Category, Post Month, Post Weekday, Post Hour, Paid, and fit a line of best fit.
• The categorical data, Type is converted to numeric with the as.numeric(type.convert()) function according to Stack Overflow (n.d.a).

## Linear Regression Model
A linear model is one in which the input variables (x) and the single output variable (y) are assumed to have a linear relationship (y). In the field of statistics, linear regression was established as a model for analysing the relationship between input and output numerical variables. It is a statistical model that analyses the relationship between a dependent output variable in this case, Lifetime Engaged Users against the 7 independent input variables. The regression model is fitted such that all the input variables in a way that the predicted values are as close as possible to the real values. The lm() function is used here to fit the regression model which is assigned to Regression and this is plotted.

### The Regression Plot

![Rplot01](https://user-images.githubusercontent.com/76513466/137340066-30792539-8d32-4865-801f-a80190c9f541.png)

In the plot above, each point where the prediction made by the model is on the x-axis and the accuracy of the prediction is on the y-axis.
The postive values for the residual (on the y-axis) above zero means the prediction was too low, and the negative values mean the prediction was too high. Zero means the prediction was exactly correct. 
Thus, the Residual vs Fitted plot is an ideal residual plot showing high prediction on the amount of lifetime engaged users that interact with the posts on the facebook page of the cosmetic brand using the page total likes gathered, category of the post, time of post and whether paid for or not.
- The plot is highly symmetrically distributed.
- They're clustered around the lower single digits of the y-axis.
- In general, there isn't any clear pattern. (If you can detect a clear pattern or trend in your residuals, then your model has room for improvement)

### The Residual Plot
![Rplot02](https://user-images.githubusercontent.com/76513466/137340256-91338a5d-b690-40eb-bc72-425bf6c10d87.png)

In order to determine normality graphically, we can use the output of a normal Q-Q Plot. If the data are normally distributed, the data points will be close to the diagonal line. If the data points stray from the line in an obvious non-linear fashion, the data are not normally distributed. As we can see from the normal Q-Q plot below, the data is normally distributed.

![Rplot03](https://user-images.githubusercontent.com/76513466/137340682-5887fc0b-502d-4611-9463-411cad0f8d36.png)

![Rplot04](https://user-images.githubusercontent.com/76513466/137340753-0c7d734a-0875-4175-858d-567b11b84006.png)

![image](https://user-images.githubusercontent.com/76513466/137411713-4965610d-6bec-44fd-b550-a6c22ca67310.png)

This residual plot is linear and non-heteroscedastious. The outling datapoints can be treated as a data error or filtered out by comparing the coefficients of the regression model with the outliers, if the model does not change much then the outliers can be dismissed.
Another way to improve this regression model is to transform the variables with the logarithm function which can change the shape of the distribution. Statistically, MSE is the maximum likelihood estimator of residual variance, but is biased (downward). The Pearson one is the restricted maximum likelihood estimator of residual variance, which is unbiased.

![image](https://user-images.githubusercontent.com/76513466/137344763-c93e0c1b-cffc-434b-9cfe-e954ca7ee544.png)

Analysis of Variance (ANOVA)
• The anova function extracts the anova table from the model assigned as Regression fitted by the lm() function and summarised.
• A high percentage indicates that the regression line closely matches the actual sample data.
• Complete_data = b1*Page.total.likes + b2*Category + b3*Post.Month + b4*Post.Weekday + b5*Post.Hour + b6*Paid + b7*Post.Type
• Since three of the input variables are not defined due to singularities, Complete_data = b2*Category + b4*Post.Weekday + b5*Post.Hour
• - b1 to b7 are regression coefficients

### Shapiro Wilk Test
• Shapiro test is a test of normality to confirm if sample test is of a normal distribution which is a common assumption in analysing dataset including regression, ANOVA, t-tests and the likes.
• Using Shapiro-wilk test to assess if each of the output columns for the features to be predicted follow a normal distribution.
• If the Sig. value of the Shapiro-Wilk Test is greater than 0.05, the data is normal. If it is below 0.05, the data significantly deviate from a normal distribution.
• The test-value here, W = 0.63449 is greater than 0.05 which shows that the variable, Lifetime Engaged Users follows a normal distribution in the Facebook metrics distribution.
• Also the data column named Lifetime Post consumers, W = 0.62031 follows a normal distribution.

## RESULTS AND OBSERVATION
The regression model produced an unbiased prediction because the residual data points fall randomly around zero and follow a normal distribution. From the Residual statistics, the p-value and squared terms are significant thereby confirming the viability of this model and unbiased fit. And the straight line of best fit indicates that the Lifetime of Engaged users is positively correlated with the 7 input variable features of the brand’s posts. A close spread of prediction values to the line of best fit indicate the level of precision of how close the predictions are to the observed values. If the spread is too large, the model becomes useless for prediction. The R-squared value indicates that the prediction is more precise. The standard error of the plotted regression model is low of about 2.856e-12 on 491 degrees of freedom also indicates the observations are closer to the fitted line.

In general, the various methods in evaluating the normality of a data sample distribution includes:
• Inputting data to the model in the case of fitting models.
• Model evaluation results in the case of model selection.
• Residual errors from model predictions in the case of regression.

## CONCLUSION
This business research aimed at demonstrating how regression analysis can be made from the input variables of Posts uploaded on the Facebook page of a renowned Cosmetic brand can be used to improve the online presence of the brand against the 11 output variable characteristics of these Posts 
and their Category based on the discretion of the brand’s Social media Manager. These performance metrics were modelled with the Category, Post Weekday and Post Hour with the best fit model without singularities. From the results obtained, denoted that the null hypothesis, H0 is valid and thus rejects the alternative hypothesis, H1.

The result showed how it is reliable to use the features of social media posts to predict by providing insights on user’s interaction with brand’s social media page, type of Posts best made, and time Posts gain more impact. Although it fails to the features of reshared posts and its performance metrics amongst others which can serve as potential aim for future research.

