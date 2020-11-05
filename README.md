# Fifa-Player-Valuation

## Project Link:
https://fifaplayermarketvaluation.herokuapp.com/

## Preview:

![fifa](https://user-images.githubusercontent.com/65092287/98266729-a6518e80-1fb0-11eb-879c-7458acc8352c.gif)


## What is Market Value of a Soccer Player?

When we talk about the market value of a soccer player, we refer to the estimate of the amount his soccer club can sell or transfer his contract to another club. And soccer clubs can pay astronomical amount to obtain the top players.

As we shall see later, market values of soccer players follow an exponential trend, indicating that the a small subset of players are highly valuable. Hence, the ability to predict market values may offer a commercial advantage to some of these rich soccer clubs.

## What are some of the most important factors that drive market value?
Upon doing some research, I list the following factors:

### Footballing Skills:
As no soccer players are 100% versatile, footballing skills are categorized into several domains such as Defending, Shooting and Goalkeeping. And having high ratings in any one of these domains can raise your market value.

### On-Field Position:
On average, strikers are valued more than midfielders, followed by defenders.

### Age:
Or the Coefficient of Youth. Naturally, younger players will command higher market value, as they have greater potential for growth and can have longer service terms.

### Media Coverage:
Or the Media Coefficient. Generally, having popular players, who make a greater media impact, can generate more revenue for the clubs.

## Web Scraping with Beautiful Soup

I web scraped the FIFA Index website with the classic Python module Beautiful Soup.

In total, I collected data from 19,401 players, which includes their height, weight, age, preferred foot and skill ratings.

Each skill rating are sub-categorized into domains, which are scored from 0–100. The skill ratings are therefore web scraped by taking the mean of their domains.

Skills ratings of footballers and their respective domains are given as:

Ball Skills: Ball Control, Dribbling

Passing: Crossing, Short Pass, Long Pass

Defense: Marking, Slide Tackle, Stand Tackle

Mental: Aggression, Reactions, Attack Position, Interceptions, Vision, Composure

Physical: Acceleration, Stamina, Strength, Balance, Sprint Speed, Agility, Jumping

Shooting: Heading, Shot Power, Finishing, Long Shots, Curve, Free Kick Accuracy, Penalties, Volleys

Goalkeeping: Positioning, Diving, Handling, Kicking, Reflexes

## Exploratory Data Analysis :

Plotting the heatmap of features and target (Market Value) reveals some interesting trends: Height, Weight, Age, Preferred Foot and Goalkeeping seems to be uncorrelated with the target variable:

![image](https://user-images.githubusercontent.com/65092287/98255668-a8f9b700-1fa3-11eb-8112-c1425b36e821.png)

Thus, the question is should we remove these features? We already understand from domain knowledge that age is an important predictor of Market Value. How about Goalkeeping skills? Note that Goalkeeping is negatively correlated with other skill metrics. This is not surprising as goalkeepers are mostly specialized, and are seldom playing on field. However, some of these goalkeepers are highly valued as shown in the pair plot:

![image](https://user-images.githubusercontent.com/65092287/98256212-4ce36280-1fa4-11eb-95aa-5b71bb5e088d.png)

## Model Selection :

Now, to fit the data, the regression models that we wish to compare are Simple Linear Regression,Polynomial Regression and Random forest Regressor.I have split the entire data frame into 80% Training Set and 20% Test set, where I hold out the Test Set for final model evaluation. For model selection, I further randomly split the Training Set into 5-Folds for cross-validation for simple regression and polynomial reggression.


## Model Evaluation :
### I got best score for the model using Random Forest Regressor:
![image](https://user-images.githubusercontent.com/65092287/98256772-f7f41c00-1fa4-11eb-97d6-032b8fc01cfa.png)

## Conclusion & Future Work
Nonetheless, the results of the finalized model is rather respectable given the limited features that I used. In the future, should other data sources be available, important features such as on-field position of players and media coefficient should be considered.

