****NFL ANALYSIS****

Team Members: Sean Oberer, Vatsal Rathod, Piyush Jain, Garrison Bolick, Anuj Sharma

**Introduction to Problem:**

For our project, we want to predict what an NFL running backs fantasy football production will be based on their statistics from 2018. Fantasy football is an extremely popular game where people can own virtual teams with NFL players in a privately owned or public league with other real people that also pick their teams. We want to predict what a running backs production would be specifically because running backs are the most valuable players in most fantasy football leagues and consistently provide the most points for fantasy football owners. We will be taking their fantasy football production statistics from 2018 and predicting what their future fantasy production will be in the upcoming season. 

**Research Questions:**

What will a NFL running back's fantasy football point per game production be based on their in-game statistics such as rushing/passing yards per game, touchdowns per game, etc.? 

What in-game statistics contribute most consistently to a NFL running back's fantasy football point and point per game production?

How accurately does a NFL running back's previous season statistics predict what they are going to do the next year they play? 

It will help us to predict and analyse:
NFL running back analysis
To predict the outcomes an NFL running backs fantasy football productions based on receiving yards, rushing yards, touchdowns, etc.


**Data Resource:**

[Fantasy Pros] (https://www.fantasypros.com/) Relative attributes that we are interested in using from the data for our project: Position: Running Back, stats: rushing yards per game, rushing attempts per game(the time in which the running back carries the football), and touchdowns per game.


**Future Work:**

Following are the list of topics which if given an opportunity in future we might able to work on:
NFL running backs previous fantasy football season production
Heat map of rushing yards, receiving yards, etc. in relation to fantasy points
Pairplot to see where there is a stronger relationship for some variables such as rushing yards, touchdowns, etc. as opposed to others

**Domain Knowledge**

Two of our group members - Sean Oberer and Garrison Bolick, have been playing fantasy football for and know the ins and outs of how everything works with fantasy football. Although sports is mostly opinionated, running backs have the second highest point differential and score the most total points out of any other position in fantasy football (Orriss et al., 2021). Because of this, we wanted to focus on NFL running back given the time constraints since they have the most impact on the success of a fantasy football team.


**Data Preparation**

When we first started our project, we were initially going to predict what an NFL running back's total fantasy football point production would be. However, due to the violent nature and human aspect of the sport - we decided it would be best to predict what a running back's fantasy football point per game production will be since this will most accurately predict their actual fantasy football point production while taking into account games players may miss due to injuries, illnesses, personal matters, etc. because we changed our dependent variable to be fantasy points per game, we also had to change the unit of measure for our original independent variables (total passing yards, total touchdowns, total rushing yards, etc.) to total passing yards per game, total touchdowns per game, total rushing yards per game, etc. so that we can accurately predict what a running back's fantasy football production will be when they are on the field.

Data Understanding and Exploration

<img width="159" alt="Screen Shot 2021-11-13 at 3 37 01 PM" src="https://user-images.githubusercontent.com/59974878/141658337-c6159e01-72cf-4e88-9c3e-80335c1504e7.png">

<img width="158" alt="Screen Shot 2021-11-13 at 3 38 20 PM" src="https://user-images.githubusercontent.com/59974878/141658389-d6d3aac4-f554-4eab-91d7-39b41c5c8ea9.png">

Based on our pairplot above, we found that the in-game statistics such as passing yards per game, rushing yards per game, touchdowns per game, etc. were all linearly correlated with our dependent variable fantasy points per game. 

<img width="627" alt="Screen Shot 2021-11-13 at 3 39 38 PM" src="https://user-images.githubusercontent.com/59974878/141658436-7bd6417f-cabe-44b5-a4d9-70ba64eb5c62.png">


We created a heat map above to see how much of a correlation there was specifically between all of our independent variables (passing yards per game, rushing yards per game, touchdowns per game, etc.) with fantasy points per game. Based on our heat map, we found that rushing yards per game, rushing attempts per game, catches per game, targets per game, and total touchdowns per game have the most impact on our dependent variables, fantasy points per game. Rushing touchdowns per game also heavily influenced NFL running backs fantasy football points per game. Still, we decided to combine rushing touchdowns per game and passing yards per game since total touchdowns per game will be more of an accurate indicator for how many touchdowns that particular running back will produce. 

<img width="557" alt="Screen Shot 2021-12-07 at 9 40 17 PM" src="https://user-images.githubusercontent.com/59974878/145138801-50c036e8-edea-4b7a-ba08-a2242962383f.png">

We found the top 5 highest scoring NFL running backs in fantasy football based on the diagram above. We want to highlight these five players shown in the diagram above because they are going to be the most valuable players at the most valuable position that fantasy football teams are going to want to try to draft, so we want to see if they are going to have an upward or downward trend in their products based on our models.


**Machine Learning (Modeling)**

We decided to use three different machine learning models for our project: linear regression, random forest, and bagging ensemble. We chose linear regression because of the high correlation between an NFL running back's game stats, such as passing yards per game, rushing yards per game, touchdowns per game, etc., and their fantasy points per game. After running our linear regression model, we ran into some overfitting problems, which we will discuss in the evaluation. After running into our overfitting problems, we wanted to create a couple of ensemble models because of their excellent predictive performance. 

**Evaluation**

Based on our R squared values, our linear regression model for predicting FPTS/G was the most accurate, with 99.97% of our data fitting the regression line. As a result of our highly high R squared value, our model was exact with our data but wasn't the best for predicting an NFL running back's fantasy football point per game production for future seasons since the predictions were close to the data set we had. We also ran into another problem with identifying the predicted points per game, as we intended to when we first began our project. As a result of this, our predictions are somewhat limited in how helpful they can be for someone who plays fantasy football unless they have the data that we used so that they can go back and search for the player using their Rank column from our data that is displayed with our predictions. Our random forest model had an R squared value of .9394, meaning that 93.94% of the data fit the regression line and our ensemble bagging model had an R squared value of .9175, meaning that 91.75% of our dataset fit the regression line. Because of the overfitting issues, the predictions from our random forest and bagging ensemble models might be best to predict what an NFL running back's fantasy football points per game will be based on their previous season's statistics.


**Conclusion**

One of the unique things about our project and dataset was that most predictive models for fantasy football are used to calculate the total fantasy points that a player will score all season. Although their total fantasy points are a valuable metric, fantasy points per game are much more valuable to predict because they take out football's randomness. A player season fantasy football point total could be highly affected for various reasons such as missing games due to injuries, illnesses, suspensions etc.; any missed game will affect an NFL running back's total fantasy football points scored for the season. By predicting their fantasy points per game, we can best predict a running back's production when they play since we can't accurately predict when they will get injured or won't play. We did not have to deal with data imbalance in our project. When we downloaded our data, we had over 270 running back records for each season where 150-200 out of that 270 would have very low or no stats because they don't play a lot in an actual game. Because of that, we deleted those records for those running backs since the most important players will only be the ones that are playing and not just on the active roster. We did not have any outliers that needed to be addressed, nor did we need to attribute our data. We created half of the metrics that we used for our project since the data we had initially had the players total passing yards, total rushing yards, and soon so, we converted all of them to be on a per-game basis. The process we used for evaluation was the R squared model to tell us how much of our dataset fit the regression lines of the predictive models we created. Our linear regression model had the highest R squared value. We ran into a few problems along the way in our model creation process. Our first problem was that the linear regression model we created was extremely overfitted. We weren't sure how to solve this since most of our features were necessary to predict a running backs fantasy points per game, and our predictions would not be nearly as accurate or valuable without those features. Because of this, we created a random forest and bagging ensemble method using all of the same features to see if we could make an accurate model and one that was not overfitted. We also ran into another problem of identifying the player for the predicted fantasy football points per game without having our data set to match the players rank with the expected value for their fantasy points per game. Because of this, our models wouldn't be practical for use by the average person since they would have to have our data set and the knowledge to know to match the players rank up with their point prediction. Given the time constraints of our project, there wasn't anything we could do in the time allotted. Still, given the time, we could create ID values for each player to have a universal identifier for each player that we can associate the predicted fantasy points per game with. In the future, we would like to update our data so that each player has an ID that can be associated with their predicted points per game. Additionally, we would like to add individual player characteristics outside of game statistics such as height, weight, 40 yard dash time, etc., to see if any of that impacts an NFL running back's fantasy points per game. For individuals who want to use our work - you will have to use their fantasy football rank associated with the running back predicted fantasy football points per game with our data set to identify which player that expected value belongs.

**References**

Orriss, J., Planas-Arteaga, S., Yen, P., &amp; Worthy, C. (2021, June 5). The importance of running backs in fantasy football. CROW WORTHY. Retrieved December 8, 2021, from https://www.crowworthy.com/posts/the-importance-of-running-backs-in-fantasy-football/. 


