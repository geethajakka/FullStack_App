# FullStack_App

Create Security Group with All the Inbound rules Port Ranges that needs to be Allowed
Create Virtual Machines for SonarQube and Nexus where Nexus minimum 4gb is required like t2medium
Create Another Virtual Machine for Jenkins which is like toolarge
Ssh into the each VM with their IP Addresses
For Jenkins 1st run sudo apt update then
Install Java sudo apt install openjdk-22-jre-headless -y
Installing Jenkins from the jenkins Documentation Page
Linux/Ubuntu long term releases
Copy all the commands into a file like vi script.sh
Give executable permissions to the file sudo chmod +x script.sh
Run it ./script.sh
all commands will execute and jenkins got installed
Install Docker
sudo apt install docker.io -y
Run the command to give permission for all users on this machine
sudo chmod 666 /var/run/docker.sock

For Nexus Server we install Docker
sudo apt install docker.io -y
we run the command for the nexus download docker image and create container out of it
sudo docker run -d -p 8081:8081 sonatype/nexus3
Having Host port and container port here host port can change but conatiner port cannot change
sudo docker ps
Docker container for nexus is created
To get Accessing Nexus Server we login with username as admin and for password we get into adminpassword file inside the container so we run command
sudo docker exec -it containerid /bin/bash
cd sonatype-work/
cd nexus3/
cat admin.password
then sign into nexus server by setting new pwd



For SonarQube Server we install Docker
sudo apt install docker.io -y
we run the command to create container for sonarqube
sudo docker run -d -p 9000:9000 sonarqube:lts-community
sudo docker ps
To get Accessing SonarQube Server we login with username as admin and for password as admin
In SonarQube--->Administration-->security-->user--->token--->generate token


Install All needed Plugins in the Jenkins
Mange jenkins-->Tools---->select sonarqube Scanner,Maven,Docker  ---->Install Automatically

