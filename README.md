# Fifa-Player-Valuation
https://fifaplayermarketvaluation.herokuapp.com/

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
