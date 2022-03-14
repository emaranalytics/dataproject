## OVERVIEW
It is hard to underestimate the role of Marketplaces in a world where most communications happen on the web and our virtual environment is full of advertisements with attractive products and services to buy. Meanwhile, it is obvious that many criminals are trying to take advantage of it, using scams and malware to compromise users’ data.

The level of E-commerce fraud is high, according to the statistics. With E-commerce sales estimated to reach $630 billion (or more) in 2020, an estimated $16 billion will be lost because of fraud. Amazon accounts for almost a third of all E-commerce deals in the United States; Amazon’s sales numbers increase by about 15% to 20% each year. From 2018 to 2019, E-commerce spending increased by 57% — the third time in U.S. history that the money spent shopping online exceeded the amount of money spent in brick-and-mortar stores.

As the trend for E-commerce fraud rises and E-commerce fraud scenarios and malware become more subtle and harder to detect, E-commerce fraud protection has never been so important. To make sure that their business is protected, every merchant and bank should pay attention to the latest trends in fraud detection such as modern E-commerce fraud software on Machine Learning (ML), learn the best fraud prevention practices, and be aware of common types of online fraud.

![image](https://user-images.githubusercontent.com/66315773/158102888-694e3147-9c16-470c-b9cf-4647bb906e09.png)

## PROJECT'S KEY CONCEPT

1.__Exploratory data analysis (EDA)__

The original database contains 2 main data, `transaction_data.csv` and `customer_data.csv`. Attributes (also called features) are the variables what we'll use to predict our target variable.

<blockquote>Attributes and features are also referred to as independent variables and a target variable can be referred to as a dependent variable.</blockquote>

We use the independent variables to predict our dependent variable.
Or in our case, the independent variables are a customer's different transaction and data attributes and the dependent variable is whether or not they are fraudulent.

![image](https://user-images.githubusercontent.com/66315773/158103867-45a9d8ea-4cad-4d45-9418-3d73f1663c2a.png)

![image](https://user-images.githubusercontent.com/66315773/158103922-c15afb6d-2b8c-4880-b9dc-4b79d425f262.png)


2. __Correlation Matrix__

Correlation between independent variables
Finally, we'll compare all of the independent variables in one hit.

Why?

<blokcquote>Because this may give an idea of which independent variables may or may not have an impact on our target variable.</blokcquote>

We can do this using `df.corr()` which will create a correlation matrix for us, in other words, a big table of numbers telling us how related each variable is the other.

![image](https://user-images.githubusercontent.com/66315773/158104189-837afa52-9a81-4bb5-a8a7-93f28bf308de.png)

3. __Modeling__

We've explored the data, now we'll try to use machine learning to predict our target variable based on the 26 independent variables.

Remember our problem?

<blockquote>Given parameters about a customer, can we predict whether or not they are fraudulent?</blockquote>

That's what we'll be trying to answer.

And remember our evaluation metric?

<blockquote>If we can reach 90% accuracy at predicting whether a customer is fraudulent or not during the proof of concept, we'll pursure this project.</blockquote>

That's what we'll be aiming for.

But before we build a model, we have to get our dataset ready.

Let's look at it again.

4. __Training and Test Split__

Now comes one of the most important concepts in machine learning, the training/test split.

This is where you'll split your data into a training set and a test set.

You use your training set to train your model and your test set to test it.

The test set must remain separate from your training set.

Why not use all the data to train a model?
Let's say you wanted to take your model into ecommerce company and start using it on transactions. How would you know how well your model goes on a new incoming customer data not included in the original full dataset you had?

This is where the test set comes in. It's used to mimic taking your model to a real environment as much as possible.

And it's why it's important to never let your model learn from the test set, it should only be evaluated on it.

To split our data into a training and test set, we can use Scikit-Learn's `train_test_split()` and feed it our independent and dependent variables `(X & y)`.


5. __Model Selection__

Now we've got our data prepared, we can start to fit models. We'll be using the following and comparing their results.

Logistic Regression - `LogisticRegression()`<br>
K-Nearest Neighbors - `KNeighboursClassifier()`<br>
RandomForest - `RandomForestClassifier()`<br><br>
__Why these?__<br>
If we look at the <a href="https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html">Scikit-Learn algorithm cheat sheet</a>, we can see we're working on a classification problem and these are the algorithms it suggests (plus a few more).

![image](https://user-images.githubusercontent.com/66315773/158104780-6963d52c-57d9-4cfe-a023-4b2dc53ec5fd.png)


"Wait, I don't see Logistic Regression and why not use LinearSVC?"

Good questions.

I was confused too when I didn't see Logistic Regression listed as well because when we read the Scikit-Learn documentation on it, you can see it's a <a href="https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression">model for classification.</a>

And as for LinearSVC, let's pretend we've tried it, and it doesn't work, so we're following other options in the map.

For now, knowing each of these algorithms inside and out is not essential.

Machine learning and data science is an iterative practice. These algorithms are tools in your toolbox.

In the beginning, on your way to becoming a practioner, it's more important to understand your problem (such as, classification versus regression) and then knowing what tools you can use to solve it.

Since our dataset is relatively small, we can experiment to find algorithm performs best.

All of the algorithms in the Scikit-Learn library use the same functions, for training a model, `model.fit(X_train, y_train)` and for scoring a model `model.score(X_test, y_test).score()` returns the ratio of correct predictions (1.0 = 100% correct).

Since the algorithms we've chosen implement the same methods for fitting them to the data as well as evaluating them, let's put them in a dictionary and create a which fits and scores them.

6. __Model Comparison__

![image](https://user-images.githubusercontent.com/66315773/158104869-a6f6c6d3-0ff7-4303-93fc-332d2963f183.png)

7. __Hyperparameter Tuning and Cross-validation__

We'll be using this setup to tune the hyperparameters of some of our models and then evaluate them. We'll also get a few more metrics like precision, recall, F1-score and ROC at the same time.

Here's the game plan:

* Tune model hyperparameters, see which performs best
* Perform cross-validation
* Plot ROC curves
* Make a confusion matrix
* Get precision, recall and F1-score metrics
* Find the most important model features

8. __Feature Selection__

Feature importance is another way of asking, "which features contributing most to the outcomes of the model?"

Or for our problem, trying to predict heart disease using a patient's medical characterisitcs, which charateristics contribute most to a model predicting whether someone has heart disease or not?

Unlike some of the other functions we've seen, because how each model finds patterns in data is slightly different, how a model judges how important those patterns are is different as well. This means for each model, there's a slightly different way of finding which features were most important.

You can usually find an example via the Scikit-Learn documentation or via searching for something like "[MODEL TYPE] feature importance", such as, "random forest feature importance".

Since we're using `LogisticRegression`, we'll look at one way we can calculate feature importance for it.

To do so, we'll use the `coef_` attribute. Looking at the `Scikit-Learn` documentation for `LogisticRegression`, the `coef_` attribute is the coefficient of the features in the decision function.

We can access the `coef_` attribute after we've fit an instance of `LogisticRegression`

![image](https://user-images.githubusercontent.com/66315773/158105103-a4cce7f1-7c87-46d8-bb85-bc7bd7e5050b.png)


9. __Experimentation__

Well we've completed all the metrics our boss requested. we should be able to put together a great report containing a confusion matrix, a handful of cross-valdated metrics such as precision, recall and F1 as well as which features contribute most to the model making a decision.

But after all this you might be wondering where step 6 in the framework is, experimentation.

Well the secret here is, as we might've guessed, the whole thing is experimentation.

From trying different models, to tuning different models to figuring out which hyperparameters were best.

What we've worked through so far has been a series of experiments.

And the truth is, we could keep going. But of course, things can't go on forever.

So by this stage, after trying a few different things, we'd ask ourselves did we meet the evaluation metric?

Remember we defined one in step 3.

If we can reach `90%` accuracy at predicting whether or not a patient has heart disease during the proof of concept, we'll pursure this project.

In this case, we didn't. The highest accuracy our model achieved was below `90%`. (Highest of `85.23%` using `LogisticRegression`)

What next?
We might be wondering, what happens when the evaluation metric doesn't get hit?

Is everything we've done wasted?

No.

It means we know what doesn't work. In this case, we know the current model we're using (a tuned version of LogisticRegression) along with our specific data set doesn't hit the target we set ourselves.

This is where step 6 comes into its own.

1. A good next step would be to discuss with our team or research on our own different options of going forward. The good question is, _"is 85% enough for our fraud detection system?"_ or _"Do we need to increase it?"_

2. Could we collect more data? _This is the possible way_

3. Could we try a better model? If you're working with structured data, you might want to look into `CatBoost` or `XGBoost`. _We need to try both if collecting more data with existing model doesn't fit our accuracy_.

4. Could we improve the current models (beyond what we've done so far)?

