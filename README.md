# Temperature and Light Monitoring with ESP32

## Summary of Functions:

### patchtemp():
- The patchTemp function sends a PUT request to update the temperature value on a remote API endpoint. It prepares a JSON payload containing the current temperature and sends it with necessary headers, such as Content-Type and API key. The function then prints the response received from the API.

### getlight():
- The getLight function sends a GET request to retrieve the light status from a remote API endpoint. It includes the necessary API key in the request header. After receiving the response, the function parses the JSON data to extract the light status and then updates the LED state on the circuit accordingly. Any relevant debug or error messages are also printed during this process.

### setup():
- The setup function initializes serial communication, connects to WiFi, and sets up the LED pin for output on the ESP32 board.

### loop():
- The loop function continuously checks the WiFi connection status. If the ESP32 is connected to WiFi, it performs the following actions in a loop:
1. Requests temperature readings from sensors (sensors.requestTemperatures()).
2. Retrieves the temperature value in Celsius (sensors.getTempCByIndex(0)).
3. Calls the patchTemp function to send a PUT request with the temperature value to the API.
4. Calls the getLight function to send a GET request to retrieve light status from the API and update the LED state accordingly.
If the WiFi connection is lost, it prints a message indicating that WiFi is disconnected.

## Purpose of the Code:
- This code is written for the ECSE3038 Course.
