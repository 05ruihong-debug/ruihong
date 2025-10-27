# Weather Dashboard ☀️🌧️

A basic web app that shows real-time weather updates for any city.

## Features
- Search for any city
- Display temperature, humidity, and weather condition
- Uses OpenWeatherMap API

## Technologies Used
- HTML
- CSS
- JavaScript

## Example Code
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Weather Dashboard</title>
  </head>
  <body>
    <h2>Weather Dashboard</h2>
    <input id="city" placeholder="Enter city name">
    <button onclick="getWeather()">Search</button>
    <div id="result"></div>

    <script>
      async function getWeather() {
        const city = document.getElementById('city').value;
        const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=YOUR_API_KEY&units=metric`);
        const data = await response.json();
        document.getElementById('result').innerHTML = 
          `${data.name}: ${data.main.temp}°C, ${data.weather[0].description}`;
      }
    </script>
  </body>
</html>
