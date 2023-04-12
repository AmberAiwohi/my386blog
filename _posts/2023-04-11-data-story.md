---
layout: post
title:  "Telling the Data Story of Superhero Movies"
author: Amber Aiwohi
description: A summary of the top 200 superhero movies' trends showcased through graphics. 
image: /assets/images/batman.jpg
---
# The Purpose
Within the past five years, superhero movies have become favorites of mine and whenever there's a new superhero movie being released, I make it a priority to watch it as soon as I can. I noticed that most of my friends and family also love superhero movies. Is it the action that pulls the audience in? Is it the length of the movie? Is it the time or year that we're living in that makes superhero movies so popular? Or it is a combination of multiple aspects? I was curious to find out, and that's where this data story begins.  

Are there any similaries or trends in runtime, rating, genre, and year published for the top 200 superhero movies? This is the question that has motivated my data analysis for my past two blog posts. First, I web scrapped [these top superhero movies](https://www.imdb.com/list/ls074940992/?sort=list_order,asc&st_dt=&mode=detail&page=1) and created a dataframe of the variables I was interested in. I explained the steps I took to web scrape in [this blog post](https://amberaiwohi.github.io/my386blog/2023/03/13/data-collection.html). I then created a variety of different plots to explore the data. To view these plots and for an in depth explaination of my findings, refer to [this blog post](https://amberaiwohi.github.io/my386blog/2023/03/27/superhero-eda.html). 

# The Data Story
<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/plot_1.html"
  style="width:100%; height:500px;"
></iframe>
In the plot above, two things stick out to me. The first is that the majority of movies on this plot are rated PG-13. The second is that there is a positive relationship between runtime and gross. We learn that PG-13 movies with a longer runtime have a higher gross, which we will interpret as being more popular. 

<iframe
  src="https://AmberAiwohi.github.io//my386blog/assets/images/plot_2.html"
  style="width:100%; height:500px;"
></iframe>
In our second plot, it is quite difficult to notice any trends. There may be a slight positive relationship between year and gross, however we can't be sure simply based off of this graph. Although it's difficult to see any trends among movie genre, when looking at the genre key to the right of the graph, we see that most superhero movies are classified as action movies. 

# The Wrap-Up
If I were a successful, high grossing superhero movie, I'd most likely be rated PG-13, have a longer runtime, and be an action movie. Each superhero movie is unique and there are many aspects that determine the sucess of a movie, but these are three simple similarities that we learn from this data story.

What unanswered questions do you have about this data? Please leave any questions or comments below and thank you for joining me on this superhero movie journey! 

To view my data, code, and all contents of this project, refer to [this Github repository](https://github.com/AmberAiwohi/superheros). 
