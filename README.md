# LoadBalancer & MQTT Brokers

The purpose of this project is using a Load Balancer with MQTT brokers for efficiency.

## Description

This project demonstrates the setup of multiple Mosquitto MQTT Brokers with HAProxy for load balancing and high availability. The configuration ensures efficient distribution of MQTT client connections across multiple brokers.

## Features
-Multiple Mosquitto Brokers: two Mosquitto instances which are listening on port 1883 and port 1884   
-HAProxy Load Balancer: Distributes MQTT client connections with using Round-Robin algorithm   
-Supports local and remote connections to MQTT brokers and Load Balancer   
-Complete dockerized project   
 
## Getting Started

### Dependencies

* Docker
* HAProxy
* mosquitto-eclipse

### Installing

* For this project you can install the folders that are uploaded.  
* You should configure your docker-compose.yml file for your needs.
* You should decide which port that you are going to use for mqtt brokers. Please carefully set your ports because If you set them up at the same port or the port you are going to use is already using, then it is inevitable that you are going to face errors.
* You should use a passw file to use this project. If you don't need user authentication, then you can set 
```
allow_anonymouse true
``` 
in your mosquitto.conf file and remove
```
password_file /etc/mosquitto/passwd
```
 line.  

### Executing program

* After you download this project you should change your haproxy.conf file for your needs. In that file you can see the "IP HERE" line. You should enter your WI-FI IPV4 adress there. 
* When you ensure your ports are true and can useable, you should dockerize the project.
* You can decide which algorithm to use for load balancing in this line. For example if you want to use leastconn algorithm then you should edit your config file as:
 ```
balance leastconn
``` 
* Open your terminal and write code below
```
cd YourFolder
```
*The code above allows you to get inside the file
*Then write this
```
docker-compose up -d
```
*After this code, your project is setted up in docker containers. You can use the ports that you assign for Load Balancer and MQTT ports.  


