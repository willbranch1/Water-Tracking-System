# Water Tracking System
## Description
The project was to create a system that allows for the billing and monitoring of water meters located on rental properties. Normally, to bill a tenant for water usage, a person would have to go to the property each month to take a reading from the water meter. This project circumvents this problem by creating a web interface in which a secretary is able to log on. From this webpage they can view the current water usage for each apartment, generate bills, and start/stop the service all without having to send a person to the site. 

The project was accomplished by installing digital water meters onto each tenants water lines. The digital water meters were then connected to a microcontroller that recorded information from the digital water meters. The microcontroller then was able to broadcast the data to a secure server via a simple WiFi connection. The server was then responsible for hosting the webpage.

My role within this project was to create an easily navigable webpage with the aforementioned functionalities. I was also tasked with programming a controller that would stay on the property to record and broadcast the information by taking readings from digital water meters that were installed in the water lines.

Note: As this was done during an internship, I was not given permission to post all of the code and technology used. However, I was given permission to post select aspects which I will be showing. If there are any questions you can connect with me through LinkedIn and I would be happy to chat!

## Languages and Technology
- HTML/CSS/JavaScript/PHP - used to build the webpage
- MySQL - used to create and maintain a database
- C++ - used to program the controller
- Linux OS
- Microcontroller

## Methodology
1. I created a relational database utilizing MySQL. This was done via the Linux command line. Data that was stored includes customer information, daily readings, dates for logs, etc. 
2. I programmed a controller that had multiple different functionalities. It is able to connect to WiFi in order to broadcast data, maintain its own logs in cases of WiFi or power outages, and read data from water meters. This was all done in C++. 
3. I created a webpage with 
