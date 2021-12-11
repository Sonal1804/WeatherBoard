<template>

        <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
            <div class="location-box">
                <div class="location">{{ weather.name }}, {{ weather.sys.country }}</div>
                <div class="date">{{ dateBuilder() }}</div>
            </div>

            <div class="weather-box">
                <div class="temp">{{ Math.round(weather.main.temp) }}°c</div>
                <div class="weather">{{ weather.weather[0].main }}</div>
            </div>

            <div class="weather-box2">
                <div class="temp-range" >Min Temp :{{Math.round(weather.main.temp_min)}}°c</div>
                <div class="temp-range" >Max Temp :{{Math.round(weather.main.temp_max)}}°c</div>
            </div>
        </div>
  
</template>

<script>
export default {
    name: 'weatherfind',
    props:["getWeather","weather","dateBuilder"],
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'montserrat', sans-serif;
}

#app1{
    margin-top:30px;
    background-image: url('../assets/cold-bg.jpg');
    background-size: cover;
    background-position: bottom;
    transition: 0.4s;
}

.try {
    border: 1px solid green;
    display: inline-block;
    height: 90vh;
    width: 50vh;
    float: left;

    margin-left: 30px;
}

#app1.warm {
    background-image: url('../assets/warm-bg.jpg');
}

main {
    min-height: 90vh;
    padding: 25px;

    background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.75));
}

.search-box {
    width: 100%;
    margin-bottom: 30px;
}

.search-box .search-bar {
    display: block;
    width: 100%;
    padding: 15px;

    color: #313131;
    font-size: 20px;

    appearance: none;
    border: none;
    outline: none;
    background: none;

    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
    background-color: rgba(255, 255, 255, 0.5);
    border-radius: 0px 16px 0px 16px;
    transition: 0.4s;
}

.search-box .search-bar:focus {
    box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
    background-color: rgba(255, 255, 255, 0.75);
    border-radius: 16px 0px 16px 0px;
}

.location-box .location {
    color: #FFF;
    font-size: 32px;
    font-weight: 500;
    text-align: center;
    text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}

.location-box .date {
    color: #FFF;
    font-size: 20px;
    font-weight: 300;
    font-style: italic;
    text-align: center;
}

.weather-box {
    text-align: center;

}

.weather-box .temp {
    display: inline-block;
    padding: 10px 25px;
    color: #FFF;
    font-size: 102px;
    font-weight: 900;

    text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
    background-color: rgba(255, 255, 255, 0.25);
    border-radius: 16px;
    margin: 30px 0px;

    box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather-box2 .temp-range {
    display :inline-block;
    padding: 10px 65px;
    color: #FFF;
    font-size: 10px;
    font-weight: 100;
    
    
    background-color: rgba(255, 255, 255, 0.25);
    border-radius: 16px;
    margin: 14px 10px;

    box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}


.weather-box .weather {
    color: #FFF;
    font-size: 48px;
    font-weight: 700;
    font-style: italic;
    text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
