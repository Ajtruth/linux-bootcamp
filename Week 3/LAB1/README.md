# Lab 1: Install a LAMP stack on an Azure Linux VM

1. Create a resource group
2. Create a virtual machine
3. Open port 80 for web traffic
4. SSH into your VM
5. Install Apache, MySQL, and PHP
6. Install WordPress

### Notes:

Tutorial: Install a LAMP stack on an Azure Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-lamp-stack

Sample Gist
* https://gist.github.com/mikepfeiffer/96d659042f0575a617648a33c92b8f4a

Build and run a web application with the MEAN stack on an Azure Linux virtual machine
* https://docs.microsoft.com/en-us/learn/modules/build-a-web-app-with-mean-on-a-linux-vm/

MEAN Stack App
* https://github.com/MicrosoftDocs/mslearn-build-a-web-app-with-mean-on-a-linux-vm


# 1. Create a resource group

I created a resource group on my Azure account using the CLI, cloud shell which i am now conversant with. One
can create resource group using interface or command line like bash, powershell ..., I used bash on the 
cloudshell to create my resource group. I used this command to create the resource group;
 * az group create --name Goop --location canada central
 
# 2. Create a virtual machine

Just like creating a resoucre group, I am now conversant with creating a resource group I am also now conversant 
creating or opening a virtual machine both on the user interface and using the command line. I was able to create 
a VM with the following commands; 
 * az vm create --resource-group Goop --name proj --image UbuntuLTS --admin-username azureuser --generate-ssh-keys
Meaning i created a resource group (goop), named it (proj), I used UbuntuLTS as my image/Os and I generated ssh-key

# 3. Open port 80 for web traffic

Again opening inbound rules and outbound are now things I do confidentally do on CLI and GUi, I can now open 
different port for diferent uses, port 80, port 22,port 443... just like port 22 is for ssh, port 80 is 
for web traffic and the Virual machine i am creating as to do with website so i opened port 80 on cloushell 
using this command
 * az vm open-port --port 80 --resource-group Goop --name proj

# 4. SSH into your VM

Ealier at the start of the program i was unable to ssh into my Vm's, had sleepless nights doing these not untill I
learnt about the inbound and oubound rules I have been able to ssh into my Vm's without stress.
I ssh into my Vm to install a LAMP stack  (Linux, Apache, Mysql, PHP).

# 5. Install Apache, MySQL, and PHP

To install the LAMP stack  (Linux, Apache, Mysql, PhP), I was able to learn and run the commands to install the 
various applications from how we were taught during the class. Although the can be installed easily using the GUI,
I was able to install mine using various commands taught in class. I was able to install Apache, PHP and Mysql using this 
command on Azure portal.
 * sudo apt update && sudo apt install lamp-server^ -y (-y command is the automatic yes I want to install)

I was able to verify my apache (apache2 -v)
I was able to verify and secure mysql installation (sudo apt update && sudo apt install lamp-server^ -y)
I was able to validate my login, created a PHP page on my VM. 

# 6. Install WordPress

Like other LAMP stack I was able to install wordpress, using the folloeing command
 * sudo apt install wordpress -y ( as always yhe -y is yes install for me without querry).
(sudo nano wordpress.sql) - using this commnand i was able to write a wordpress script 


I was able to view all my applications in action and also edited my wordpress. 













