# Football Forecasting

## Overview

`datasets` contains set of data used in Poisson Regression to predict match scores [Source](https://www.football-data.co.uk/englandm.php)

`FootballForecasting` contains set of strategy used in the football forecasting competition

## Strategies

`Arithmetic Value Betting` (Main strategy) - Decimal odds from several bookmakers are scraped and inverted to find the probability of each event occurring.The mean probability of home wins,away wins and draws for each match are then taken to form the average fair estimation. Poisson model to predict the scores for each match and assigned the confidence weightings using the average fair estimation measured before.

`Population` - if the home team won most of its previous matches as compared to draws or losses, predicted home goals is equal to the mean home goals in games where the home won, predicted away goals is equal to the mean away goals in games where the home won and vice versa.

`All 2-1` - submit all predictions as 2-1

`Actual Betting` - Arithmetic Value Betting strategy used in actual football betting

## Scoring metric used

$Accuracy = 1 - \frac{(\frac{|O_h-P_h|}{1+P_h})+(\frac{|O_a-P_a|}{1+P_a})}{2}$

O = actual goals, P = predicted goals, h = home, a = away

Accuracy is multiplied by a weighting dependent on the confidence weight allocated to the match to derive the score obtained from a match

2 additional points are given for correct score predictions

## Approach to the competition

Intuitively, a prediction of (0,0) should never be made regardless of the output from the regression model as the absolute value of the difference between actual goals and predicted goals is used. This is shown in `Expected Accuracy`

The rules required that each participant was a student of the university with a valid university email addresses. Since there was no mentions regarding collusion, and that the predictions tend to be right in the long run, I got a few willing participants and submitted predictions with slight variations, (e.g. one model would submit (1,1) with a confidence of 20 while the other would submit (2,1) with a confidence of 20)

Infinite monkey theorem stated that as long as I have an infinite number of monkeys exhausting the possible combinations of football scores and confidence scores, one would emerge victorious. In my case, I had 4 monkeys (including me), and with that we all placed top 4 and won the entire prize pool
