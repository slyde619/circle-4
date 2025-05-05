---
layout: default
---

# Making API Calls - Weather App Example

<div class="grid grid-cols-2 gap-4">
  <div class="col-span-1">
    <h3>API Implementation</h3>
    
```js
// From our weather app
(async function getWeatherData() {
  const city = "lagos";
  const apiKey = "2608xxxxxxxxxxxxxxxxxx";
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;
  const response = await fetch(url);
  const data = await response.json();
  
  const { name, sys, wind, main, weather } = data;
  console.log(data);
  
  app.innerHTML = `
  <article class="weather-report">
        <h1>Weather Report</h1>
        <div>
            <h3>${name}</h3>
            <h1>${sys.country}</h1>
        </div>
        <div class="weather-data">
            <p>Humidity: <span>${main.humidity}g/m<sup>3</sup></span></p>
            <p class="desc">Weather Description: <span>${weather[0].description}</span></p>
            <p>Wind Speed: <span>${wind.speed}</span></p>
            <p>Temperature: <span>${main.temp}&deg;C</span></p>
        </div>
     </article>
  `;
})();
```
  </div>
  
  <div class="col-span-1 flex items-center justify-center">
    <div class="max-w-sm w-full">
      <div class="bg-gradient-to-r from-blue-500 to-blue-700 rounded-t-lg p-4 text-white">
        <h1 class="text-xl font-bold mb-2">Weather Report</h1>
        <div class="flex justify-between items-center">
          <h3 class="text-lg">Lagos</h3>
          <h1 class="text-lg font-bold">NG</h1>
        </div>
      </div>
      <div class="bg-white rounded-b-lg shadow-xl p-4">
        <div class="weather-data space-y-3">
          <p class="flex justify-between border-b pb-2">Humidity: <span class="font-bold">69g/m<sup>3</sup></span></p>
          <p class="flex justify-between border-b pb-2">Weather Description: <span class="font-bold">overcast clouds</span></p>
          <p class="flex justify-between border-b pb-2">Wind Speed: <span class="font-bold">3.6</span></p>
          <p class="flex justify-between pb-2">Temperature: <span class="font-bold text-red-500">30.39°C</span></p>
        </div>
      </div>
    </div>
  </div>
</div>

```
