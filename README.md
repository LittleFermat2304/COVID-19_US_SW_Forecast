# COVID-19_US_SW_Forecast
#### Collaborators: Jake Bell, Jonathan Hake, Sean Lovullo
##### Project completetion date: 6 May 2020 <br /> <br />

This project was done as a part of Point Loma Nazarene University's Applied Project course.  

For this project, we used the COVID-19 Global Forecasting (Week 4) data publically available [here on Kaggle](https://www.kaggle.com/c/covid19-global-forecasting-week-4) <br />

To view the HTML document of the project, please make sure that US_SW_COVID-19_Forecast.html, ConfirmedCases.gif, and Fatalities.gif are all in the same directory when opening the HTML file. If not, then the animations will likely not be able to be displayed in the file. <br />

#### Project Goals:
* Create predictions for three weeks for the number of confirmed cases and fatalities for the southwestern United States, including Arizona, California, Colorado, Nevada, New Mexico, and Utah  
* Add external data to add to model (collected NOAA weather data and population statistcs)
* Create various visualizations of results <br /> <br />

#### What I worked on in this project:  
* The data visualizations were my main responsibility. Most of the packages I used were in R's tidyverse (ggplot2 and gganimate), although I was able to get a map of only the selected states using the usmap package
* Assisted with data preparation tasks, using the dplyr package to filter out data for the select states and to join data, such as joining the new predictions to the data set
  - Used the lubridate package to transform the dates given in the .csv files into a variable "t" that counts the number of days since 22 January 2020.
* Helped develop the code to create the model, creating a linear model from the exponential growth of cases by getting the natural logarithm of the recorded target values

#### Details of project expereince <br />  
Creating data vizualizations for the project was my primary task. Intuitively, the first graphs I wanted to make were of each individual state's confirmed cases and fatalities, and then a comparison graph for confirmed cases and for fatalities in order to comapre how COVID-19 was affecting these states. Knowing that the model was going to be a linear model, I also decided to make graphics showing the linearity by making plots for the natural log of confirmed cases and of fatalities. <br />  
I was able to spend more time writing the code for the graphics earlier on, so not enough of the data preparation had been done yet to have data to use for the graphs, so I wrote my code thinking ahead so that I would have to change as little as possible once the data was ready. After that, I decided to help with the data preparation to have data to use to make sure that the visuals were appearing as they should. <br />  
As these graphs show, the predictions from the model do not seem to be an accurate fit. To have a finished product by the due date, we stuck with this model; however, if given more time, the model definitely would have been modified as it is quite an overestimate. <br />  
I finished the standard graphs earlier on in the timeline, but I particularlly wanted to learn how to create an animation so that I could better demonstrate the growth of COVID-19 over time. After researching which packages to use and how those packages worked, I finally settled on using the packages usmap and gganimate. I chose to use usmap because of the scope of our project. We were not creating predictions for the entire United States, so showing the entire country in the animation when only a small number of states were being used would be a waste. By using usmap, I was able to show only the 6 states I wanted. <br />  
I was already using ggplot2 and the tidyverse throughout the project, so using gganimate, which just extended the language of the tidyverse packages, made my life simple since I knew it would play nice with what I was already using. By about halfway through our project timeline, I had finished the animations for confirmed cases and fatalities, and had them written in such a way such that only minor changes needed to be made in order for the animation to include the prediction data. At this point, I spent time improving how the graphics looked and fixing errors. <br />  
Since we were nearing the due date and the model had not been developed yet, I was in a position to help and began to figure out how to piece that together. Searnching online, I discovered a package called modelr that would both make it easier to create the forecasted values and that is a tidyverse package, melding easily with the already imported packages. Using this package, our group was able to create the linear model using the COVID-19 data along with the collected NOAA weather data and population data. The part I particularly spent a good chunk of time figuring out was how to add the new data values to the previously existing confirmed cases and fatalities columns. Once I found a solution using an anti-join, I was able to fix errors for my visualizations and enjoy the final results.

