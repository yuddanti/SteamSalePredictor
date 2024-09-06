# SteamSalePredictor
Predicts when a game will go on sale on Steam using historical price data from SteamDB

### Why make this?
I got tired of waiting of games to go on sale by constantly checking Steam, so I decided to make this little project to see if I could predict when a game will go on sale using data from SteamDB. I'm still waiting for the game to go on sale by the way (but I hope the model is correct in its predictions!)

### Datasets

| File | Game | Release Year | Source |
| ---- | ---- | ---- | ---- |
| [chart.csv](chart.csv) | Outer Wilds: Echoes of the Eye | 2021 | https://steamdb.info/app/1622100/ |
| [chart2.csv](chart2.csv) | Portal 2 | 2011 | https://steamdb.info/app/620/ |

While the original datasets had a relatively limited number of records due to SteamDB only tracking when the price of a game changes, I expanded the original datasets by filling in missing dates where the price stayed the same. This dramatically improved the accuracy of the models since there were more examples to pull from. I also excluded the price record's year while training the model since it would have no impact on the sale date of a game when used for future sale date prediction.

I chose these two datsets because of the difference in how long their respective games have been available on Steam. Outer Wilds: Echoes of the Eye was only published in 2021, while Portal 2 was published in 2011. I wanted to compare the accuracy of the models based on how much data over time was available for them to pull from. From my limited testing, it seems that games that have been available for a shorter period have varied predictions, while games that have been available for a long time tend to have more stable predictions.

### Results

| Model | Accuracy (chart.csv data) | Accuracy (chart2.csv data) |
| --------| ------- | ------- |
| Basic Decision Tree* | 0.81    |  0.87  |
| Optimized Decision Tree | 0.79     |    0.88  |
| Basic Neural Net | 0.85    |  0.88    |

*without optimized parameters from grid search cross validation

### Future

I plan to test more varied models and more datasets to see differences in accuracy for the models depending on the length of time the game has been available on Steam.
