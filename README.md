# cherry-blossom
Variables

'location': location
'lat':Latitude
'long': Longitude
'alt':Altitude
'year': year of blossom
'bloom_date': date of blossom
 "month": month of blossom
"tempmax" : Avg. maximum temperature from december to february   
"tempmin" : Avg. minimum temperature from december to february   
"temp"    : Avg. temperature from december to february    
"dew"     : Avg. dew from december to february   
"humidity": Avg. humidity from december to february     
"precip"  : Avg. percipitation from december to february     
"snow"    : Avg. snow from december to february     
"windspeed": Avg. windspeed from december to february    
"moonphase" :  Avg. moonphase from december to february    
"solarradiation": Avg. solarradiation from december to february
"daytime": Avg. daytime (in sec) from december to february


Predicting the peak boom is an interesting project. To achieve this, I use historic data from 1981 to 2022. 
I choose.
“Year”: Blooming year
“Month”: Blooming month
“temp”: Avg. temperature for DEC to FEB
“humidity”: Avg. humidity for DEC to FEB
“windspeed”: Avg. windspeed for DEC to FEB
As independent variables to predict the “Bloom day”. 
Now my challenge is, data for the blooming month is not available for future years. So, I fit a glm regression model with a “binomial family” to predict the “month” first.

I use,
“Location”: Location
“Year”: Blooming year
“Temp”: Avg. temperature for DEC to FEB
“Daytime”: Avg. Daytime for DEC to FEB
“Moonphase”: Avg. Moonphase for DEC to FEB
“Dew”: Avg. Dew for DEC to FEB
“humidity”: Avg. humidity for DEC to FEB
as independent variables to predict the Blooming Month.
My model is 77% accurate while predicting the month on the test dataset.
Now that I have the Month for our future years. I go ahead and fit a Multiple linear regression model. 
bloom_doy = year + as.factor(month) + exp(temp) + humidity + windspeed

I transform “temp” to “exp(temp)” to achieve normality.
Residual standard error: 4.556 on 118 degrees of freedom
Multiple R-squared:  0.6626,	Adjusted R-squared:  0.6455 
F-statistic: 38.63 on 6 and 118 DF, p-value: < 2.2e-16

Now my model is explaining 64% variability on the training dataset. With a low standard error of 4.556.
And the p-value is less than 0.05. So, the regression model is significant at the 95% level of significance.
With the help of these two models, I predicted the pick bloom date from 2023 to 2032.
