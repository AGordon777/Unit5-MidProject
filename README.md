# Unit5-MidProject

### Purpose

To analyze a library of chess matches and derive insights into optimal openings for different ELO levels, and to predict chances of success against different levels of opponents.

### Source data

https://www.ficsgames.org/download.html - Jan 2018 (~750,000 games)

https://database.lichess.org/#standard_games - also prepared but not used


### Documentation

'data preparation.ipynb' converts a text file containing the .pgn game data into a pandas dataframe and exports to .csv

'exploratory data analysis.ipynb' reviews this data and draws insights

### Summary

I converted the .pgn text string into a usable pandas Dataframe.

I then removed data that might corrupt the analysis - games ending by disconnection and draws/resignations with fewer than 5 moves played - on the assumption that something outside of the game ended it prematurely.

On this cleaned datset, I used MinMaxScaler and OneHotEncoder to build a simple predictive classification model, which I improved marginally by over-sampling games ending in a Draw.

I grouped ELO ratings of White and Black into quantiles and considered 'matched' games where both players were in the same ELO_quantile, and 'stretch' games where Black was in the ELO_quantile above White.

From these, you can draw conclusions on win-rate and commonly used opening sequences for White that optimise the chance of a White win.

Further areas to study would be:
- tracking the performance of an individual who's ELO increased dramatically to glean insights into good play
- creating a simple function that could play the optimised move for White/Black for a given set of moves already played

In both cases, I would need more data.

### Conclusions drawn

To increase the chance of White beating players of a similar rating, use English Openings.

To increase the chance of White beating players of a higher rating, use the Queen's Gambit!