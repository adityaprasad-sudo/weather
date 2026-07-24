# Lazy Weather webpage

This is a very lazy made weather app Man i am tired of making projects.

## AI_USAGE

I used AI to assist me in writing javascript since it requires brain and i am just too exhausted.
I also used Windsurf(Vs code extension) in-line suggestionss to create this project


## To Reviewers

Please dont deduct any hours 😭😭😭😭😭😭😭😭😭😭😭😭
I am sorry to ship such a shi project

### Dependencies

- html,css
- javascript
- weather, aqi and search geo location apis

### Explain

**1.**

```
function chigga(code){
            if(code == 0) return "Clear Sky";
            if (code == 1 || code == 2 || code == 3) return "Cloudy";
            if (code == 45 || code == 48) return "Fog";
            if (code >= 51 && code <= 67) return "Rain";
            if (code >= 71 && code <= 77) return "Snow";
            if (code >= 80 && code <= 82) return "Rain showers";
            if (code >= 95) return "Thunderstorm";
            return "Idk";
        }
```
this part deals with the status of the current weather in your city(if you search it)
**NOTE** The search engine is made very lazily so it doesnt give recommendations so just enter your city an click enter

**You can refer to the the weather codes here [Weather Codes](https://open-meteo.com/en/docs?hourly=temperature_2m,weather_code#weather_variable_documentation)**

**2.** HOw the search fn is so shi ahh made?
```
let input = document.getElementById('locainput').value;
            if (input == "") return;
            let searchApi = "https://geocoding-api.open-meteo.com/v1/search?name=" + input + "&count=1&language=en&format=json";
            try {
                let res = await fetch(searchApi);
                let locData = await res.json();
                if (locData.results && locData.results.length > 0) {
                    lat = locData.results[0].latitude;
                    longi = locData.results[0].longitude;
                    if (locData.results[0].country) {
                        cityname = locData.results[0].name + ", " + locData.results[0].country;
                    } else {
                        cityname = locData.results[0].name;
                    }
                    update(); 
                } else {
                    alert("City not found!");
                }
            } catch(e) {
                console.log(e);
            }
        // below is the enter key and searchbtn setup keep this out of the search fn
        document.getElementById('seebtn').addEventListener('click', searchCity);
        document.getElementById('locainput').addEventListener('keypress', function(e) {
            if (e.key === "Enter") {
                searchCity();
            }
        });
```
This is the whole searching engine which only takes the name of the place and feeds it into the searchapi **AI is used here**


## Help

If you have any doubts related to syntax I had too you can check the open meteo docs [here](https://open-meteo.com/en/docs)

## Motivation

Made this webpage to gain 5 hours so i can go to singapore

## THANK YOU