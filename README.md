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

