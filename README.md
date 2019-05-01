# Sabermetrics_Final
Final project for CSCI 4831 - Sabermetrics

## In this repo:  
* Final_Project.ipynb: Jupyter notebook containing all the code and graphs for this project.  
* Project_Initial_Description.pdf: The initial project proposal for shift rating.  
* README.md: This document!  
* Sabermetrics_Final_video.mov: Video showing demonstration of this statistic  
* player_id_map.csv: csv file used to find player's MLB id numbers  
* stats_shift_2018.csv: Statcast data for all instances of a shifted infield or outfield (2018)  
* stats_shift_2016.csv: Statcast data for all instances of a shifted infield or outfield (2016)  

## Statistic Explanation - Shift Rating  
I created a new statistic called "shift rating." This statistic evaluates how good a player is at "beating the shift" relative to the rest of Major League Baseball. This stat can be used to see how effective a shift is on a certain player, and influence a manager's decision to implement such an alignment. Alternatively, it can show a hitter that he is, perhaps, rarely beating the shift, and should change his approach when at the plate.  

Shift rating is calculated by the following:  
shift-rating = (((H + SF)/(AB + SF) - shift_mean) / shift_point) + 100

There are some interesting things to unpack here. In this calculation, H, SF, and AB stand for the hits, sacrifice flies, and at bats the player had while there was some sort of non-standard alignment. Shift_mean is the league average shift average and shift_point is the shift_mean / 100. Essentially, this calculation creates a number that has 100 as its average value, and each point increase or decrease from 100 equates to a 1% increase or decrease in that player's shift-beating ability. This is similar to park-adjusted statistics like ERA+ or wRC+, however, shift rating is not park adjusted.  

Another important note is that "non-standard alignment" is being defined here by anywhere statcast had either a "shifted" or "strategic" infield or outfield alignment listed. Shifted alignment refers to more than 2 infielders or outfielders on one side of the field, an obvious shift, whereas strategic refers to an alignment which isn't an explicit "shift" but is clearly a non-standard alignment put in place for that specific batter. The shortstop playing direcly behind second-base, or the second baseman acting as a fourth outfielder, could be examples of a strategic alignment.  

Also, you can see above that this statistic is, in a way, treating sacrifice flies as a "hit." I chose to do this because I figured that a hitter's goal with runners on base is to advance or score those runners. A sacrifice fly does just that. Therefore, I would consider a sacrifice fly a successful at bat, and thus beat the shift.  

I decided to create shift rating because I don't believe there are any good metrics on player's behavior in the shift. The shift is clearly an effective tool, or else we wouldn't see such a rise in its usage over the last few seasons. However, there could be some diamonds in the rough, so to speak, in players that are overlooked even though the shift doesn't affect them as much. If managers and GMs can put together a lineup of players that have good shift ratings, then there wouldn't be much an opposing manager could do by way of defensive alignment to decrease offensive production. This would be a huge advantage for the hitting team.  

Given its calculation, shift rating is most closely related to batting average. One could think of it as "shifted hits" over "shifted at bats," however I choose to think of it more as "successful shifted plate appearances" over "shfited attempts." Shift rating does not take into account walks or hit by pitches, because those are not a good indicator of the player's shift beating ability specifically. Therefore, it's hard to classify either the numerator or the denominator as strictly at bats or plate appearances.  

Despite its relation to batting average, though, the correlation between the two was not very high. If we look at a player's shift rating for the entire season and compare it to their batting average, we get an r-squared value of around 0.21. If we look at an individual part of the season, like early, mid, or late season, the r-squared value dives below 0.1. Obviously, shift rating is not a great predictor of batting average. However, I think a player's natural ability has a lot to do with their shift rating. Beating the shift, in my opinion, shows a hitter that has incredible bat control and is experienced enough to make adjustments on the fly. Batting average has a lot more to do with luck. So perhaps a low correlation isn't all that surprising. One way to improve shift rating, though, would be to factor in what successful at bats do actually result in the ball being hit to the other side of the shift, where the fielders are vacant, and what successful at bats are simply from finding a hole on the heavily guarded side, or from a bloop hit into the shallow outfield. This would require some more statcast data, and isn't out of the realm of possibility. However, I think shift rating as is still tells a compelling story, because the shift, by definition, shouldn't allow many balls to simply find holes since there aren't as many to find. 

Overall, shift rating is a good start to being able to look deeper at player's ability in certain situations that weren't very prevalent even ten years ago. As shifts are used more and more, I believe that the hitters should learn to adjust. Eliminating the shift by way of rule changes ruins a crucial aspect of the game: defensive player mobility. With shift rating, though, we can see what players are close to making that adjustment, starting to hit to the opposite field more, and are in general not held to the stereotypical shift stigma. 


