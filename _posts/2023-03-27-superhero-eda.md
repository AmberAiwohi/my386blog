---
layout: post
title:  "Trends of Superhero Movies"
author: Amber Aiwohi
description: Using exploratory data analysis to visualize any trends that superhero movies have. 
image: /assets/images/supergirl.jpg
---
# Introduction
In my [last blog post](https://amberaiwohi.github.io/my386blog/2023/03/13/data-collection.html), I explained how I used web scrapping to gather data pertaining to the top 200 superhero movies. Since I now have a dataframe to work with, I'm excited to share how I used exploratory data analysis to learn more about these superhero movies and see if I can find any similarities or patterns. 


# Let's Explore (EDA)
There are many different ways to determine the success of a movie. Some ways include looking at the Rotten Tomatoes score or counting how many tickets were sold opening weekend. For this EDA, I'm going to be identifying the success of a movie based off of its gross. I wanted to see if a certain genre, runtime, year, or rating was particularly popular among superhero movies. My EDA graphs and findings can be found below whereas my EDA code can be found in [this Github repository](https://github.com/AmberAiwohi/superheros).

## Runtime
Are there any patterns between runtime and gross?

<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/runtime.html"
  style="width:100%; height:500px;"
></iframe>

In the above plot, I color coded the points by rating to see if there were any similar trends. We can see that there seems to be a positive relationship between the length of the movie and its gross. Longer movies seem to have a higher gross. Feel free to interact with this plot by hovering over the points and seeing which points represent which movies. 

I also wanted to see if there was an overall trend without honing in on the rating. 

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/runtime_lowess.png)

In the graph above, we see the same positive trend between runtime and gross. The farthest and highest points in both graphs are important to take note of. These two points represent the Avengers: Endgame movie, which may be an outlier. 

## Rating
Are there any trends between movie rating and gross?

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/rating.png)

When looking at the above plot as well as the Runtime vs. Gross plot, we can see that PG-13 is the most common rating among superhero movies. We can also see that PG-13 movies bring in the most money with a higher gross. This could be due to the large age range that PG-13 movies tend to attract. Rated R movies restrict the age of viewers, and PG movies aren't always created for those who will spend money throughout the week to go to the movie theater. PG-13 is the rating to be for superhero movies wanting a higher gross. 

## Genre
What is the most common superhero movie genre? 

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/genre.png)

It was somewhat difficult to perform EDA with reguards to the genre because the genres collected were specific and consisted of multiple genres for each movie. However, we are still able to learn more about the data from our plots. In the plot above, unfortunatly the genre's for each bar are cut off, but you're able to view this graph when looking at the [.ipybn file](https://github.com/AmberAiwohi/superheros/blob/main/superheroEDA.ipynb) in [this repository](https://github.com/AmberAiwohi/superheros). You're going to have to trust me, but action, adventure, sci-fi movies are the most common. 

<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/genre.html"
  style="width:100%; height:500px;"
></iframe>

We can note that most of the 200 superhero movies explored are classified as an action movie. From the Genre vs. Gross plot, it's difficult to draw any conclusions, but feel free to interact with the graph and explore the movies grouped by genre. 

## Year
In what year was the highest number of superhero movies produced? 

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/mov_per_year.png)

From the bar chart above, we can see that 2011 has the highest number of superhero movies produced with 11 movies. 

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/year_lowess.png)

From the scatter plot above, we see a slight positive trend as the gross increased with time. This could be an indicator that superhero movies have become increasingly popular or better produced over the years. It may be important to note that inflation costs may be a factor of increased gross represented on this graph. 

# Conclusion
This EDA helps us visualize a few patterns:

- The longer the runtime, the higher the gross.
- PG-13 movies are the highest grossing on average. 
- Superhero movies classified as action, adventure, sci-fi are the most common.
- 2011 had the most superhero movies produced.
- Gross increases as the years pass.

What else do you notice from these plots? What questions do you have about this data and want answered through EDA? Please feel free to leave any questions or comments in the section below. 

For complete code and the dataframe I scrapped, refer to [this repo](https://github.com/AmberAiwohi/superheros).
