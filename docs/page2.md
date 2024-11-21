---
title: Second Page
layout: home
---
# A small weather app

```python
import requests

def get_weather(city):
    api_key = "your_api_key"  # Replace with your OpenWeatherMap API key
    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"
    
    try:
        response = requests.get(url)
        response.raise_for_status()
        data = response.json()

        Console.log()

        if data.get("cod") != 200:
            print(f"Error: {data.get('message')}")
            return

        main = data["main"]
        weather = data["weather"][0]
        
        print(f"Weather in {city}:")
        print(f"Temperature: {main['temp']}°C")
        print(f"Condition: {weather['description'].capitalize()}")

    except requests.exceptions.RequestException as e:
        print(f"Error fetching weather data: {e}")

if __name__ == "__main__":
    city = input("Enter the name of the city: ")
    get_weather(city)
```
