# **Baseball Web Scrapping**

Baseball is often referred to as America’s pastime, with a rich history, abundant statistics, and loyal fanbas it is also considered a data rich sport. However, these information is stored in webpages like [Baseball Reference](https://www.baseball-reference.com). The main focus of this project is to web scrape baseball reference to gather this data and store in a AWS RDS database to be used for future statistical analysis.

*Side-note:*  Although there are python libraries such as [baseball-scraper](https://pypi.org/project/baseball-scraper/), I took this project as a personal challenge to refresh web scrapping abilities and put them in practice with a topic that I am passionate about.

## Project Development

### Exploring Baseball Reference

First we need to identify the data that we are interested in. If we visit the baseball reference page, we can find a header that reads "Scores".

![Scores Header](images/BR-Scores.png)

In here we can find a list of all the matches that took place in a specific season. For this project we are going to be focusing on the recent 2024 season. Searching in this page we can find a link that reads "boxscore" for everyone of the matches.

![Boxscore](images/BR_boxscores.png)

After clicking in this link we are redirected to a page that contains the information of that game. This information includes 4 tables that contain the batting and pitching stats of each of the two teams. Also it includes the metadata of that day that depicts the time, attendance of the match, etc. All this information is going to be captured and uploaded to the database.

![Match Data](images/BR_match.png)
