# Analyzing Injuries in Professional Soccer Players
##### MSDS Data Science Practicum By Andrea Fernandez

## Introduction
Soccer players are known for falling and embellishing their injuries on the field but, they do actually obtain injuries sometimes. My project focuses on injuries that occur in professional soccer players that play in Europe. I wanted to focus on Europe because these teams were ending their season and have been playing for months on end. The purpose of this project was to better understand what factors effect players and their injuries, like their age or the position that they play. Another goal was to try and predict how long a player might be injured and unable to play based on the various factors. This information can be useful to a variety of staff on the teams by implementing injury prevention programs and also make adjustments to future line-ups. 

## Data 
I collected all of the data myself from mostly betting websites that update player injuries multiple times a day. When searching for datasets, I came up short for soccer injuries. Since there was a definite lack of data on this subject I decided to collect it and compile it all of myself and use it for my project. Although the information from different sources was not very detailed, I was able to add a couple variables specific to the players. I collected data on Premier League in the UK, La Liga in Spain, and Bundesliga in Germany. The reason I chose these three leagues is because I could find similar data on them, whereas a league in Italy barely updated their injuries. It is also important to note that Premier League was the only league that provided 3 other variables that the other leagues did not. 

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
Some important exploratory data analysis was 

![image](https://user-images.githubusercontent.com/60277706/123505342-b5f31580-d61b-11eb-9e68-0811011a1b74.png)
