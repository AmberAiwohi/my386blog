---
layout: post
title:  "Trends of Superhero Movies"
author: Amber Aiwohi
description: Using exploratory data analysis to visualize any trends that superhero movies have. 
image: /assets/images/supergirl.jpg
---
# Introduction
In my [last blog post](https://amberaiwohi.github.io/my386blog/2023/03/13/data-collection.html), I explained how I used web scrapping to gather data about the top 200 superhero movies. Since I now have a dataframe to work with, I'm excited to share how I used exploratory data analysis to learn more about these superhero movies and see if I can find any similaries or patterns. 

# Let's Explore (EDA)
There are many different ways to determine the success of a movie. Some ways include looking at the Rotten Tomatoes score or counting how many tickets were sold opening weekend. For this EDA, I'm going to be identifying the success of a movie based off of its gross. I wanted to see if a certain genre, runtime, year, or rating was particularly popular among superhero movies. My EDA graphs and findings can be found below whereas my EDA code can be found in [this Github repository](https://github.com/AmberAiwohi/superheros).

## Runtime
When looking at the plot below, we can see that there seems to be a positive relationship between the length of the movie and its gross. Longer movies seem to have a higher gross. This may be due to the fact that people want lots of bang for their buck. If they're going to spend $10 on a movie ticket reguardless of how long the movie is, it might as well be for a longer movie where audience members can sit in the comfy theater seats with a big screen and surround sound. The farthest and highest point of this graph is important to take note of. This point represents the Avengers: Endgame movie, which was thee movie to see when it hit theaters. However, this may be an outlier. 

<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/runtime.html"
  style="width:100%; height:500px;"
></iframe>

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/runtime_lowess.png)

## Rating
From the previous graph and the graph below, we can see that PG-13 movies may be the most popular rating among superhero movies. Reguardless of whether it's the most popular rating, we can also see that PG-13 movies bring in the most money with a higher gross than movies rated differently. I think this may be due to the large age range that PG-13 movies tend to attract. Rated R movies restrict the age of viewers, and PG movies aren't always created for those who will spend money throughout the week to go to the movie theater. PG-13 is the rating to be for superhero movies wanting a higher gross. 

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/rating.png)

## Genre
It was somewhat difficult to perform EDA with reguards to the genre because the genres collected were specific and consisted of multiple genres indicating each movie. However, we are still able to learn more about the data from our plots. First, I was curious to know what the top superhero movie genre is in terms of frequency, which we can see is action, adventure, sci-fi. 
![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/genre.png)

We can also note that most of the 200 superhero movies explored are classified as an action movie. From our second plot, it's difficult to draw any conclusions, but we are able to interact with the graph and explore the movies grouped by genre. 

<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/genre.html"
  style="width:100%; height:500px;"
></iframe>

## Year
When looking at the year, I was curious as to which year had the most movies produced. From the bar chart below, we can see that 2011 has the highest number of superhero movies produced with 11 movies. 
![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/mov_per_year.png)

From the Year vs. Gross plot, we see a slight positive trend as the gross seems to increase as the years go by. This could be an indicator that superhero movies have become increasingly popular or better produced over the years. It may be important to note inflation costs, which may be correlated to increased gross. 

<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/year.html"
  style="width:100%; height:500px;"
></iframe>

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/year_lowess.png)

# Conclusion
This EDA helps us visualize a few patterns:

- The longer the runtime, the higher gross.
- PG-13 movies are the highest grossing on average. 
- Superhero movies classified as action, adventure, sci-fi are the most common.
- 2011 had the most superhero movies produced.
- Gross increases as the years pass.

What else do you notice from these plots? What questions do you have about this data and want answered through EDA? Please feel free to leave any questions or comments in the section below. 

For complete code and the dataframe I scrapped, refer to [this repo](https://github.com/AmberAiwohi/superheros).
