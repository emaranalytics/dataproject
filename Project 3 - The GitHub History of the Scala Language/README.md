
## OVERVIEW
With almost 30k commits and a history spanning over ten years, Scala is a mature programming language. It is a general-purpose programming language that has recently become another prominent language for data scientists.

Scala is also an open source project. Open source projects have the advantage that their entire development histories -- who made changes, what was changed, code reviews, etc. -- are publicly available.

We're going to read in, clean up, and visualize the real world project repository of Scala that spans data from a version control system (Git) as well as a project hosting site (GitHub). We will find out who has had the most influence on its development and who are the experts.

The dataset we will use, which has been previously mined and extracted from GitHub, is comprised of three files:

* `pulls_2011-2013.csv` contains the basic information about the pull requests, and spans from the end of 2011 up to (but not including) 2014.
* `pulls_2014-2018.csv` contains identical information, and spans from 2014 up to 2018.
* `pull_files.csv` contains the files that were modified by each pull request.

![alt text](https://www.lightbend.com/assets/images/brand/scala/scala-logos/svg/scala-full-color.svg)

## PROJECT'S KEY CONCEPTS
1. __Is The Project Still Actively Maintained?__

The activity in an open source project is not very consistent. Some projects might be active for many years after the initial release, while others can slowly taper out into oblivion. Before committing to contributing to a project, it is important to understand the state of the project. Is development going steadily, or is there a drop? Has the project been abandoned altogether?

The data used in this project was collected in January of 2018. We are interested in the evolution of the number of contributions up to that date.

For Scala, we will do this by plotting a chart of the project's activity. We will calculate the number of pull requests submitted each (calendar) month during the project's lifetime. We will then plot these numbers to see the trend of contributions.

* A helpful reminder of how to access various components of a date can be found in this exercise of Data Manipulation with pandas
* Additionally, recall that you can group by multiple variables by passing a list to `groupby()`. This video from Data Manipulation with pandas should help!

![image](https://user-images.githubusercontent.com/66315773/157216715-9ae2ecad-e36b-4b77-92f9-cbbf400cb732.png)


2. __Is there camaraderie in the project?__
The organizational structure varies from one project to another, and it can influence your success as a contributor. A project that has a very small community might not be the best one to start working on. The small community might indicate a high barrier of entry. This can be caused by several factors, including a community that is reluctant to accept pull requests from "outsiders," that the code base is hard to work with, etc. However, a large community can serve as an indicator that the project is regularly accepting pull requests from new contributors. Such a project would be a good place to start.

In order to evaluate the dynamics of the community, we will plot a histogram of the number of pull requests submitted by each user. A distribution that shows that there are few people that only contribute a small number of pull requests can be used as in indicator that the project is not welcoming of new contributors.

![image](https://user-images.githubusercontent.com/66315773/157217024-8eeb3e27-2213-4fb9-94d6-72fde8fdc6de.png)

3. __What files were changed in the last ten pull requests?__
Choosing the right place to make a contribution is as important as choosing the project to contribute to. Some parts of the code might be stable, some might be dead. Contributing there might not have the most impact. Therefore it is important to understand the parts of the system that have been recently changed. This allows us to pinpoint the "hot" areas of the code where most of the activity is happening. Focusing on those parts might not the most effective use of our times.

![image](https://user-images.githubusercontent.com/66315773/157217162-e93db4a1-1bc9-426a-b825-f94927784892.png)


4. __Who made the most pull requests to a given file?__

When contributing to a project, we might need some guidance. We might find ourselves needing some information regarding the codebase. It is important direct any questions to the right person. Contributors to open source projects generally have other day jobs, so their time is limited. It is important to address our questions to the right people. One way to identify the right target for our inquiries is by using their contribution history.

We identified `src/compiler/scala/reflect/reify/phases/Calculate.scala` as being recently changed. We are interested in the top 3 developers who changed that file. Those developers are the ones most likely to have the best understanding of the code.

![image](https://user-images.githubusercontent.com/66315773/157217387-e35fe6cd-bdaa-432c-9678-8733a02c5211.png)

5. __Who made the last ten pull requests on a given file?__

Open source projects suffer from fluctuating membership. This makes the problem of finding the right person more challenging: the person has to be knowledgeable and still be involved in the project. A person that contributed a lot in the past might no longer be available (or willing) to help. To get a better understanding, we need to investigate the more recent history of that particular part of the system.

Like in the previous task, we will look at the history of `src/compiler/scala/reflect/reify/phases/Calculate.scala`

![image](https://user-images.githubusercontent.com/66315773/157217555-7eb0d3fd-b3aa-4dc8-b39b-01ee2a3f434f.png)

6. __The pull requests of two special developers__
Now that we have identified two potential contacts in the projects, we need to find the person who was most involved in the project in recent times. That person is most likely to answer our questions. For each calendar year, we are interested in understanding the number of pull requests the authors submitted. This will give us a high-level image of their contribution trend to the project.

![image](https://user-images.githubusercontent.com/66315773/157217797-bd8fd6ea-9a57-443e-b63b-a30366ed8063.png)


7. __Visualizing the contributions of each developer__

As mentioned before, it is important to make a distinction between the global expertise and contribution levels and the contribution levels at a more granular level (file, submodule, etc.) In our case, we want to see which of our two developers of interest have the most experience with the code in a given file. We will measure experience by the number of pull requests submitted that affect that file and how recent those pull requests were submitted.

![image](https://user-images.githubusercontent.com/66315773/157217913-330a8dd7-8975-4089-badc-61de2fa02d36.png)

