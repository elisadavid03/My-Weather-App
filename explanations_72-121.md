### Explanation of Each Line (72-121 JS)

1. **`if (dailyForecasts[day].length > 0 && displayedDays < 6) {`**:
   - This line checks two conditions before processing the forecast for a day:
     - `dailyForecasts[day].length > 0`: Ensures there are forecast entries for the current day.
     - `displayedDays < 6`: Ensures that no more than 6 days' forecasts are displayed.

2. **`const date = new Date(dailyForecasts[day][0].dt * 1000);`**:
   - Converts the Unix timestamp (in seconds) of the first forecast item of the current day to a JavaScript `Date` object by multiplying by 1000 to convert it to milliseconds.

3. **`const dayName = days[date.getDay()];`**:
   - Retrieves the name of the day (e.g., "Monday") from the `days` array using the day index from the `Date` object.

4. **`const dayContainer = document.createElement('div');`**:
   - Creates a new `div` element to hold the forecast information for the current day.

5. **`dayContainer.classList.add('day-forecast');`**:
   - Adds a CSS class (`day-forecast`) to the `div` element to apply specific styling.

6. **`const dayTitle = document.createElement('h3');`**:
   - Creates a new `h3` element to hold the title of the day.

7. **`dayTitle.classList.add('date');`**:
   - Adds a CSS class (`date`) to the `h3` element to apply specific styling.

8. **`dayTitle.textContent = dayName;`**:
   - Sets the text content of the `h3` element to the name of the day.

9. **`dayContainer.appendChild(dayTitle);`**:
   - Appends the `h3` element to the `dayContainer` `div` element.

10. **`dailyForecasts[day].forEach(item => {`**:
    - Starts a loop over each forecast item for the current day.

11. **`const iconCode = item.weather[0].icon;`**:
    - Retrieves the weather icon code from the forecast item.

12. **`const iconImageUrl = `http://openweathermap.org/img/w/${iconCode}.png`;`**:
    - Constructs the URL for the weather icon image using the retrieved icon code.

13. **`const time = document.createElement('p');`**:
    - Creates a new `p` element to hold the time of the forecast.

14. **`time.classList.add('time');`**:
    - Adds a CSS class (`time`) to the `p` element to apply specific styling.

15. **`time.textContent = new Date(item.dt * 1000).toLocaleTimeString();`**:
    - Sets the text content of the `p` element to the time of the forecast, formatted as a locale-specific string.

16. **`const temp = document.createElement('p');`**:
    - Creates a new `p` element to hold the temperature of the forecast.

17. **`temp.classList.add('current-temp');`**:
    - Adds a CSS class (`current-temp`) to the `p` element to apply specific styling.

18. **`temp.innerHTML = `Temperatura: ${item.main.temp} &deg;C`;`**:
    - Sets the inner HTML of the `p` element to display the temperature with the degree symbol.

19. **`const icon = document.createElement('img');`**:
    - Creates a new `img` element to display the weather icon.

20. **`icon.src = iconImageUrl;`**:
    - Sets the `src` attribute of the `img` element to the URL of the weather icon image.

21. **`icon.classList.add('icon');`**:
    - Adds a CSS class (`icon`) to the `img` element to apply specific styling.

22. **`const description = document.createElement('p');`**:
    - Creates a new `p` element to hold the weather description.

23. **`description.classList.add('conditions');`**:
    - Adds a CSS class (`conditions`) to the `p` element to apply specific styling.

24. **`description.textContent = `Descriere: ${item.weather[0].description}`;`**:
    - Sets the text content of the `p` element to display the weather description.

25. **`const humidity = document.createElement('p');`**:
    - Creates a new `p` element to hold the humidity level.

26. **`humidity.classList.add('humidity');`**:
    - Adds a CSS class (`humidity`) to the `p` element to apply specific styling.

27. **`humidity.textContent = `Umiditate: ${item.main.humidity}%`;`**:
    - Sets the text content of the `p` element to display the humidity level.

28. **`const forecastCard = document.createElement('div');`**:
    - Creates a new `div` element to hold all the forecast information for a single 3-hour interval.

29. **`forecastCard.classList.add('forecast-card');`**:
    - Adds a CSS class (`forecast-card`) to the `div` element to apply specific styling.

30. **`forecastCard.appendChild(time);`**:
    - Appends the `time` element to the `forecastCard` element.

31. **`forecastCard.appendChild(icon);`**:
    - Appends the `icon` element to the `forecastCard` element.

32. **`forecastCard.appendChild(temp);`**:
    - Appends the `temp` element to the `forecastCard` element.

33. **`forecastCard.appendChild(description);`**:
    - Appends the `description` element to the `forecastCard` element.

34. **`forecastCard.appendChild(humidity);`**:
    - Appends the `humidity` element to the `forecastCard` element.

35. **`dayContainer.appendChild(forecastCard);`**:
    - Appends the `forecastCard` element to the `dayContainer` element.

36. **`forecastContainer.appendChild(dayContainer);`**:
    - Appends the `dayContainer` element to the `forecastContainer` element, which is the main container for displaying the forecasts.

37. **`displayedDays++;`**:
    - Increments the `displayedDays` counter by 1 to keep track of how many days' forecasts have been displayed. This ensures that no more than 6 days' forecasts are shown.
