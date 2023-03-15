# Water Tracking System
## Description
Note: As this was done during an internship, I was not given permission to post all of the code and technology used. However, I was given permission to post select aspects which I will be showing. If there are any questions you can connect with me through LinkedIn and I would be happy to chat!

The project was to create a system that allows for the billing and monitoring of water meters located on rental properties. Normally, to bill a tenant for water usage, a person would have to go to the property each month to take a reading from the water meter. This project circumvents this problem by creating a web interface in which a secretary is able to log on. From this webpage they can view the current water usage for each apartment, generate bills, and start/stop the service all without having to send a person to the site. 

The project was accomplished by installing digital water meters onto each tenants water lines. The digital water meters were then connected to a microcontroller that recorded information from the digital water meters. The microcontroller then was able to broadcast the data to a secure server via a simple WiFi connection. The server was then responsible for hosting the webpage.

My role within this project was to create an easily navigable webpage with the aforementioned functionalities. I was also tasked with programming a controller that would stay on the property to record and broadcast the information by taking readings from digital water meters that were installed in the water lines.

## Languages and Technology
- HTML/CSS/JavaScript/PHP - used to build the webpage
- MySQL - used to create and maintain a database
- C++ - used to program the controller
- Linux OS
- Microcontroller

## Methodology
1.	I began by programming the controller that would be connected to the water meters. We used an esp32 due to its ability to have Wi-Fi and an ample number of GPIO pins. 
    -	This was done in C++.
    -	The microcontroller was programmed to record the amount of water used for each unit. It did this by reading info from GPIO pins that were connected to the digital water meters. It then stored this data on an SD card.
    -	To broadcast the data, the controller ran up a simple webserver. When an outside program accesses the server with correct identification keys, the requested information is sent back in JSON format. This is done via GET and POST requests. 

<p align="center">
    <img alt="Admin Page" width="50%" src="https://i.imgur.com/c7zfviA.png"/>
    <p align="center">Diagram of the controller that is connected to the water meters.</p>
    <br>
</p>

2.	I created an administration webpage that is accessible via a secured network. Once reached, a form prompts for login information. The webpage then shows different administrative functions.
    -	This was done in HTML, PHP, and MySQL.
    -	When any link on the admin page is clicked, a PHP file is called that then retrieves data from the controller and makes MySQL calls corresponding to the link that is clicked. For example, the “Get Monthly Bill” link directs you to a page where you enter the renter information, and it makes MySQL calls to grab information to generate a bill. 
    -	MySQL was used to create a relational database. This was done within the Linux command line. 
 
<p align="center">
    <img alt="Admin Page" width="75%" src="https://i.imgur.com/XzkjA2g.png"/>
    <p align="center">Admin page that is revealed after a user logs in.</p>
    <br>
</p>

<p align="center">
    <img alt="Initialize Customer" width="75%" src="https://i.imgur.com/ofILtsh.png"/>
    <p align="center">Initialize Customer prompts for a name and the apartment. Using this info, it will grab the necessary info from the database and create a new user.</p>
    <br>
</p>

<p align="center">
    <img alt="Finalize Customer" width="75%" src="https://i.imgur.com/RrS3iDF.png"/>
    <p align="center">Finalize Customer terminates a user but keeps their previous information within the database for logging purposes.</p>
    <br>
</p>

<p align="center">
    <img alt="Current Data" width="75%" src="https://i.imgur.com/JIE9fVY.png"/>
    <p align="center">Current Data displays the info regarding specific meters.</p>
    <br>
</p>

<p align="center">
    <img alt="System Log" width="75%" src="https://i.imgur.com/Ybz3r50.png"/>
    <p align="center">View System Log displays any log information from the controller.</p>
    <br>
</p>
    
3.	I created a daemon script that retrieves data from the controller and updates the database on a time interval. 
    -	This was done in Python.
    -	This is used to create logs and send email alerts if the controller is not responding.


