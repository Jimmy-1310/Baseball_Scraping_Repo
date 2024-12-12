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

### Capturing the Information

When developing the code that will extract the information from the page HTML first I developed a "Test Enviroment" so that I can explore the page and see if the code will gather the information and store it as wished. First, the file [Match_Scrapping_Test_Env.ipynb](TEST_ENV/Match_Scrapping_Test_Env.ipynb) is where I tested the code so that It would gather the information from a specific match. After having the code and structure it as a function, I then proceeded to create file [Baseball_Season_Scrap_Test_Env.ipynb](TEST_ENV/Baseball_Season_Scrap_Test_Env.ipynb) where I explored the season page and stablished how the code should loop around all the matches and gather the data.

*Importand Findings:* It was during this stage of the project that I was able to refresh my knowledge regarding HTML files and selenium to webscrape the data. At first I used the "Requests" library to gather the HTML from the webpage, however we needed to wait for the page to fully load. For this I changed to selenium to wait until the page is fully loaded before getting the HTML. Also a benefit of selenium at this stage is that it gives the option to see the web browser work in real time. This gave me a usefull troubleshooting tool to identify where the code was getting stuck, if it was accesing the right page, etc.
