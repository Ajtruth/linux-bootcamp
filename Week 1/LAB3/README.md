# Lab 3: Manage Azure disks with the Azure CLI

1. Default Azure disks
2. Azure data disks
3. VM disk types
4. Launch Azure Cloud Shell
5. Create and attach disks
6. Prepare data disks
7. Take a disk snapshot

### Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart



# 1. Default Azure disks

At the creation of any virtual machine two disks are automatically attached to the virtual machine, they
are the operting system disk and temporary disk. 
I learnt that the OS disk can be sized up to 2 terabyte and because of it's configuration the disk should 
not be used for applications or data.
l learnt that Temp disks are highly performant and may be used for operations such as temporary data processing
also, if the VM is moved to a new host any data stored on the temp disk is removed.

 
# 2. Azure data disks

The Data Disk is used to install applications and store data. Even after creation of the VM we can add data disk 
if we are not satisfied with the size of the disk initailly created. The size of VM determines how many data disks 
can be attached to the VM.


# 3. VM disk types

There are 2 types of Azure disk called 
Standard disk and Premium disks
The Standard disks is backed by HDDs. I learnt it's cost-effective storage while still being performant. It is 
said to be goodfor cost effective dev and test workload.

The Premium disk backed by SSD-based, it's an high-performant low-latency disk and it is said to be perfect for 
VMs running production workload.

# 4. Launch Azure Cloud Shell
Lunching an Azure Cloud Shell just involes clicking on it's icon on azure portal then it auomatically opens.

# 5. Create and attach disks

As earlier stated if we have created our VM and we want to put and additional disk we just need to run some commands. 
I used one of my already created VM named (First) and i attached a new disk into it running ths command (az vm disk attach).



# 6. Prepare data disks

I was also able to partition it using ths command (sudo parted /dev/sdc --script mklabel gpt mkpart xfspart xfs 0% 100%)
I was able to mount the partitioned disk so it was able to access the operating system. If we rebot after this then all 
the disk created will disappear because we've not saved it on the Os, so to do this i ran this command on my shell 
(sudo -i blkid), I reboted and it remained on the OS.



# 7. Take a disk snapshot
Snapshots are used to save the state of a VM before any configuration is made. Incase of any mix-up the VM can be restored 
using the snapshot. This command (az snapshot create) added with resource group, source and the disk name helps to create/
take a snapshot
