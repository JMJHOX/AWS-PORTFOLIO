# Food Truck Web App

##### REMEMBER THIS PROJECT IS USING FREE TIER

There is a currently need with restaurants and food trucks to be employing the last technologies on their business to become more atractive for people and to low significantly costs on their operations and model of doing things.
The Food Truck App needs to be fully functional offline and heavily focused on mobile/tablet platforms.
<br><br>
Requirements to fullfill business model:

* Can be used as a digital menu(create, read, update and delete dishes on the menu)
*  checkout the user´s order and generate a PDF with it and be downloable
* It has to manage a sesion user system per company/person that can be scalable
* Store a backup and keep track of order´s history of clients per restaurant, and has to be synchronizable with the cloud and viceversa.


## Architecture proposal
Our first proposal with be a classic architecture consisting on a EC2 with the Web App deployed on the public subnet.<br>
Its purpose is to be able to communicate with the Internet Gateway and thus, users can be able to reach the App <br>
On the private subnet we´ll be using a RDS Instance to store our order´s history and be able to sinchronize RDS Instance´s data compared with the Web App, and  create backups with it. 
<br>
To provide high availability, we´ll be setting our RDS instance with Multi-AZ deployment failover. And to upload our app on the EC2 Instance, we´ll be employing a S3 Bucket to store our webapp.zip to be reachable for our app and be installed.

![f](imgs/FoodTruckArchJPG.001.jpeg)

![f](imgs/app-db.png)
