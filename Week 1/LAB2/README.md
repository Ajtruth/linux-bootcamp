# Lab 2: Manage Linux VMs with the Azure CLI

1. Create resource group
2. Create virtual machine
3. Connect to VM
4. Understand VM images
5. Understand VM sizes
6. VM power states
7. Management tasks

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


# 1. Create resoucre group
I am now acquitted to creating resource groups using both GUi and CLi, I created a
resource group using CLi named FreeRg

# 2. Create Virtual machine 
I created a virtual machine and named it Project

# 3. Connect to Vm
I was unable to SSh into my vm, keeps brining permission deined (public key) 
so i had to connect using use Putty and i was able to connect to my Vm

# 4. Understand VM images
The VM images is the configuration of what i want my VM to carry, it includes the ram, the c.p.u, 
the disk etc. The VM Images are in hundreds, there are lots of configurations to pick from depending 
on the work we want to carry out. We have Images from different publisher like SUSE,Redhat,windows, 
coreos. The images are much so we can pick from any of them depending on the task.

# 5. Understand VM sizes
The VM sizes determines the amount of compute resource, the memory avaliable to the VM. One need to pick the 
size that would be enough for the workload to be done. If the task ahead requires much space to work with then
it is advisable to pick a large size. One can also create the particular size needed for the job and also go
ahead tp partition it running some commands

# 6. VM power State
The VM power state shows the current state of the virtually machine. Maybe or not it is running, stopped
stopped, starting, deallocating. we can view the power state by running some command on the cloud shell starting 
with (az vm grt-instance-view) then add other informations

# 7. Management task
One will want to manage the VM and will want to run the management tasks such as 
deleting, starting, stopping, a VM. Using various command for various task.