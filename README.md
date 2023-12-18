# ESP8266 MPU6050 Orientation Sensor Prototype 📡🔄

This project features an ESP8266-based prototype leveraging the MPU6050 MEMS Gyro-sensor to stream orientation data across the X, Y, and Z axes via WiFi using HTTP.

## Project Structure 📂

```
- mpu6050.h
- Orientation-Sensor.ino
- server.h
- wifi.h
```

## Code Snippets 🧩

### MPU6050 Initialization and Sensor Data Retrieval

#### `void initMPU6050()`
- Initializes the MPU6050 sensor.
- Sets the sensor's range for accelerometer data.

#### `void getSensorData()`
- Retrieves sensor data for gyroscope and accelerometer events.
- Stores values for gyro X, Y, Z, and accelerometer X, Y, Z, as well as temperature.

### WiFi and Server Initialization

#### `void initWiFi()`
- Sets up WiFi mode as an access point.
- Initializes a soft access point using specified SSID and password.
- Configures device hostname.

#### `void initServer()`
- Initiates the MPU6050 sensor.
- Defines a server endpoint for streaming sensor data.
- Begins the server.

### HTTP Request Handling and Sensor Data Streaming

#### `void handleRequest()`
- Manages incoming HTTP requests.
- Triggers the `getSensorData()` function.
- Handles client requests to the server.

#### `void sendSensorData()`
- Formats sensor data into a string.
- Sends sensor data over HTTP in a comma-separated format.

## How It Works ℹ️

- The `Orientation-Sensor.ino` file is the main program file containing the setup and loop functions.
- Initialization of the MPU6050 sensor is handled in `mpu6050.h`.
- WiFi setup and server endpoints are defined in `wifi.h` and `server.h` respectively.
- Sensor data retrieval, HTTP request handling, and data streaming occur in the main file.
- Access the sensor data by sending an HTTP GET request to the server endpoint at `http://DEVICE_IP_ADDRESS/data`.
- Sensor data is transmitted in comma-separated format for X, Y, Z axes for both gyroscope and accelerometer, along with temperature data.

