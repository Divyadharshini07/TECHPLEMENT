# TECHPLEMENT
### Monolithic Architecture:

1. *Create an EC2 instance with t2.micro and Ubuntu AMI:*
   
   aws ec2 run-instances --image-id <your-ubuntu-ami-id> --instance-type t2.micro --key-name <your-key-pair-name> --security-group-ids <your-security-group-id> --count 1
   

2. *SSH into the EC2 instance:*
   
   ssh -i <your-key-pair.pem> ubuntu@<your-instance-public-ip>
   

3. *Install MySQL and WordPress on the same instance:*
   
   sudo apt-get update
   sudo apt-get install mysql-server php libapache2-mod-php php-mysql
   sudo apt-get install wordpress
   

4. *Configure MySQL for WordPress:*
   Follow MySQL setup steps to create a database, user, and grant permissions.

5. *Configure WordPress:*
   
   sudo ln -s /usr/share/wordpress /var/www/html/wordpress
   sudo cp /usr/share/wordpress/wp-config-sample.php /etc/wordpress/config-localhost.php
   sudo nano /etc/wordpress/config-localhost.php
   
   Edit the database settings in the config file.

6. *Access WordPress:*
   Open a web browser and go to your instance's public IP to complete WordPress setup.

### Microservices Architecture:

1. *Create two EC2 instances (one for WordPress, one for MySQL):*
   
   aws ec2 run-instances --image-id <your-ubuntu-ami-id> --instance-type t2.micro --key-name <your-key-pair-name> --security-group-ids <your-security-group-id> --count 2
   

2. *SSH into each EC2 instance.*

3. *Install MySQL on the MySQL instance:*
   
   sudo apt-get update
   sudo apt-get install mysql-server
   

4. *Configure MySQL for WordPress:*
   Follow MySQL setup steps to create a database, user, and grant permissions.

5. *Install WordPress on the WordPress instance:*
   
   sudo apt-get update
   sudo apt-get install wordpress
   

6. *Configure WordPress on the WordPress instance:*
   Follow steps 5 and 6 from the monolithic architecture.

7. *Access WordPress:*
   Open a web browser and go to your WordPress instance's public IP to complete WordPress setup.

Remember to replace placeholders like <your-ubuntu-ami-id>, <your-key-pair-name>, <your-security-group-id>, <your-instance-public-ip>, etc., with your actual values.

TASK IS COMPLETED
