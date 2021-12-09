# Lab 3: GCP

## Compute Engine

### Tutorials

# 1. Quickstart using a Linux VM

# 2. Connect to Linux VMs

# 3. Connecting to Linux VMs using advanced methods

# 4. Using startup scripts on Linux VMs

# 5. Querying VM metadata 






# 1. Quickstart using a Linux VM

Creating a Vm using GCP platform.

Aforemost we need to create a billing account becasue withouth it the project cannot be created.

I was able to create virtual machines on this platform using both the user interface and the 
cloudshell.

Using the Interface was straight-forward since i am sure of the images i am willing to use unlike
the command line that has lots of command. To use the command we need to set all the images by 
running various commands e.g

gcloud projects create <project_id> --name=<project_name> --set-as-default(it is used in creating
a project).
gcloud config set compute/region (it is used to set the region)
gcloud config set compute/zone (it is used to set the zone)
create demo --machine-type=e2-micro --description="demo web" --image-project=ubuntu-os-cloud 
--image-family=ubuntu-2004-lts --network=vpc-network --subnet=default --service-account=Account
--tags=ssh,web (This is to create an instance).
  
 

# 2. Connect to Linux VMs

I was able to connect to my Vm on using ssh on a new windows and it automatically connects

# 3. Connecting to Linux VMs using advanced methods

Connect to instances using third-party tools
Connect to instances as the root user
SSH with security keys

I was able to ssh into my instance using the third party client Putty configuration to create an ssh key
and using the key to ssh into my VM. 
I was also able to go through the root-user to log in into my VM.


# 4. Using startup scripts on Linux VMs

Using the exapmle used during the class i was able to add up a start-up script to my instance at the inital 
stage.

I created an instance and i added a start-up script to it at the stage of creating it by opening the
Networking, disks ..., i opend up the Management section and added the script to the automation section.

I futher learnt that a start up script can be added to an already created Instance either from the local or Cloud
depending on where the script is stored, doing this some permission needs to be set bacause if they aren't set it
won't work.
I also learnt that that a start-up script can also be created to affect all the instance created in a project
and one can make it affect only one instance. 

This can be acheived using both GUI and CLi


# 5. Querying VM metadata

I was also able to install a web server apache2, verify that it's working and able to survive a reboot
sudo install apache2 
sudo systemctl start apache2
sudo systemctl enable apache2
Access using this ip address 35.240.98.110
