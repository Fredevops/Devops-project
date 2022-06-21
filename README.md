#MERN STACK IMPLEMENTATION
**The aim of this project is to be able  to add a simple todo  application on MERN Wen stack**

*MERN*
1. MongoDB: A document-based, No-SQL database used to store application data in a form of documents
2. ExpressJS: A server side Web Application framework for Node.js
3. ReactJS: A frontend framework based on JavaScript, used to build User Interface (UI) components.
4. Node.js: it is a JavaScript runtime environment, used to run JavaScript on a machine

*Connecting To AWS EC2 instance*

I signed up and created a new Ubuntu Instance for my Project 1 LAMP stack which generated a .pem file which I downloaded from AWS to my PC.

*BACKEND CONFIGURATION*

I updated  and upgraded the server using `sudo apt update and apt upgrade`
Note! When i finished the update and upgrade, it prompted me to restart ubuntu, see pix.

![Kernel upgrade prompt](./Images/Kernel_upgrade_prompt.png)

Node.js software from Ubuntu repositories with the codes `curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -` and `sudo apt-get install -y nodejs`

i created a Todo  directory i initialise To-do project, with a new file named `package.json` with the commad 
`npm init` This file will contain information about my application and the dependencies to run. i followed the instruction and came out with the picture below.

![Content of package.json](./Images/Screenshot _package_json.png)

*INSTALL EXPRESSJS*

Express is a framework for Node.js which simplifies development, and abstracts. 
It defines routes of applications based on HTTP methods and URLs.

I installed Express with `npm install express`, created index.js file. i also installed dotenv module using 
`npm install dotenv`, opened the index.js file with `vim index.ja` , this get us into the vim enviroment.
Note that you have to make sure that you capture all the codes by copy and paste in the Vim. you will need to confirm that all code are well pasted by runing the command cat index.js. Also note that need to enter Esc:qwa to save and exit vim.
see 

On the code inputed you will notice that we specified to use port 5000.'so i allocated port 5000 to inbound rule for TCP port in EC2 Security Groups.

![View of security group inbound rules](./Images/security_group_inbound _rule.png)

I used the command `node index.js` and i got the message Server running on port 5000 in my terminal.
i also inserted my server’s Public IP :5000 in my browser see the outcome below 

![weblink with port 5000](./Images/weblink_with_port_5000.png)

To inpute codes in api.js file, I created routes directory to define various endpoints for To-do app for each task.
I open the file with the vim command `vim api.js` to copy the codes into the vim environment


*MODELS*

i instlled Mongodb  which is a NoSQL database, with the command `npm install mongoose`i  created a models which define the database schema.  the commad make directory, change directory  and file creation, all were executed with one command `mkdir models && cd models && touch todo.js`

i input `vim todo.js` then paste the code 
I update my routes from the file api.js in ‘routes’ directory to make use of the new model with `vim api.js`. I deleted the code inside  the vim with :%d command and paste the code given and save :qwa

 *MONGODB DATABASE*
 I signed up and created a new account on mLab to provide MongoDB database as a service solution (DBaaS) 
 i created a MongoDB database and collection inside mLab 

 i created a env file in Todo directory by adding the connection string to access the database in it, just as below

 `DB = 'mongodb+srv://fred-devops:Syno=Logy@<network-address>/myfirstconnection?retryWrites=true&w=majority'`

  ![DB_1_Screenshot](./Images/DB_1_Screenshot.png)

  i updated the index.js to reflect the use of .env for the Node.js to connect to the database.
  `vim index.js` i deleted the code in the vim and replaced it by pasting the entire code

i used `node index.js` to Start your server hoping to get the below message  ‘Database connected successfully’

But i got the below messagem see picture.

![Screenshot_node_index_js_syntacx_error](./Images/Screenshot_node_index_js_syntacx_error.png)

*I toubleshoot and found out the following errors* 
1. I used a special character for the password when i signed up for mongodb
2. I observed that there were spaces between DB and = and between = and 'mongodb (see Screenshot on node index.js_syntacx error message )

*Steps taken to correct syntax error*
1. I changed the password by removing any character.
2. I closed up the dspaces between Db,= and 'mongobd

see outcome below
![Database_connected_successfully](./Images/Database_connected_successfully.png)


*Testing Backend Code without Frontend using RESTful API*

With all i have done so far, i have been able to write the backend  in the To-do application and  the database. 
To test if the backend is working, i installed Postman as a RESTfulL  API development client to test our code.

POST request to the API http://<PublicIP-or-PublicDNS>:5000/api/todos. This request sends a new task to our To-Do list so the application could store it in the database.
