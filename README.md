Watching Liverpool and Man City fighting for the top spot in the the ongoing EPL and bored on a weekend I got curious to come up with metrics to quantify such intense rivalry across the length of a long season. Who likes a dull league where the top spot gets sealed only after a few games. Metrics are useful as an analysis tool and a way to look at subjective elemtents of past data (competition in the league in this case). These representations can be useful in certain modeling tasks such as a regression model of TRP (viewership etc).

I used the historical EPL data here: https://datahub.io/sports-data/english-premier-league to compute the metrics over previous seasons. The original data as shown below has information about teams and results of each match. I aggreated this data and prepared results table at the end of each round.

__Metric 1__ (_Rank change_): <br>
Given the results table over two consequetive weeks this metric computes the the sum of changes in the leader board positions compared with the previous week. For example given this data over two weeks:


| Week-1 | Week-2 |
| --- | --- |
| a | a |
| b | c |
| c | d |


the metric outputs a value of 2 for round 2.

__Metric-2__ (_Bag size_): <br>
This metric computes how many teams are within a certain points difference of each position, summed across every position on the leader board. The intuition behind the metric goes that more the teams are closer to each other in term of number of points more the interest in the league is alive (Man United, Arsenal, Tottenham and Chelsea fighting for the position in top 4 and a chance to play the champions league. Consider the leaderboard for week k.


| Club | Points |
| --- | --- |
| a | 80 |
| b | 78 |
| c | 75 |
| d | 70 |



with the points diff of 3 (one match) the metric outputs a value of (1 + 2 + 1 + 0) = 4 for this round. a's bag has b it; b has a and c while d has 0.

__Metric-3__ (_Weighted bag size_): <br>

Bag sizes are inverse weighted as per the position on the leaderboard. Intuitively there is most interest in fight for higher ranks up the leaderboard (other weights could be used to focus more on certain positions etc).

The plots below (aggregated across season and variation in a single season) compare each metric values across seasons and for sections of the leaderboard (top position, top 4, relegation zone and full leaderboard) to derive interesting insights across seasons. 

Invite the subject matter experts and fans to comment send feedback/validate/in-validate the findings in the plots for this fun little project.

Toggle the button below to view code for implemenation of these metrics using pandas and numpy.
