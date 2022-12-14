# Improving Reddit Advertising via Classification - Kyle Ness

If a company wants to be successful in marketing their products to prospective customers, they must know their audience. The founders at Everything Meal Prep believe that wholeheartedly, and for that reason, they have gone the distance of hiring us consultants at Online Analysis Co. to help them towards this success. They have done this in the hopes that via our data-driven insights and our ability to create an automated classification system, their meal plan advertisements will only reach customers with matching diets / food interests going forward. This should save them money that would otherwise be spent on ineffective advertising, and conversely, potentially boost sales (if they committed to the same amount of advertising spend). 

Specifically, Everything Meal Prep has tasked us with improving their online advertisements hosted on reddit. As their name suggests, they provide customers meal plans consisting of virtually any ingredients. For this task, they want us to focus solely on aiding the performance of their carnivore and vegan meal plan lines. To this end, we must build an accurate binary classification system, determining whether an online person is a carnivore or a vegan. We will do this by analyzing data that we scraped from the subreddits (of Reddit.com) r/vegan and r/carnivore. Hopefully by using natural language processing techniques and testing various classification models, we will arrive at a system that can perfrom this task with the utmost accuracy.

pecifically, Naive Bayes and logistic regression models will be constructed and evaluated for this task. We also aim to provide Everything Meal Prep with recommendations about how to go about their marketing.

### Dictionary

|Feature             |Type  |Dataset          |Description                                                                           |
|--------------------|------|-----------------|--------------------------------------------------------------------------------------|
|subreddit           |string|vegan, carnivore |Which subreddit, r/vegan or r/carnivore, that the post originated from                |
|title               |string|vegan, carnivore |Title of post                                                                         |
|selftext            |string|vegan, carnivore |The description text contained within the post, i.e., the body of the post            |


### Analysis - Summary
Analysis was conducted on two datasets containing roughly 1,050 observations each on 3 features (1 dependent, 2 independent). These datasets were scraped and assembled from recent posts on r/carnivore and r/vegan, opposing subreddits of the popular website reddit.com. After data cleaning, EDA, and distribution plotting, 2 different classification models were explored, namely: Naive Bayes and Logistic Regression. Both of these models used the sklearn library's CountVectorizer to transform the combined dataset (vegan.csv and carnivore.csv were concatenated) into columns of post word counts, making for a dataframe of well over 10,000 features. This task was a feat in natural language processing. In the end, the Naive Bayes model performed better for this task, although both were high-scoring and very acceptable replacements over the null model whose baseline accuracy was 50.12%. Here, the Naive Bayes model had an accuracy of 95.47% and recall of 97.13%

### Conclusion and Recommendations
Given the results of our model creation and evaluation above, it is evident that Everything Meal Prep can indeed rely on an NLP classification system reliant on user post content for highly accurate targeting of potential customers. While the baseline accuracy rate was 50.12%, our best model, the Naive Bayes estimator paired with a CountVectorizer with tuned parameters, boasts a 95.47% accuracy rate and a 97.13% recall rate which are each very attractive for the task at hand. Everything Meal Prep should go forward with utilizing this model immediately to save on advertising spend and / or boost sales. They can know their audience like the back of their hand using this system, which is what they were initially striving for. The stakeholders in Everything Meal Prep will benefit greatly from the bolstered performance in online marketing that this system promises, as company value will increase on potential higher earnings.

Further, there are some insights gathered from the analysis here. When it comes to delivering these advertisements, they should be tailored to the nature of the recipients. As observed above, posts are generally longer on r/vegan, and seem to contain discussions of animals, people, feelings, and more that may fall outside the realm of just diets (going by common words used). These users are perhaps more conscientious, and a well-targeted ad may need to be conveyed in a savvier, more thought-provoking manner. Beyond these assumptions, the company should also simply use these common words sort of like buzzwords / points of fixation. Mentioning how Everything Meal Prep's "Super Vegan" diet helps preserve wildlife reserves, for example, may goad a vegan to try the product.

Future steps in aiding Everything Meal Prep in this endeavor would perhaps be performing more grid searches for even better hyperparamters, choosing and evaluating estimators not seen here, and collecting more data from reddit. Each of these may potentially lead to an even better-performing model than the Naive Bayes one found here.

### Datasets Source:
Obtained from reddit.com using the Pushshift API: https://github.com/pushshift/api:
