# Jenkins Setup & Projects
In this repository we see how to install jenkins on EC2(ubuntu) instance and configure docker agent.

## Installation of Jenkins on EC2 instances:
 - Go to AWS Console
 - Search for EC2 and click on it
 - Click on instance running
 - Click on launch instance

    - Type instance/server name as Jenkins-master
    - Select application OS image according to your need (in this we select for ubuntu latest)
    - Select instance type t2.micro if you are using free tier account 
    - Create a new pair key and save it at safe place for logIN or SSH in Instance
    - Now click on launch instances
 - Now go to instance running and select your instance and click on connect or via terminal you can connect to your instance (ssh -i 
  key.pem ubuntu@publicIP).
    - Now update your instance (sudo apt-get update)

### Install Jenkins
 Pre-requisites:
 - Install Java(JDK)

### Below commands are used to install java & Jenkins
 #### Install Java
    sudo apt update
    sudo apt install openjdk-11-jre
 ### Verify Java is installed
    java -version
 ### Instal Jenkins
    curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins

**Note** By default, Jenkins will not be accessible to the external world due to the inbound traffic restriction by AWS. Open port 8080 in the inbound traffic rules as show below:

 - Go to ec2 instance
 - In bottom tab click on security group
 - Click on edit inbound rules
    - Add rule as below
        - Type: Custom TCP
        - Port Range: 8080
        - Source: Anywhere
        - Description: Jenkins

### Login to Jenkins using the below URL:
    - http://<public-ip>:8080
Run the command to copy the Jenkins Admin Password
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword
 - Enter the Administrator password
 - Click on install suggested plugins
 - Wait for the Jenkins to Install suggested plugins
 - Create First Admin User
    - Click on Save and Finish
    - Click on Start using Jenkins