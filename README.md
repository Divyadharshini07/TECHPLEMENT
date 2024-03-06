# TECHPLEMENT
sudo apt update 

The sudo apt update command is used to update the local package index and provide the system with the latest information about available packages.

sudo apt upgrade
The sudo apt upgrade command downloads and installs the latest packages for a system, replacing any older versions. This command can be used to free up system memory

1. Install Apache server on Ubuntu
sudo apt install apache2
(Apache HTTP Server is a free, open-source web server software. It's the most commonly used web server on Linux systems)


2. Install php runtime and php mysql connector

sudo apt install php libapache2-mod-php php-mysql

 (Install core PHP packages as dependencies)


3. Install MySQL server

sudo apt install mysql-server 
(This installs the package for the MySQL server, as well as the packages for the client and for the database common files.)

4. Login to MySQL server

sudo mysql -u root


5. Change authentication plugin to mysql_native_password (change the password to something strong)

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Testpassword@123';

6. Create a new database user for wordpress (change the password to something strong)

CREATE USER 'wp_user'@localhost IDENTIFIED BY 'Testpassword@123';

7. Create a database for wordpress
CREATE DATABASE wp;

8. Grant all privilges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp_user'@localhost;
crtl+d to exit from sql terminal

9. Download wordpress
cd /tmp
wget https://wordpress.org/latest.tar.gz

10. Unzip
tar -xvf latest.tar.gz

11. Move wordpress folder to apahe document root
sudo mv wordpress/ /var/www/html

12. Command to restart/reload apache server
sudo systemctl restart apache2
OR
sudo systemctl reload apache2


for testing purpose copy the IP adress of your instance and paste it in any browser with http/: "ip adress"/wordpress  
Here we can see wordpress site ,enter your  database name ,username and password

at this step we may get error ,here he have to troublshoot this error ,for that we just need to follow the steps as given in wordpress dialogue box

here error was  wp.congig.php file(as mentioned ) was missing ,so we have to create a new file by name wp.congig.php (as mentioned )by using command 

13 nano "file name ",

for saving this file use ctrl+o ,enter,ctrl+x hit enter 


refresh http/: "ip adress"/wordpress tab ,you will get welcome  note from wordpress 

TASK IS COMPLETED
