# Lab 4: Create and use an SSH public-private key pair for Linux VMs in Azure

1. Supported SSH key formats
2. Create an SSH key pair
3. Provide an SSH public key when deploying a VM
4. SSH into your VM

### Notes:

Quickstart: SSH for Linux VMs
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


# 1. Supported SSH key formats
There are ssh key format that azure support

# 2. Create an SSH key pair
I created the ssh key pair as instructed (ssh-keygen -m PEM -t rsa -b 4096)

# 3. Provide an SSH public key when deploying a VM
I provided the ssh pulic key while deploying into the VM

# 4. SSH into your VM
I ssh into the VM and got this reply
Permission denied (public key), i have scorged the internet trying to provide a solution to 
it but to no avail. I had to conect to my VM using putty key username and passweord. i believe i
would be able to rectify the error soon.