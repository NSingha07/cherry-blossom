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

The prediction of peak bloom is an interesting research project that requires the use of historical data to develop models that can accurately forecast the blooming date for future years. I used data from 1981 to 2022 and identified year, month, temperature, humidity, and windspeed as independent variables for predicting the bloom day. However, since data for the blooming month is not available for future years, I employed a glm regression model with a binomial family to predict the month first. I employed location, year, temperature, daytime, moon phase, dew, and humidity as independent variables. The model achieved 77% accuracy in predicting the month on the test dataset.
Having predicted the month for future years, I fit a multiple linear regression model to predict the peak bloom date using year, month, temperature, humidity, and windspeed as independent variables. The temperature variable was transformed to achieve normality, and the model was evaluated using various statistical measures. The results indicated that the model explained 64% variability on the training dataset, and the standard error was low at 4.556. The regression model was significant at the 95% level of significance, with a p-value of less than 0.05.
The models developed in this project can be used to predict the peak bloom date for future years from 2023 to 2032. These predictions are essential for farmers and growers who rely on the blooming of flowers to plan their activities. 
Furthermore, the models can be extended to other regions and flowers to aid in their cultivation and management. The project's success demonstrates the value of historical data in developing predictive models and the importance of employing different statistical techniques to achieve accurate predictions. Overall, the project provides a useful framework for predicting the peak bloom date, which can be applied to various fields, including agriculture, horticulture, and climate science.
