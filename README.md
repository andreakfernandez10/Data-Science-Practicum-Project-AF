# Analyzing Injuries in Professional Soccer Players
##### MSDS Data Science Practicum By Andrea Fernandez

## Introduction
Soccer players are known for falling and embellishing their injuries on the field but, they do actually obtain injuries sometimes. My project focuses on injuries that occur in professional soccer players that play in Europe. I wanted to focus on Europe because these teams were ending their season and have been playing for months on end. The purpose of this project was to better understand what factors effect players and their injuries, like their age or the position that they play. Another goal was to try and predict how long a player might be injured and unable to play based on the various factors. This information can be useful to a variety of staff on the teams by implementing injury prevention programs and also make adjustments to future line-ups. 

## Data 
I collected all of the data myself from mostly betting websites that update player injuries multiple times a day. When searching for datasets, I came up short for soccer injuries. Since there was a definite lack of data on this subject I decided to collect it and compile it all of myself and use it for my project. Although the information from different sources was not very detailed, I was able to add a couple variables specific to the players. I collected data on Premier League in the UK, La Liga in Spain, and Bundesliga in Germany. The Premier League and La Liga consists of 20 teams, while Bundesliga has 18. The reason I chose these three leagues is because I could find similar data on them, whereas a league in Italy barely updated their injuries. It is also important to note that Premier League was the only league that provided 3 other variables that the other leagues did not. 

### Main Injury Dataset:	
#### 1. Player - First and last name 
#### 2. Injury- body area	
#### 3. Date of Injury- Exact date it occurred
#### 4. Potential Return- Estimate of return of player
#### 5. Age- current age of player
#### 6. Team- current team 
#### 7. Total Days- Number of days player was injured
#### 8. Position- Forwards, Midfileder, Defender, or Keeper
#### 9. Reoccurring Injury- Whether this injury has happened before
#### 10. League- Premier, La Liga, or Bundesliga	
### Premier League Dataset Only:
#### 11. Condition- Player being assessed, fitness test, or no condition
#### 12. Status- Status of injury 25%, 50%, 100%
#### 13. Details- Any information given from the team abou the injury 

## Data Cleaning
Since I compiled the dataset entirely, I knew there was not a lot of data cleaning that needed to be done. My dataset was on the smaller side so I couldn't omit any of the rows or columns that had errors so I made sure to fix any typos or date errors that occurred before getting further into my project. The main Injury dataset with all leagues did not contain any missing values, but the Premier League dataset did have 77 missing values. I decided to fix this issues by replacing the NA's with another character to prevent any issues.
<p align="center">
<img width="405" alt="Screen Shot 2021-06-25 at 8 18 35 PM" src="https://user-images.githubusercontent.com/60277706/123522381-26308400-d67a-11eb-8b6e-6b40d65848b6.png">
</p>
<p align="center">
<img width="553" alt="Screen Shot 2021-06-25 at 8 21 41 PM" src="https://user-images.githubusercontent.com/60277706/123522449-950ddd00-d67a-11eb-831f-f3715128304e.png">
</p>
<p align="center">
<img width="556" alt="Screen Shot 2021-06-25 at 8 21 50 PM" src="https://user-images.githubusercontent.com/60277706/123522471-b53d9c00-d67a-11eb-9969-efc9a2529494.png">
<p/>
<p align="center">
<img width="212" alt="Screen Shot 2021-06-25 at 8 25 12 PM" src="https://user-images.githubusercontent.com/60277706/123522478-bec70400-d67a-11eb-9b60-f35ccc9dc0da.png">
<p/>

## Exploratory Data Analysis
Some of the more important exploratory commands I used was producing the frequency for all of the character variables. This function gave a lot of insight into which injuries happen the most along with the team and leagues effected. We can also see that Defender is the most injured position and two of the Premier League teams have the largest number of injuries. The number of reoccurring injuries is almost the same as new injuries, which was suprising to see. We can also see that Premier League has the most injured players with Bundesliga second, although they have the least amount of teams. 

<p align="center">
<img width="671" alt="Screen Shot 2021-06-26 at 2 59 36 PM" src="https://user-images.githubusercontent.com/60277706/123525603-2be49480-d68f-11eb-89d9-eae9440c0b85.png">
<img width="673" alt="Screen Shot 2021-06-26 at 3 00 21 PM" src="https://user-images.githubusercontent.com/60277706/123525620-59314280-d68f-11eb-8361-78a882191326.png">
<img width="669" alt="Screen Shot 2021-06-26 at 3 00 44 PM" src="https://user-images.githubusercontent.com/60277706/123525624-63534100-d68f-11eb-98bc-80331f2bdb16.png">
<img width="666" alt="Screen Shot 2021-06-26 at 3 01 03 PM" src="https://user-images.githubusercontent.com/60277706/123525631-6b12e580-d68f-11eb-9d25-f286d41474c0.png">
<img width="695" alt="Screen Shot 2021-06-26 at 3 25 27 PM" src="https://user-images.githubusercontent.com/60277706/123526087-c72b3900-d692-11eb-9cec-0673b9bb8631.png">
</p> 
## Building The Models
The goal for making these models was to accurately predict how long players will be injured and unable to play based on which injury they possessed and their injury type and their age. I used two different model types and ran them together to see which one predicted the total days of injury better. I split the data based on whether or not it was a reoccurring injury or not since it was almost even number in the data. Once the data was split, I made training and testing data in order to run through the model. The first model I created was a linear regression model with the data frame of Date of Injury, Age, Total Days, Reoccurring Injury. The linear model was set up to predict the total days based on the rest of the variables in the data frame. The next model was a random forest with regression purposes just like the linear model. Once all of the models were built, I was able to train them and test the results.
<p align="center">
<img width="686" alt="Screen Shot 2021-06-26 at 4 12 15 PM" src="https://user-images.githubusercontent.com/60277706/123527037-4f144180-d699-11eb-83d4-cb66b9afba39.png">
<img width="682" alt="Screen Shot 2021-06-26 at 4 13 56 PM" src="https://user-images.githubusercontent.com/60277706/123527121-1fb20480-d69a-11eb-9e04-1d2a8fc91b91.png">
</p>

