# Lab 2: Install a LAMP stack on an Azure Linux VM

1. Prepare the LAMP server
2. Test your Lamp server
3. Secure the database server
4. (Optional) Install phpMyAdmin

### Notes:

Tutorial: Install a LAMP web server on the Amazon Linux AMI
* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/install-LAMP.html

Tutorial: Host a WordPress blog on Amazon Linux 2
* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/hosting-wordpress.html

Sample Gist
* https://gist.github.com/mikepfeiffer/c079608703e604224e58a3d40d0fa043#file-lamp-linux-aws-sh



# 1. Prepare the LAMP server

Just like installing a LAMP stack (Linux, Apache, Mysql, PHP) on Azure, I was also able to do the same thing on
Aws. As always we can install these using both GUI and CLI. 
NOTE; I was able to install the LAMP stack using the followings code but on Amazon Linux Ami.
To install the LAMP stack we need to have a running instance and our instance security group must have open port 
80 opened since it's a web server we are working on.

I created my VM using an Amazon Linux Ami and on this VM i configured my security group to open port 80 for 
the web sever and port 22 for ssh.

I was able to run this following command to install Apache, Mysql and PHP
 * sudo yum install -y httpd24 php72 mysql57-server php72-mysqlnd

This command installed the various apps simultaneously.

 * sudo service httpd start - ( This is to start Apache web server after installation)
 * sudo chkconfig httpd on  - ( This is to enable Apache web server to survive a reboot).

 
# 2. Test your Lamp server

I was able to test my various installed apps by using my public Ip. 

For my PHP, to create a PHP file i ran this command as directed 
 * echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
but it came back with an error "permission denied" 

After much troubleshooting i ran another ran this command and it gave the desired outcome 
 * sudo sh -c 'echo "<?php phpinfo(); ?>" > /var/www/html/info.php'

After this i was able to view my PHP page online, while Apache was the Index html file, Php was the other page.
I was able to put in (my Ip address/info.php).


# 3. Secure the database server

To secure my database which is MySql i was able to run the folloeing command to start and secure Mysql 
 * sudo service mysqld start - (This is to start Mysql database)
 * sudo mysql_secure_installation - (This is to secure Mysql, I was able setting my password, disable the 
remote root login. I was remove the test database).


# 4. (Optional) Install phpMyAdmin

I encountered errors trying to run commands to install PhpMyAdmin at the time of submitting this aasignment, Just like
my ssh issue, i will have to continue running trials to get the desired outcome.