
# Using AWS platform to create and install Docker image. Answring all the week 4 labs on this page 




# 1. Installing Docker  

My Azure is asking for an upgrade which includes  making payment since it's an account to learn i decided 
to do this lab using AWS. 

I was able to create and install a Docker image using AWS platform.

I created a virtual machine to achieve the task ahead which includes creating and installing a Docker 
image. I created the instance using amazon linux ami 2. I was able to ssh into my Vm after opening 
port 22. I also opened port 80 for web traffic.

(sudo yum update -y), This is the first command to run on any newly created Instance to be able to keep it 
updated.

(sudo amazon-linux-extras install docker), I enetered this command to install the latest configuration of 
Docker image. It Installed without hiccpus, no error poped up.

(sudo service docker start), I used this command initially to start the nwely installed docker image but it 
won't start, it refered me to use sudo systemctl. so i used this command to start the new Docker image 
(sudo systemctl start docker.service) this command started the docker image without error.


(sudo usermod -a -G docker ec2-user) i was able to run this command to allow my ec2-user to be added to docker 
group so as to have access to some permissions. Although it didn't work at first not untill i reboot 
the instance.  


(docker info) - I was able to use this command to test whether or not i have been added to the docker group so
as to have access to some permisions. After i had to reboot the instance this command was successfully.


# 2. Create a Docker Image

(touch Dockerfile1) I was able to create a docker image. i created the file which i named Dockerfile1.

I was able to look into the file using LS command which the file was empty. I then inputed some commands 
into the file using ( sudo nano dockerfile1), it opened up the file and inputed this content into the file 

FROM ubuntu:18.04

# Install dependencies
RUN apt-get update && \
 apt-get -y install apache2

# Install apache and write hello world message
RUN echo 'Hello World!' > /var/www/html/index.html


# Configure apache
RUN echo '. /etc/apache2/envvars' > /root/run_apache.sh && \
 echo 'mkdir -p /var/run/apache2' >> /root/run_apache.sh && \
 echo 'mkdir -p /var/lock/apache2' >> /root/run_apache.sh && \ 
 echo '/usr/sbin/apache2 -D FOREGROUND' >> /root/run_apache.sh && \ 
 chmod 755 /root/run_apache.sh

EXPOSE 80

CMD /root/run_apache.sh


Then i ran (cat dockerfile1) and it brought back this file which means i have succesfully inputed the content.



(docker build -t hello-world .) i was able to use this command to create a docker image, which was done seamlessly
then i ran this
(docker images --filter reference=hello-world) command to verify that the image was created correctly which gave the 
expected output.
 
since i have opened up port 80 at initital stage of creating the Vm what i needed to do was to check out my newly
created Docker image using the Ip address of my Vm. 

It came out okay as expected. I had HELLO WORD! on my docker page 