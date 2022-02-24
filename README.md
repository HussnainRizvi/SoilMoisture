# SoilMoistureMonitoring
Soil moisture is basically the content of water present in the soil. This can be measured using a soil moisture sensor which consists of two conducting probes that act as a probe. It can measure the moisture content in the soil based on the change in resistance between the two conducting plates. The resistance between the two conducting plates varies in an inverse manner with the amount of moisture present in the soil.
The purpose of this project is to detect and sense the amount of moisture present in a soil which is a crucial factor in agriculture.

SoilMoistureMonitoring is a simple function made for Nuclio (an open source and managed serverless platform that we can run on our home server). It uses RabbitMQ as broker to share MQTT messages around.

## Prerequisite

- Docker
- Nuclio
- RabitMQ
- Arduino IDE
- IFTTT
- Node.js

## How to use it
Clone this repository, then you need to start a Docker to start up a docker instance of Nuclio, use this command on nuclio:

` $ sudo docker run -p 8070:8070 -v /var/run/docker.sock:/var/run/docker.sock -v /tmp:/tmp nuclio/dashboard:stable-amd64 `

And to start up a docker instance of RabbitMQ, with the command:

` $ sudo docker run -p 9000:15672 -p 1883:1883 -p 5672:5672 cyrilix/rabbitmq-mqtt `

To Run The Logger You Can Use CMD Before that you have install Npm Dependency By Following command : 

` $ sudo apt install npm `

To get the notifications of data readings on Telegram, make an IFTTT applet through Webhooks service. After creating applet, write the IP address, name of event and Key in the code of Nuclio function from IFTTT post-URL section and deploy the function. You can find the key through webhooks service on IFTTT. When the soil moisture level gets below or higher than threshold, an message notification will be sent on user telegram.

## Libraries

- ESP8266WiFi
  
  The ESP8266WiFi library provides a wide collection of C++ methods (functions) and properties to configure and operate an ESP8266 module in station and / or soft access point mode.

- Pubsub Client

  A client library for MQTT messaging. MQTT is a lightweight messaging protocol ideal for small devices. This library allows you to send and receive MQTT messages.

