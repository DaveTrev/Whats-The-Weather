![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

Welcome DaveTrev,

This is the Code Institute student template for deploying your third portfolio project, the Python command-line project. The last update to this file was: **August 17, 2021**

## Reminders

* Your code must be placed in the `run.py` file
* Your dependencies must be placed in the `requirements.txt` file
* Do not edit any of the other files or your code may not deploy properly

## Creating the Heroku app

When you create the app, you will need to add two buildpacks from the _Settings_ tab. The ordering is as follows:

1. `heroku/python`
2. `heroku/nodejs`

You must then create a _Config Var_ called `PORT`. Set this to `8000`

If you have credentials, such as in the Love Sandwiches project, you must create another _Config Var_ called `CREDS` and paste the JSON into the value field.

Connect your GitHub repository and deploy as normal.

## Constraints

The deployment terminal is set to 80 columns by 24 rows. That means that each line of text needs to be 80 characters or less otherwise it will be wrapped onto a second line.

-----
Happy coding!
"""
Todo list
colour program title  **
add menu options **
install time to create pause for user
give option to repeat program or quit
choose another city option on current and forecast

readme
## functionality i would like to add, generate current weather and give option to compare against historical data
## in the future look at tkinter and build a gui for this app
heroku deploy
"""

Resources Used for project ----
api from openweather.com
hiding api keys https://blog.netwrix.com/2022/11/14/how-to-hide-api-keys-github/#:~:text=So%20how%20can%20we%20hide,control%20(e.g.%2C%20gitignore).
configparser - reading config file, hiding api key
configparser - https://www.tutorialandexample.com/how-to-write-a-configuration-file-in-python
https://www.geeksforgeeks.org/python-ascii-art-using-pyfiglet-module/
youtube - https://www.youtube.com/watch?v=baWzHKfrvqw
youtube - https://www.youtube.com/watch?v=jpsmNr4-v4Y
setting timeout for requests - https://reqbin.com/code/python/3zdpeao1/python-requests-timeout-example
python checker - https://www.pythonchecker.com/
python import statements - https://careerkarma.com/blog/python-import/#:~:text=import%20Python%3A%20Using%20the%20from,can%20use%20the%20from%20statement.
https://www.geeksforgeeks.org/print-colors-python-terminal/
https://www.geeksforgeeks.org/print-colors-python-terminal/
https://stackoverflow.com/questions/42475681/using-openweather-json-api-how-to-fetch-the-temperature
https://www.studytonight.com/python-howtos/how-to-print-colored-text-in-python
----need to add requests.get
https://datagy.io/python-requests-timeouts/
https://en.wikipedia.org/wiki/ANSI_escape_code#Colors
https://towardsdatascience.com/prettify-your-terminal-text-with-termcolor-and-pyfiglet-880de83fda6b
https://stackoverflow.com/questions/39473297/how-do-i-print-colored-output-with-python-3
weather data and forecasts - https://medium.com/@joseph.magiya/weather-data-and-forecasts-from-open-weather-api-1636691d5ba
five day forecast open weather link https://openweathermap.org/forecast5
Time Series Analysis and Weather Forecast in Python - https://medium.com/@llmkhoa511/time-series-analysis-and-weather-forecast-in-python-e80b664c7f71
max min temp from stackoverflow javascript - https://stackoverflow.com/questions/55222100/how-to-get-min-and-max-temp-for-the-day-from-5-day-weather-forecast-js
Creating daily forecasts with python - https://www.tomorrow.io/blog/creating-daily-forecasts-with-a-python-weather-api/
rain print out  stackoverflow - https://stackoverflow.com/questions/68696505/how-to-find-rain-in-a-variable-for-openweathermap
date / time and converting to strings - https://www.programiz.com/python-programming/datetime/strftime
get datetime - https://www.programcreek.com/python/?CodeExample=get+datetime
css gradient background - https://cssgradient.io/


Data returned from open weather for current weather request "berlin"
{'coord': {'lon': 13.4105, 'lat': 52.5244}, 'weather': [{'id': 800, 'main': 'Clear', 'description': 'clear sky', 'icon': '01d'}], 'base': 'stations', 'main': {'temp': 6.29, 'feels_like': 3.99, 'temp_min': 4.49, 'temp_max': 8.3, 'pressure': 990, 'humidity': 90}, 'visibility': 10000, 'wind': {'speed': 3.09, 'deg': 210}, 'clouds': {'all': 0}, 'dt': 1681362490, 'sys': {'type': 2, 'id': 2011538, 'country': 'DE', 'sunrise': 1681359231, 'sunset': 1681408782}, 'timezone': 7200, 'id': 2950159, 'name': 'Berlin', 'cod': 200}

Data returned from open weather for forcast request "London"
b'{"cod":"200","message":0,"cnt":40,"list":[{"dt":1681635600,"main":{"temp":8.96,"feels_like":8.39,"temp_min":8.96,"temp_max":11.25,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":86,"temp_kf":-2.29},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":100},"wind":{"speed":1.57,"deg":261,"gust":2.44},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-16 09:00:00"},{"dt":1681646400,"main":{"temp":11.49,"feels_like":10.47,"temp_min":11.49,"temp_max":13.33,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":68,"temp_kf":-1.84},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":99},"wind":{"speed":2.28,"deg":275,"gust":1.72},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-16 12:00:00"},{"dt":1681657200,"main":{"temp":11.84,"feels_like":10.72,"temp_min":11.84,"temp_max":11.84,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":63,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":94},"wind":{"speed":2.96,"deg":272,"gust":3.4},"visibility":10000,"pop":0.04,"sys":{"pod":"d"},"dt_txt":"2023-04-16 15:00:00"},{"dt":1681668000,"main":{"temp":10.64,"feels_like":9.59,"temp_min":10.64,"temp_max":10.64,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":70,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":97},"wind":{"speed":1.08,"deg":295,"gust":1.89},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-16 18:00:00"},{"dt":1681678800,"main":{"temp":10.13,"feels_like":9.16,"temp_min":10.13,"temp_max":10.13,"pressure":1027,"sea_level":1027,"grnd_level":1024,"humidity":75,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04n"}],"clouds":{"all":100},"wind":{"speed":0.38,"deg":192,"gust":0.48},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-16 21:00:00"},{"dt":1681689600,"main":{"temp":9.75,"feels_like":9.75,"temp_min":9.75,"temp_max":9.75,"pressure":1027,"sea_level":1027,"grnd_level":1023,"humidity":78,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04n"}],"clouds":{"all":100},"wind":{"speed":0.76,"deg":111,"gust":0.9},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-17 00:00:00"},{"dt":1681700400,"main":{"temp":9.21,"feels_like":9.21,"temp_min":9.21,"temp_max":9.21,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":85,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10n"}],"clouds":{"all":100},"wind":{"speed":0.61,"deg":67,"gust":0.75},"visibility":10000,"pop":0.22,"rain":{"3h":0.19},"sys":{"pod":"n"},"dt_txt":"2023-04-17 03:00:00"},{"dt":1681711200,"main":{"temp":8.24,"feels_like":7.46,"temp_min":8.24,"temp_max":8.24,"pressure":1027,"sea_level":1027,"grnd_level":1024,"humidity":93,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10d"}],"clouds":{"all":100},"wind":{"speed":1.67,"deg":104,"gust":3.63},"visibility":10000,"pop":0.88,"rain":{"3h":0.8},"sys":{"pod":"d"},"dt_txt":"2023-04-17 06:00:00"},{"dt":1681722000,"main":{"temp":8.79,"feels_like":7.99,"temp_min":8.79,"temp_max":8.79,"pressure":1029,"sea_level":1029,"grnd_level":1025,"humidity":89,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":100},"wind":{"speed":1.77,"deg":81,"gust":3.29},"visibility":10000,"pop":0.14,"sys":{"pod":"d"},"dt_txt":"2023-04-17 09:00:00"},{"dt":1681732800,"main":{"temp":14.35,"feels_like":13.15,"temp_min":14.35,"temp_max":14.35,"pressure":1028,"sea_level":1028,"grnd_level":1025,"humidity":50,"temp_kf":0},"weather":[{"id":803,"main":"Clouds","description":"broken clouds","icon":"04d"}],"clouds":{"all":59},"wind":{"speed":3.04,"deg":59,"gust":4.39},"visibility":10000,"pop":0.08,"sys":{"pod":"d"},"dt_txt":"2023-04-17 12:00:00"},{"dt":1681743600,"main":{"temp":15.33,"feels_like":14.2,"temp_min":15.33,"temp_max":15.33,"pressure":1027,"sea_level":1027,"grnd_level":1024,"humidity":49,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01d"}],"clouds":{"all":1},"wind":{"speed":3.61,"deg":64,"gust":5.07},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-17 15:00:00"},{"dt":1681754400,"main":{"temp":12.36,"feels_like":11.51,"temp_min":12.36,"temp_max":12.36,"pressure":1028,"sea_level":1028,"grnd_level":1025,"humidity":71,"temp_kf":0},"weather":[{"id":801,"main":"Clouds","description":"few clouds","icon":"02d"}],"clouds":{"all":16},"wind":{"speed":3.59,"deg":80,"gust":6.91},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-17 18:00:00"},{"dt":1681765200,"main":{"temp":9.38,"feels_like":7.87,"temp_min":9.38,"temp_max":9.38,"pressure":1029,"sea_level":1029,"grnd_level":1026,"humidity":84,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01n"}],"clouds":{"all":5},"wind":{"speed":2.83,"deg":64,"gust":8.31},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-17 21:00:00"},{"dt":1681776000,"main":{"temp":7.74,"feels_like":5.97,"temp_min":7.74,"temp_max":7.74,"pressure":1029,"sea_level":1029,"grnd_level":1026,"humidity":87,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01n"}],"clouds":{"all":6},"wind":{"speed":2.74,"deg":38,"gust":8.86},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-18 00:00:00"},{"dt":1681786800,"main":{"temp":6.79,"feels_like":4.51,"temp_min":6.79,"temp_max":6.79,"pressure":1029,"sea_level":1029,"grnd_level":1025,"humidity":84,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01n"}],"clouds":{"all":3},"wind":{"speed":3.22,"deg":33,"gust":9.92},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-18 03:00:00"},{"dt":1681797600,"main":{"temp":6.59,"feels_like":3.93,"temp_min":6.59,"temp_max":6.59,"pressure":1029,"sea_level":1029,"grnd_level":1025,"humidity":84,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01d"}],"clouds":{"all":2},"wind":{"speed":3.79,"deg":40,"gust":11.33},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-18 06:00:00"},{"dt":1681808400,"main":{"temp":10.68,"feels_like":9.42,"temp_min":10.68,"temp_max":10.68,"pressure":1029,"sea_level":1029,"grnd_level":1025,"humidity":62,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01d"}],"clouds":{"all":0},"wind":{"speed":6.22,"deg":59,"gust":10.53},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-18 09:00:00"},{"dt":1681819200,"main":{"temp":12.86,"feels_like":11.48,"temp_min":12.86,"temp_max":12.86,"pressure":1028,"sea_level":1028,"grnd_level":1024,"humidity":49,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01d"}],"clouds":{"all":2},"wind":{"speed":7.06,"deg":67,"gust":11.25},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-18 12:00:00"},{"dt":1681830000,"main":{"temp":12.85,"feels_like":11.44,"temp_min":12.85,"temp_max":12.85,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":48,"temp_kf":0},"weather":[{"id":800,"main":"Clear","description":"clear sky","icon":"01d"}],"clouds":{"all":8},"wind":{"speed":6.96,"deg":62,"gust":10.89},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-18 15:00:00"},{"dt":1681840800,"main":{"temp":10.27,"feels_like":8.97,"temp_min":10.27,"temp_max":10.27,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":62,"temp_kf":0},"weather":[{"id":801,"main":"Clouds","description":"few clouds","icon":"02d"}],"clouds":{"all":15},"wind":{"speed":5.45,"deg":57,"gust":9.82},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-18 18:00:00"},{"dt":1681851600,"main":{"temp":8.23,"feels_like":5.34,"temp_min":8.23,"temp_max":8.23,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":81,"temp_kf":0},"weather":[{"id":803,"main":"Clouds","description":"broken clouds","icon":"04n"}],"clouds":{"all":68},"wind":{"speed":5.09,"deg":51,"gust":10.01},"visibility":10000,"pop":0.02,"sys":{"pod":"n"},"dt_txt":"2023-04-18 21:00:00"},{"dt":1681862400,"main":{"temp":8.24,"feels_like":5.46,"temp_min":8.24,"temp_max":8.24,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":86,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10n"}],"clouds":{"all":84},"wind":{"speed":4.82,"deg":66,"gust":9.55},"visibility":10000,"pop":0.2,"rain":{"3h":0.21},"sys":{"pod":"n"},"dt_txt":"2023-04-19 00:00:00"},{"dt":1681873200,"main":{"temp":7.91,"feels_like":5.55,"temp_min":7.91,"temp_max":7.91,"pressure":1026,"sea_level":1026,"grnd_level":1022,"humidity":86,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04n"}],"clouds":{"all":89},"wind":{"speed":3.77,"deg":50,"gust":9.78},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-19 03:00:00"},{"dt":1681884000,"main":{"temp":8.57,"feels_like":6.14,"temp_min":8.57,"temp_max":8.57,"pressure":1025,"sea_level":1025,"grnd_level":1022,"humidity":92,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":94},"wind":{"speed":4.23,"deg":58,"gust":9.53},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-19 06:00:00"},{"dt":1681894800,"main":{"temp":9.2,"feels_like":6.75,"temp_min":9.2,"temp_max":9.2,"pressure":1026,"sea_level":1026,"grnd_level":1023,"humidity":88,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":100},"wind":{"speed":4.6,"deg":59,"gust":9.23},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-19 09:00:00"},{"dt":1681905600,"main":{"temp":10.68,"feels_like":9.81,"temp_min":10.68,"temp_max":10.68,"pressure":1025,"sea_level":1025,"grnd_level":1022,"humidity":77,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":100},"wind":{"speed":5.59,"deg":68,"gust":9.58},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-19 12:00:00"},{"dt":1681916400,"main":{"temp":11.85,"feels_like":10.68,"temp_min":11.85,"temp_max":11.85,"pressure":1025,"sea_level":1025,"grnd_level":1021,"humidity":61,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":98},"wind":{"speed":6.47,"deg":66,"gust":9.4},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-19 15:00:00"},{"dt":1681927200,"main":{"temp":9.36,"feels_like":6.53,"temp_min":9.36,"temp_max":9.36,"pressure":1025,"sea_level":1025,"grnd_level":1022,"humidity":66,"temp_kf":0},"weather":[{"id":803,"main":"Clouds","description":"broken clouds","icon":"04d"}],"clouds":{"all":57},"wind":{"speed":5.71,"deg":53,"gust":10.46},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-19 18:00:00"},{"dt":1681938000,"main":{"temp":5.81,"feels_like":2.07,"temp_min":5.81,"temp_max":5.81,"pressure":1025,"sea_level":1025,"grnd_level":1022,"humidity":79,"temp_kf":0},"weather":[{"id":801,"main":"Clouds","description":"few clouds","icon":"02n"}],"clouds":{"all":12},"wind":{"speed":5.65,"deg":44,"gust":12.37},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-19 21:00:00"},{"dt":1681948800,"main":{"temp":5.08,"feels_like":1.51,"temp_min":5.08,"temp_max":5.08,"pressure":1024,"sea_level":1024,"grnd_level":1021,"humidity":79,"temp_kf":0},"weather":[{"id":802,"main":"Clouds","description":"scattered clouds","icon":"03n"}],"clouds":{"all":25},"wind":{"speed":4.85,"deg":38,"gust":10.68},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-20 00:00:00"},{"dt":1681959600,"main":{"temp":6.07,"feels_like":2.5,"temp_min":6.07,"temp_max":6.07,"pressure":1023,"sea_level":1023,"grnd_level":1020,"humidity":64,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04n"}],"clouds":{"all":93},"wind":{"speed":5.39,"deg":50,"gust":10.43},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-20 03:00:00"},{"dt":1681970400,"main":{"temp":5.94,"feels_like":2.69,"temp_min":5.94,"temp_max":5.94,"pressure":1022,"sea_level":1022,"grnd_level":1018,"humidity":72,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":96},"wind":{"speed":4.63,"deg":27,"gust":10.32},"visibility":10000,"pop":0,"sys":{"pod":"d"},"dt_txt":"2023-04-20 06:00:00"},{"dt":1681981200,"main":{"temp":5,"feels_like":1.33,"temp_min":5,"temp_max":5,"pressure":1020,"sea_level":1020,"grnd_level":1017,"humidity":93,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10d"}],"clouds":{"all":93},"wind":{"speed":5.02,"deg":40,"gust":9.12},"visibility":881,"pop":0.8,"rain":{"3h":1.2},"sys":{"pod":"d"},"dt_txt":"2023-04-20 09:00:00"},{"dt":1681992000,"main":{"temp":8.25,"feels_like":5.14,"temp_min":8.25,"temp_max":8.25,"pressure":1018,"sea_level":1018,"grnd_level":1015,"humidity":70,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10d"}],"clouds":{"all":86},"wind":{"speed":5.68,"deg":68,"gust":8.41},"visibility":10000,"pop":1,"rain":{"3h":1.36},"sys":{"pod":"d"},"dt_txt":"2023-04-20 12:00:00"},{"dt":1682002800,"main":{"temp":5.98,"feels_like":3.16,"temp_min":5.98,"temp_max":5.98,"pressure":1017,"sea_level":1017,"grnd_level":1014,"humidity":92,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10d"}],"clouds":{"all":98},"wind":{"speed":3.82,"deg":54,"gust":7.39},"visibility":10000,"pop":1,"rain":{"3h":1.69},"sys":{"pod":"d"},"dt_txt":"2023-04-20 15:00:00"},{"dt":1682013600,"main":{"temp":6.44,"feels_like":4,"temp_min":6.44,"temp_max":6.44,"pressure":1016,"sea_level":1016,"grnd_level":1012,"humidity":86,"temp_kf":0},"weather":[{"id":500,"main":"Rain","description":"light rain","icon":"10d"}],"clouds":{"all":85},"wind":{"speed":3.36,"deg":86,"gust":6.63},"visibility":10000,"pop":1,"rain":{"3h":1.04},"sys":{"pod":"d"},"dt_txt":"2023-04-20 18:00:00"},{"dt":1682024400,"main":{"temp":4.67,"feels_like":3.29,"temp_min":4.67,"temp_max":4.67,"pressure":1016,"sea_level":1016,"grnd_level":1013,"humidity":92,"temp_kf":0},"weather":[{"id":802,"main":"Clouds","description":"scattered clouds","icon":"03n"}],"clouds":{"all":26},"wind":{"speed":1.72,"deg":93,"gust":5.04},"visibility":10000,"pop":0.12,"sys":{"pod":"n"},"dt_txt":"2023-04-20 21:00:00"},{"dt":1682035200,"main":{"temp":3.95,"feels_like":2.76,"temp_min":3.95,"temp_max":3.95,"pressure":1015,"sea_level":1015,"grnd_level":1012,"humidity":94,"temp_kf":0},"weather":[{"id":802,"main":"Clouds","description":"scattered clouds","icon":"03n"}],"clouds":{"all":31},"wind":{"speed":1.49,"deg":86,"gust":2.15},"visibility":10000,"pop":0,"sys":{"pod":"n"},"dt_txt":"2023-04-21 00:00:00"},{"dt":1682046000,"main":{"temp":4.59,"feels_like":4.59,"temp_min":4.59,"temp_max":4.59,"pressure":1014,"sea_level":1014,"grnd_level":1011,"humidity":93,"temp_kf":0},"weather":[{"id":803,"main":"Clouds","description":"broken clouds","icon":"04n"}],"clouds":{"all":80},"wind":{"speed":1.1,"deg":41,"gust":1.55},"visibility":10000,"pop":0.12,"sys":{"pod":"n"},"dt_txt":"2023-04-21 03:00:00"},{"dt":1682056800,"main":{"temp":5.04,"feels_like":3.58,"temp_min":5.04,"temp_max":5.04,"pressure":1014,"sea_level":1014,"grnd_level":1011,"humidity":93,"temp_kf":0},"weather":[{"id":804,"main":"Clouds","description":"overcast clouds","icon":"04d"}],"clouds":{"all":85},"wind":{"speed":1.84,"deg":49,"gust":4.11},"visibility":10000,"pop":0.04,"sys":{"pod":"d"},"dt_txt":"2023-04-21 06:00:00"}],"city":{"id":2643743,"name":"London","coord":{"lat":51.5085,"lon":-0.1257},"country":"GB","population":1000000,"timezone":3600,"sunrise":1681621397,"sunset":1681671424}}'
