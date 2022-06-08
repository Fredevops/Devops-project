**LAMP STACK IMPLIMENTATION**

**INSTALLING THE COMPONENT OF LAMP **
 *The LAMP consist of Linux, Apache, Mysql and Php* 

*LINUX*
*Conecting To AWS EC2 intance*

I signed up and created a new Ubuntu Instance for my Project 1 LAMP stack which generated a .pem file which i downloaded from AWS to my PC.

I then connected to the server using the ssh and the .pem file with the windows Terminal ssh -i "project.pem" ubuntu@ec0-00-00-00-0.compute-1.amazonaws.com
0 is the rfernce of address

I updated  and upgraded of server using sudo apt-get update and apt-get upgraded.

i have just concluded the installing of the first element of LAMP , which is LINUX (ubuntu)

**INSTALLING THE COMPONENT OF LAMP  apache**

*APACHE (engine)*

I installed apache using sudo apt installed

checked satus using sudo systemctl status apache2 which shows green dot to confirm the ststus active.

![Apache status](image/status of apache.png)

**INSTALLING THE COMPONENT OF LAMP  Mysql**

*MYSQL (Database)*

I installed Mysql using sudo apt install mysql-server

then connect to the MySQL server to authenticate installation by creating a Root User and password.

then opend mysql using sudo mysql to connect to Database.

User name and password was created to connect remotly. i confirmed that i can n login into MySQL console by using the $ sudo mysql -p.

**INSTALLING THE COMPONENT OF LAMP  php**

*PHP (coding)*

I installed php using the sudo apt install php libapache2-mod-php php-mysql

and confirem the installed version on my server by using the php -v

**CREATING A VIRTUAL HOST FOR YOUR WEBSITE USING APACHE**
