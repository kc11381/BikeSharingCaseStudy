# Bike Sharing Predictors
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

   1. Which variables are significant in predicting the demand for shared bikes.
   2. How well those variables describe the bike demands


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
A US based bike-sharing system wants to know
   1. Which variables are significant in predicting the demand for shared bikes.
   2. How well those variables describe the bike demands
- We need to find the predictors and their effect for count(total bike shared) so that company can take an informed decision.
  A linear regression model is used here.
- Dataset - Bike sharing dataset is used. 
  - It is provide at upgrad (https://ml-course2-upgrad.s3.amazonaws.com/Linear+Regression+Assignment/Bike+Sharing+Assignment/day.csv)
    =========================================
    Dataset characteristics
    =========================================	
    day.csv have the following fields:
	
	- instant: record index
	- dteday : date
	- season : season (1:spring, 2:summer, 3:fall, 4:winter)
	- yr : year (0: 2018, 1:2019)
	- mnth : month ( 1 to 12)
	- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
	- weekday : day of the week
	- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
	+ weathersit : 
		- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
		- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
		- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
		- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
	- temp : temperature in Celsius
	- atemp: feeling temperature in Celsius
	- hum: humidity
	- windspeed: wind speed
	- casual: count of casual users
	- registered: count of registered users
	- cnt: count of total rental bikes including both casual and registered

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
- We have variables like temp which is lineraly related to cnt. So linear regression makes sense here.
- Predictors for cnt and their coefficients are
   const         0.0984
   yr            0.2336
   workingday    0.0555
   temp          0.5395
   windspeed    -0.1637
   summer        0.0745
   winter        0.1153
   jan          -0.0460
   july         -0.0360
   sep           0.0869
   sat           0.0676
   Light_Snow   -0.2878
   Misty        -0.0799
- Equation of the model is
   cnt = 0.2336yr + 0.0555workingday + 0.5395temp - 0.1637windspeed + 0.0745summer + 0.1153winter - 0.0460jan - 0.0360july + 0.0869sep + 0.0676sat - 0.2878Light_Snow - 0.0799Misty + 0.0984
- There is a significant rise in count(cnt) from 2018 (0) to 1 (2019).
- There is a drastic drop in count(cnt) in the month of Dec and Nov.
- When wheather is clear then count(cnt) is higher and when its Light and snow its drastically low.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- python - 3.9.7
- numpy - 1.20.3
- pandas - 1.3.4
- matplotlib - 3.4.3
- seaborn - 0.11.2
- sklearn - 0.24.2
- statsmodels - 0.12.2

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project was inspired by Linear Regression Model learning at Upgrade as part of AI/ML course.
- This project was based on [this tutorial](https://learn.upgrad.com/course/1991/segment/16594/129672/396956/2065942).


## Contact
Created by [@kc11381] - feel free to contact me!


## License
Dataset(day.csv) License
[1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{
	year={2013},
	issn={2192-6352},
	journal={Progress in Artificial Intelligence},
	doi={10.1007/s13748-013-0040-3},
	title={Event labeling combining ensemble detectors and background knowledge},
	url={http://dx.doi.org/10.1007/s13748-013-0040-3},
	publisher={Springer Berlin Heidelberg},
	keywords={Event labeling; Event detection; Ensemble learning; Background knowledge},
	author={Fanaee-T, Hadi and Gama, Joao},
	pages={1-15}
}

<!-- You don't have to include all sections - just the one's relevant to your project -->