## Evaluate Model
I first evaluated the training data with both models, which was the larger of the two datasets split. Then the testing data was run with both models and they produced the predicted values, true values, and which model it was. The next step I took was measure how each of the models performed on both the training and testing datasets. Below we can see the results of how the root mean square error(rmse) for the random forest was lower, which means it performed better than the linear regression model for the training data. The rmse was lower for the linear regression model and peformed better when run on the testing data. Since the random forest was not performing as well as it should be, I decided to use resampling on the training data. This is to get a better estimate on how the model will likely perform if there was new data put into the model.

<p align="center">
 <img width="579" alt="Screen Shot 2021-06-26 at 4 34 59 PM" src="https://user-images.githubusercontent.com/60277706/123527408-846e5e80-d69c-11eb-9d94-6daac61d552a.png"> 
</p>
<p align="center">
<img width="567" alt="Screen Shot 2021-06-26 at 4 35 06 PM" src="https://user-images.githubusercontent.com/60277706/123527410-89cba900-d69c-11eb-8a74-0e1a0640c047.png">
</p>
<p align="center">
<img width="705" alt="Screen Shot 2021-06-26 at 4 27 19 PM" src="https://user-images.githubusercontent.com/60277706/123527288-753ae100-d69b-11eb-9756-6b2f7033bc9d.png">
</p>

## Try Random Forest Again
The second random forest model is made by creating folds instead of splitting the data like before, but still using Reoccurring Injuries as the divisive property. What this does is fit a model to the first 9 folds and then evaluate the models on the 10th and last fold, until it goes through the whole training set. After we run this model we were able to produce the same results as the linear model, which means it is a better random forest model than the inital one.
<p align="center">
<img width="584" alt="Screen Shot 2021-06-26 at 6 17 00 PM" src="https://user-images.githubusercontent.com/60277706/123529142-d3bb8b80-d6aa-11eb-8660-973b06e38f5b.png">
</p>
<p align="center">
<img width="691" alt="Screen Shot 2021-06-26 at 6 32 28 PM" src="https://user-images.githubusercontent.com/60277706/123529386-e636c480-d6ac-11eb-81e0-c15c9712cc23.png">
</p>

## Text Mining
I wanted to do text mining for the Premier League data set since the teams provided a qucik detailed explination of the players injury. A lot of the details were direct quotes, which meant that the details were too different to categorize. I took the Details variable and ran a text mining analysis to produce a word cloud of the most frequent words to see if there was a common theme in the injuries. It appears that being able to play for the rest of the season was mainly talked about and anoth one that stood out was surgery. I explore this further in Tableau and visualization section. 

![image](https://user-images.githubusercontent.com/60277706/123505342-b5f31580-d61b-11eb-9e68-0811011a1b74.png)


## Visualizations
I used Tableau to create visualizations to go deeper into the data and understand how injuries effect players and teams. I will link the Tableau Public page so you can interact with the visualizations and see all of the details by hovering over the data points.
- This first visualization shows two different graphs. The first graph shows how close the reoccurring injuries in quantity. The second shows the injuries that occur the most for each position played. We can see that the knee has the most injuries for every position played on the field. 
![image](https://user-images.githubusercontent.com/60277706/123529426-50e80000-d6ad-11eb-99a5-0f843f59a0a3.png)

- This visualization has two separte line graphs. The plot on the top left shows the relationship between the age of the player and the total days they were injured. We can see that the total days increase with age. The bottom left graph shows the relationship of the total number of injuries and the age of the players. We can see the peak in injuries at the same age as the previous graph. Players in their late twenties and towards the end of their careers are the most injured for the longest amount of time as well.
![image](https://user-images.githubusercontent.com/60277706/123529489-dec3eb00-d6ad-11eb-9557-9ffb7e2e2faa.png)

- This last visualization focuses on the specific injuries that occur and injuries that lead players to be out for the season. The left bar graph is filtered to show which injuries lead players to either have surgery or to be out for the season completely, or both. We can see the knee is by far the most problematic and serious injury for players. The left visual is filtered to show the injuries that occur the most in the dataset and how they compare in size. 
![image](https://user-images.githubusercontent.com/60277706/123529535-63af0480-d6ae-11eb-9cac-bbe9d7f625b1.png)

## Conclusion



