---
layout: post
title:  "Summoning All Superheros: Web Scrapping 200 Top Superhero Movies"
author: Amber Aiwohi
description: Everyone loves superhero movies. This post shows how to collet data about the top 200 superhero movies of all time by web scrapping. 
image: /assets/images/supershirt.jpg
---
# Introduction
We've all seen our fair share of superhero movies. They're so popular nowadays that it's impossible to go on social media without seeing a new trailer for the next superhero movie coming to theaters soon. Whether you're team Marvel or team DC, there's no denying that superhero movies have been, are, and will continue to be a huge hit. But what makes these movies so good? The focus of my data collection, exploration, and analysis stems from the common traits of the top 200 superhero movies. These traits include runtime, genre, rating, and more. 

![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/supercomic.jpg)

Complete code and data can be found at [this GitHub repo](https://github.com/AmberAiwohi/superheros).

# Data Collection
## Tools
Python and specifically the Requests and Beautiful Soup packages were used to web scrape [this collection of superhero movies](https://www.imdb.com/list/ls074940992/?sort=list_order,asc&st_dt=&mode=detail&page=1). Because I'm not gaining any monetary value or praise from the data I scraped, it is ethical for me to use this data as I strive to increase my data analysis skills. I implemented good scraping practices by not changing or ignoring any information found on the website as I created the dataframe. I also would like to thank the creators of the website for compiling all the information in one place. Below is how I web scraped and created the movies dataframe. 

## Step 1: Create Beautiful Soup Object
After choosing which website you wanted to scrape, load the url into an object.
```
url = "https://www.imdb.com/list/ls074940992/"
```
Creating a beautiful soup (bs) object of the request text allows you to search for and extract the information you want. 
```
r0 = requests.get(url)
bs = BeautifulSoup(r0.text)
```

## Step 2: Extract Wanted Tags
Knowing what html code contains the information you want can be tricky. To search for this specific code, right click on the webpage you're scraping and click 'inspect.' Enable inspection by your curser and explore the parts of the webpage you are interesting in scraping. The information you want is likely inside of a nested tag. I like to think of these tags as Russian nesting dolls. In the example below, the first tag we're interested in is a div tag. Next, we navigate to a h3 tag. Finally, the title of the movie is found in an a tag. The title was found in a tag within a tag within a tag, just like smaller dolls are nested within bigger dolls. If needed, specify the tag by the class as seen below. 
```
# extract the div tag 
div = bs.find_all("div", {"class": "lister-item-content"})
```
Loop through to pull wanted information from tags. I used list comprehension to hold the information.
```
# extract title
titles = [d.find('h3').find('a').text for d in div]

# extract year
year = [d.find('h3').find('span',{"class":"lister-item-year text-muted unbold"}).text.strip('()') for d in div]

# extract genre
genre = [d.find('p').find('span',{"class":"genre"}).text for d in div]
```
Sometimes the above method of extracting the information will throw an error. This is most likely because there are missing values that the code doesn't know what to do with. In this case, create a function to assign a None value to those missing values. Call this function to perform the extraction. 
```
# create function to extract rating
def pull_rating(d):
  try:
    r = d.find('p').find('span',{"class":"certificate"}).text
  except: r = None
  return r
  
# call function to extract rating 
ratings_pulled = [pull_rating(d) for d in div]

# create function to extract runtime
def pull_runtime(d):
  try:
    r = d.find('p').find('span',{"class":"runtime"}).text
  except: r = None
  return r
  
# call function to extract runtime
runtimes_pulled = [pull_runtime(d) for d in div]
```
Below is another method of how to extract wanted information: using a for loop. When extracting the gross for each movie, I had to index to the tag I wanted since there were multiple tags named the same thing, having the same class. I created an empty list, then looped through all the div tags to pull the gross, then added or appended those values to the empty list. 
```
# for loop to extract gross
gross = []
for d in div:
  try:
    gross.append(d.find_all('p',{"class":"text-muted text-small"})[2].find_all('span',{'name':'nv'})[1]['data-value'])
  except:
    gross.append(None)
gross
```

## Step 3: Create a Dataframe
Once you have all the information you want, it's time to put it into a dataframe. Doing this allows you to explore the data. Create a dataframe, then add however many columns you want with their corresponding values. 
```
# create dataframe of movies 1-100
df = pd.DataFrame (titles, columns = ['Title'])
df['Year'] = year
df['Rating'] = ratings_pulled
df['Runtime'] = runtimes_pulled
df['Genre'] = genre
df['Gross'] = gross
```
You now have an easy-to-read dataframe that allows you to have fun with exploring the data!

# Conclusion
![Figure](https://github.com/AmberAiwohi/my386blog/raw/main/assets/images/super.jpg)

In this post, I explained how I web scraped in order to compile a dataframe of 200 superhero movies. I plan to use exploratory data analysis to find any trends or similaries among these movies. What makes up a great superhero movie? Let's find out! 

If you have any questions, comments, or concerns, please leave them in the comments below. I'd also love to know, what's your favorite superhero movie?
