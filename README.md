# mqtt-realtime-chart-client

This project demonstrates the visualization of high-frequency data streams (50Hz+) with Rickshaw.js chart library! 

**mqtt-realtime-chart-client** is a Vue.js client application, which works in conjunction with [mqtt-realtime-chart-server](https://github.com/NickJokic/mqtt-realtime-chart-server).


![Alt Text](https://raw.githubusercontent.com/NickJokic/mqtt-realtime-chart-client/master/static/mqtt-realtime-chart.gif)


## Features
### Client
+ real-time data visualization with a multi-series line chart
+ dynamic slider which controls the chart render frequency (renders chart after N message(s))
	+ this is useful for optimization purposes, especially in high-frequency real-time streams, where you 	can	lower the chart render calls in order to lessen the CPU load. 

### Server
+ publishes and subscribes to MQTT topic (e.g. **voltage**)
+ forwards the received messages to the client using websockets

## Getting Started

### Prerequisites

Before you run the client, be sure you have these downloaded/installed on your machine:

+ node.js
+ npm
+ [mqtt-realtime-chart-server](https://github.com/NickJokic/mqtt-realtime-chart-server)
+ [Moquette (MQTT broker)](https://github.com/andsel/moquette) (or any other MQTT broker that listens on port 1883)
    + If using Moquette, be sure to have Java JDK installed (tested with JDK 8)   


### Installing

To get started with this project, follow the 3-step installation, described here.

## 1. Moquette 

The following commands will unpack and run the Moquette broker, which listens on port 1883:

```
tar zxf distribution-0.10-bundle-tar.tar.gz
cd bin
./moquette.sh	
```

*Windows specific:*

```
cd bin
.\moquette.bat 
```


## 2. mqtt-realtime-chart-*server*

Navigate inside the root folder and run:

```
npm install
npm start
```
this will install the dependencies and start the express server locally on port 3000.

If the server-app and Moquette are already running in separate terminals, you can see the data stream inside the terminal. You can also check out the stream with a 3rd party MQTT client (e.g. MQTTfx) by connecting to **0.0.0.0:1883** and subscribing to topic **voltage**.


## 3. mqtt-realtime-chart-*client* *\(this repo)\*

*Before running the client, be sure you have already completed steps 1 and 2, and have both Moquette and mqtt-realtime-chart-server running in separate terminal windows.*

Open a new terminal window and navigate inside the root folder of the client application, then run:

```
npm install
npm start
```

After compilation, you will see the link in the terminal *(e.g. http://localhost:8081)* where the application is currently running. Use your browser to navigate to that link. 

If everything went smoothly, you should see a real-time chart with data frequency of around 50Hz.


## Built With

### Client
* [Vue.js](https://github.com/vuejs/vue) - JavaScript framework for building UI on the web.
* [Rickshaw.js](https://github.com/shutterstock/rickshaw) - JavaScript toolkit for creating interactive real-time graphs
* [Socket.io-client](https://github.com/socketio/socket.io) - real-time bidirectional event-based communication using websockets (client)
* [Bootstrap](https://github.com/twbs/bootstrap) - HTML, CSS, and JavaScript framework for developing responsive, mobile first projects on the web.

### Server
* [Express.js](https://github.com/expressjs/express) - minimalist web framework for node.
* [Socket.io](https://github.com/socketio/socket.io) - real-time bidirectional event-based communication using websockets
* [MQTT.js](https://github.com/mqttjs/MQTT.js) - MQTT client for Node.js and the browser 


## Authors

* **Nick Jokic** - [GitHub](https://github.com/NickJokic)


## License

This project is licensed under the MIT License.

## Acknowledgments

* God bless the creators and contributors of [Moquette](https://github.com/andsel/moquette) for their **1 minute set up**!

