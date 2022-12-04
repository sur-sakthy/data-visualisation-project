# Commentary - describe the process of creating and interacting with the visualisation

Hey My name is Sakthi and I am going to describe the process of creating and interacting with my visualisation as well as the story that I want to convey.

First of all I'll talk about the dataset, my dataset is a collection of 21M game reviews from Steam on 300+ different games on the platform. There are 23 columns of attributes available in the dataset, and the ones that I chose to help me with my visualisation are:
- steam app id
- app name 
- language 
- review text
- creation timestamp

I created additional columns that aren't provided in the dataset, and they are 
- sentiment scores for the reviews and 
- game statistics such as average players over time

I want to correlate the review sentiment with the player engagement in the game. Essentially, I want to show that the more positive reviews a game has, the more players are willing to play the game. 

This is evident in the charts on the dashboard. All three charts I have presented are related. 
The top bar chart shows average players over time up until the present. 
The bottom line chart shows the sentiment towards the game - derived from the reviews
The bubble chart shows the percentage of positive, negative and neutral reviews for a particular game which can be selected from the filter.

I've chosen a bar chart with a neutral color for the average players to show clearly the player count over time.

I've chosen a line chart for the average sentiment with a bit of color: navy for positive and dark orange for negative to visually show which direction is not desired and which is.

Ideally I wanted the two graphs on the same chart, but I couldn't achieve that due to issues with the timestamp in the dataset.

Finally, the colors used for the bubble chart are red, green and yellow to align with our natural tendency to associate red with negative, green with positive and yellow with neutral. I've added labels as well as percentage scores inside the bubbles because comparing the bubbles sizes to gauge percentage is not ideal.

I'm now going to show you how to interact with my visualisation to view the results for different games.
