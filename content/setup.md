+++
title = "Setting-up Threads"
date = "2020-12-16"
sidemenu = "true"
description = "A Vulnerable Web Application Lab"
+++

As we know Threads is a vulnerable lab application which looks the  same like any other social media platform but the main motto is to solve the vulnerabilities present in it. So here is a guide on how to setup Threads application on your local system which is divided into two parts, one contains the information on how to install the  prerequisite before setting up the lab and the other part contains on how to setup lab if you already have the both prerequisite installed in your system.

## How to setup Threads on your local system

### Part-1:(Prerequisite for setting up lab)

There are only two prerequisite:

1. Install **Node.js** in your system.

2. Install **MongoDB**.

**Note**: Check with commands ($npm -v and $node -v) if the node is already installed then it’s not necessary to follow the node.js installation setup below.

### Node.js Setup

1. Go to your terminal.

2. `$ sudo apt update`

3. `$ cd ~`

4. `$ curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh`

5. `$ sudo bash nodesource_setup.sh`

6. `$ sudo apt install nodejs`

7. Check the version after above commands with:
   
   a. `$ node -v`
   
   b. `$ npm -v`

### MongoDB setup

1. Open up your terminal 

2. `$ wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -`

3. `$ sudo add-apt-repository 'deb [arch=amd64] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse'`  (for Ubuntu OS, the URL inside this command will change according to different OS)

4. `$ sudo apt-get update`

5. `$ sudo apt install mongodb-org`

6. `$ sudo systemctl enable --now mongod`

7. To check if the MongoDb was installed successfully use this command:

   `$ mongo --eval 'db.runCommand({ connectionStatus: 1 })'`

8. You must get a output like this or similar to this after the above command which means MongoDB was installed properly.

```
MongoDB shell version v4.4.0 
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb 
Implicit session: session { "id" : UUID("2af3ab0e-2197-4152-8bd0-e33efffe1464") } 
MongoDB server version: 4.4.0 
{ 
  "authInfo" : {
    "authenticatedUsers" : [ ],
    "authenticatedUserRoles" : [ ] 
  }, 
  "ok" : 1
}
```


### Part-2:(Setting up Threads app)

1. First download the [Threads application](https://github.com/enciphers/ThreadsApp).

2. Open up  your terminal and go to the folder where the zip file got downloaded. 

3. Unzip the downloaded zip file for Threads application.

4. Then go inside the main directory of the application and use these commands to run the application server on your localhost:

    a. `$ cd ThreadsApp`

    b. `$ npm install`
    
    c. Enter 'yes' if you want to add dummy users to the application.

    d. `$npm run client_install` : To install the dependencies of React App.
    
    e.`$ npm start`

5. After using the above commands you will see the message in the terminal like these given below which means that the application server has been connected to the MongoDB database.
 
```
> vulnerable_app@1.0.0 start /root/Downloads/enciphers_web-master

> nodemon server.js

[nodemon] 2.0.4 
[nodemon] to restart at any time, enter `rs` 
[nodemon] watching path(s): *.*
[nodemon] watching extensions: js,mjs,json
[nodemon] starting `node server.js`
Connected to Database :: MongoDB
Connected to Moongose
```

6. As the Threads application is running on port no. 3000 in you localhost. So go to your browser and vist [http://localhost:3000/home](http://localhost:3000/home)



#### The best way to learn something is to play with it.
