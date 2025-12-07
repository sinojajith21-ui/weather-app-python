import requests

city = input("Enter city name: ")

# Step 1: Get latitude & longitude of the city
geo_url = f"https://geocoding-api.open-meteo.com/v1/search?name={city}"
geo_data = requests.get(geo_url).json()

if "results" not in geo_data:
    print("City not found!")
    exit()

lat = geo_data["results"][0]["latitude"]
lon = geo_data["results"][0]["longitude"]

# Step 2: Fetch weather data
weather_url = f"https://api.open-meteo.com/v1/forecast?latitude={lat}&longitude={lon}&current_weather=true"
weather_data = requests.get(weather_url).json()

temp = weather_data["current_weather"]["temperature"]
wind = weather_data["current_weather"]["windspeed"]

print(f"\nWeather in {city}:")
print(f"Temperature: {temp} °C")
print(f"Wind Speed: {wind}")
