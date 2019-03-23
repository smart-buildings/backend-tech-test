# Tech test

## Overview

Smart Buildings has deployed air quality devices to offices around the world for a theoretical customer. An application is required to consume the data outputted by the sensors and provide ratings on the air quality and the comfort of the office spaces.

## Information provided the sensors

|Reading|Ideal Min|Ideal Max|Notes|
|---|---|---|---|
|Relative Humidity|30%|50%|Uncomfortable above 50%|
|Co2|250 ppm|1000 ppm|Unsafe above 1000ppm|
|PM2.5|0 μg/m3|12 μg/m3|Unsafe above 12ppm|
|Space Temperature|21°C|23°C|Uncomfortable outside of ideal, unsafe below 16°C|

## How the sensors provide data

On reading change, the sensors publish to a [MQTT](http://mqtt.org/) Broker.

The MQTT topic format is described below:

`smart/{location-id}/{sensor-number}/{reading}`
e.g. `smart/leeds/5/relative-humidity`


## The challenge

- Subscribe to the MQTT broker
- Create a rating system on Air Quality and Comfort based on the notes above. The further outside the ideal the reading, the more severe the rating should be.
- In real-time provide a list of devices, live readings and air quality/comfort ratings. The way you make the data available is up to you, e.g:
  - Console output
  - Write to file
  - Database
  - Queryable via an API
  - User Interface

## Get started

You will need to download [Docker Desktop](https://www.docker.com/products/docker-desktop).

Once downloaded and installed. Clone this repository (or copy the `docker-compose.yml` file to a folder of your choice). Open a terminal and run `docker compose up`

The MQTT broker will start to listen on port `1883`. You can use tool such as [MQTT.FX](https://mqttfx.jensd.de/index.php/download) to connect to and test the broker.
