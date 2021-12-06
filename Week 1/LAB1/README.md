# Lab 1: Create a Linux virtual machine with the Azure CLI

1. Launch Azure Cloud Shell
2. Create a resource group
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-cli

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


# 1. Launch Azure Cloud Shell
Lunching an Azure Cloud Shell is basically straight-forward, one just need to click on it's icon on azure then it auomatically opens.


# 2. Create a resource group
Unlike lauching a cloud shell, creating a resoucre group goes a bit further.
Although there are like two ways to do this either through the GUi or running a command. 
For the purpose of this learning we are to use cLi which all we basically do is run a code 
(az group create followed by whatevername we want to give the RG and include the location).
I followed the same command and i created a resource group named "Neew"

# 3. Create virtual machine
I was able to create a virtual machine which i named First running this code (az vm create --resource-group Neew --name First --image
UbuntuLTS --admin-username azureuser --generate-ssh-keys)

# 4. Open port 80 for web traffic
I was also able to open port 80 because the Vm i am creating is to allow web traffic, this code was used 
(az vm open-port --port 80 --resource-group Neew --name First)

# 5. Connect to virtual machine
I was unable to ssh into the my Vm, it displayed error Permission Denied (Public Key)which i am still battling
with, still unable to ssh to VM. I decided to create a Vm but instead of using ssh, i used Administartor and along side Putty
and i was able to connect to my VM

# 6. Install web server
I was also able to install a wab server by running the command (sudo apt-get install apache2) ip address (20.115.64.65),
i went further to try and open port 81 so as to install ngix but didn't have an head way.
I lunched another Vm and installed nginx with the ip address (20.106.217.143).

# 7. View the web server in action
I was able to view my Vms ip address (20.115.64.65), 
ip address (20.106.217.143). and it came out just like we did in class

I also went further and tried to write anything on the site just like our instructor did, i managed to create a storage on 
my resource group, added a script, installed custom line for linux but it was quite unfortunate that it came out with errors 
without even deploying.
