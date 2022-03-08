## OVERVIEW
Mobile apps are everywhere. They are easy to create and can be lucrative. Because of these two factors, more and more apps are being developed. In this notebook, we will do a comprehensive analysis of the Android app market by comparing over ten thousand apps in Google Play across different categories. We'll look for insights in the data to devise strategies to drive growth and retention.

![image](https://user-images.githubusercontent.com/66315773/157197611-077c9aab-7f9a-4251-abfb-70ff86268097.png)

## PROJECT'S KEY CONCEPTS
1. __Dataframe__

The date we use consists of two files:

* `apps.csv`: contains all the details of the applications on Google Play. There are 13 features that describe a given app.
* `user_reviews.csv`: contains 100 reviews for each app, most helpful first. The text in each review has been pre-processed and attributed with three new features: Sentiment (Positive, Negative or Neutral), Sentiment Polarity and Sentiment Subjectivity.

![image](https://user-images.githubusercontent.com/66315773/157198559-24175000-45ea-43d4-a93c-3acaf5ef00c9.png)

2. __Data Cleaning__

The three features that we will be working with most frequently henceforth are `Installs`, `Size`, and `Price`. A careful glance of the dataset reveals that some of these columns mandate data cleaning in order to be consumed by code we'll write later. Specifically, the presence of special characters (`, $ +`) and letters (`M k`) in the `Installs`, `Size`, and `Price` columns make their conversion to a numerical data type difficult. Let's clean by removing these and converting each column to a numeric type.

![image](https://user-images.githubusercontent.com/66315773/157199791-347f481c-5cdc-4768-ab76-b6170d7fedc9.png)

3. __Exploring App Categories__

With more than 1 billion active users in 190 countries around the world, Google Play continues to be an important distribution platform to build a global audience. For businesses to get their apps in front of users, it's important to make them more quickly and easily discoverable on Google Play. To improve the overall search experience, Google has introduced the concept of grouping apps into categories.

This brings us to the following questions:

* Which category has the highest share of (active) apps in the market?
* Is any specific category dominating the market?
* Which categories have the fewest number of apps?
We will see that there are `33` unique app categories present in our dataset. _Family_ and _Game_ apps have the highest market prevalence. Interestingly, _Tools_, _Business_ and _Medical_ apps are also at the top.

![image](https://user-images.githubusercontent.com/66315773/157200230-0b974014-2c01-43a7-a3b3-c7a144b25c2c.png)


4. __App Ratings Distribution__

After having witnessed the market share for each category of apps, let's see how all these apps perform on an average. App ratings (on a scale of `1` to `5`) impact the discoverability, conversion of apps as well as the company's overall brand image. Ratings are a key performance indicator of an app.

From our research, we found that the average volume of ratings across all app categories is `4.17`. The histogram plot is skewed to the right indicating that the majority of the apps are highly rated with only a few exceptions in the low-rated apps.

![image](https://user-images.githubusercontent.com/66315773/157200744-b3c1b071-86ea-44ea-bc62-ae05c7e1e66e.png)


5. __Size and Price of An App__

Let's now examine app size and app price. For size, if the mobile app is too large, it may be difficult and/or expensive for users to download. Lengthy download times could turn users off before they even experience your mobile app. Plus, each user's device has a finite amount of disk space. For price, some users expect their apps to be free or inexpensive. These problems compound if the developing world is part of your target market; especially due to internet speeds, earning power and exchange rates.

How can we effectively come up with strategies to size and price our app?

* Does the size of an app affect its rating?
* Do users really care about system-heavy apps or do they prefer light-weighted apps?
* Does the price of an app affect its rating?
* Do users always prefer free apps over paid apps?
We find that the majority of top rated apps (rating over `4`) range from `2 MB` to `20 MB`. We also find that the vast majority of apps price themselves under `$10`.

6. __Relation Between App Category and App Price__

So now comes the hard part. How are companies and developers supposed to make ends meet? What monetization strategies can companies use to maximize profit? The costs of apps are largely based on features, complexity, and platform.

There are many factors to consider when selecting the right pricing strategy for your mobile app. It is important to consider the willingness of your customer to pay for your app. A wrong price could break the deal before the download even happens. Potential customers could be turned off by what they perceive to be a shocking cost, or they might delete an app they’ve downloaded after receiving too many ads or simply not getting their money's worth.

Different categories demand different price ranges. Some apps that are simple and used daily, like the calculator app, should probably be kept free. However, it would make sense to charge for a highly-specialized medical app that diagnoses diabetic patients. Below, we see that _Medical_ and _Family_ apps are the most expensive. Some medical apps extend even up to `$80`! All game apps are reasonably priced below `$20`.

![image](https://user-images.githubusercontent.com/66315773/157201714-d00c90b6-cdb2-494f-8d28-e0ce5c5adbd2.png)


7. __Filter Out _Junk_ Apps__

It looks like a bunch of the really expensive apps are "junk" apps. That is, apps that don't really have a purpose. Some app developer may create an app called _`I Am Rich Premium or most expensive app (H)`_ just for a joke or to test their app development skills. Some developers even do this with malicious intent and try to make money by hoping people accidentally click purchase on their app in the store.

Let's filter out these junk apps and re-do our visualization. The distribution of apps under `$20` becomes clearer.

![image](https://user-images.githubusercontent.com/66315773/157202385-5b51fced-a748-4230-9ccb-640e638aac0f.png)

8. __Popularity of Paid vs Free Apps__

For apps in the Play Store today, there are five types of pricing strategies: free, freemium, paid, paymium, and subscription. Let's focus on free and paid apps only.

_Some characteristics of free apps are_:

* Free to download.
* Main source of income often comes from advertisements.
* Often created by companies that have other products and the app serves as an extension of those products.
* Can serve as a tool for customer retention, communication, and customer service.

_Some characteristics of paid apps are_:

* Users are asked to pay once for the app to download and use it.
* The user can't really get a feel for the app before buying it.

Are paid apps installed as much as free apps? It turns out that paid apps have a relatively lower number of installs than free apps, though the difference is not as stark as I would have expected!

![image](https://user-images.githubusercontent.com/66315773/157202822-51f5fb4c-1f89-4aec-b08e-67bc4f3bb913.png)

9. __Sentiment Analysis of User Reviews__

Mining user review data to determine how people feel about your product, brand, or service can be done using a technique called sentiment analysis. User reviews for apps can be analyzed to identify if the mood is positive, negative or neutral about that app. For example, __positive__ words in an app review might include words such as `amazing`, `friendly`, `good`, `great`, and `love`. __Negative__ words might be words like `malware`, `hate`, `problem`, `refund`, and `incompetent`.

By plotting sentiment polarity scores of user reviews for paid and free apps, we observe that free apps receive a lot of harsh comments, as indicated by the outliers on the negative y-axis. Reviews for paid apps appear never to be extremely negative. This may indicate something about app quality, i.e., paid apps being of higher quality than free apps on average. The median polarity score for paid apps is a little higher than free apps, thereby syncing with our previous observation.

In this notebook, we analyzed over ten thousand apps from the Google Play Store. We can use our findings to inform our decisions should we ever wish to create an app ourselves.

![image](https://user-images.githubusercontent.com/66315773/157203424-4f2e15f9-77e7-45fb-813a-bb6b9c90f490.png)
