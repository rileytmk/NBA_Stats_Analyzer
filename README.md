# NBA_Stats_Analyzer

## Introduction / General Information
I created this project for fun after joining a fantasy basketball league with my friends. For those who aren't familiar with fantasy basketball, it's a competition where participants draft real-life NBA players to create a team. Players earn points based on the stats they achieve in game and the goal is to outscore the competition. As someone who enjoys competition, I had the desire to create a tool that could predict the performance of NBA players in an upcoming game.

Currently, the core functionality of the project is a machine learning model that precicts the amount of points a player will score in their next game based on their past 5 performances. Using the nba_api, I am able to access historical data from nba.com and store it into data frames

## Features
- Data Collection: Retrieves historical data and stored in pandas dataframes for starters from the 2023-24 NBA season using functions from the nba_api to use as training data.
- Machine Learning Model: Utilizes a Linear Regression Model from scikit-learn train data from the 2023-24 season and recognize patterns.
- Prediction: Given a Player's past 5 games the model is able to predict the amount of points they will score in their next game.

## Future Goals
- Incorporate additional data sources such as:
    - Defensive rating of opposing team
    - A player's historical performance against specific teams
    - Other stats (assists, rebounds, etc.)
- Improve accuracy by experimenting with different machine learning models
- Use generative AI to create player data that mimics realistic performance

## How it works
Starts by retrieving data 





## Example

```python
# Gets points scored in the past 5 games for nba player Victor Wembanyama
def predict_next_points(games):
    games = [games]
    next_points = model.predict(games)
    return next_points[0]

player = Player("Victor Wembanyama")
player.player_id = player.getPlayerId()
games = player.getGameStats2425()
past_5 = player.getPast5Pts(games)
past_5.reverse()
print(past_5)
predicted_points = predict_next_points(past_5)
print(predicted_points)
```

```python
# Ouput
[30, 20, 23, 30, 27] # past 5 games
25.801693715428033 # predicted points scored in next game
```

