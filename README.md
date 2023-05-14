# Weather-Go
A simple web application that displays the current weather information for a given city. I will be using the OpenWeatherMap API to fetch weather data.

## <u>Explanation of the code</u>
First, I define a weatherData struct to represent the weather information I will be returning to the user. I also define a getWeather function that takes a city name as a parameter and returns a weatherData struct containing the current weather information for that city. The function makes an HTTP request to the OpenWeatherMap API and parses the JSON response to extract the relevant information.

Next, I define a getWeatherHandler function that handles HTTP requests to the /weather/{city} endpoint. It uses the mux.Vars function to extract the {city} variable from the URL and calls getWeather to fetch the weather information for that city. If there is an error fetching the weather information, it returns a 500 internal server error. Otherwise, it sets the content type of the response to application/json and encodes the weather information as JSON using json.NewEncoder.

Finally, in the main function, I create a new mux.Router and register the getWeatherHandler function to handle requests to the /weather/{city} endpoint. I then start the HTTP server on port 8080 using http.ListenAndServe.

## How to run
To run the application, navigate to the directory containing main.go in your terminal and run:

```go

go run main.go

