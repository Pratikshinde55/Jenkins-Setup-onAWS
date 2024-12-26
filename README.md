# Jenkins-Setup-onAWS
On the top AWS Cloud EC2 Instance i Download and access Jenkins by WebUI

 - How to install jenkis :

Following are the ways of connect to jenkins:

1. WebUI 
2. CLI
3. API

Install and steup of jenkins bye WebUI:
 
For this i use AWS Cloud EC2 instance (amazon linux2 ami), In this instance i installed jenkins.

 - Note:

For install jenkins need yum repository and key, & Jenkins is made from Java , so jenkins work on java .
[Jenkins-Download-Link](https://pkg.jenkins.io/redhat-stable/)

Following command For Installing Jenkins on AWS EC2  :

1. Install yum repo For Jenkins:

       sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

2. Install Jenkins key:

        sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

3. Install java For Jenkins: (This command is different for different os)
   
        yum install java-17-amazon-corretto-devel
 
  - This not work in some AMI

        yum install fontconfig java-17-openjdk
4. Install Jenkins:

       yum install jenkins -y

5. Start Jenkins service:

       systemctl start jenkins
       systemctl enable jenkins

Now Jenkins is installed successfully, connet jenkins by webUI:

For this we use EC2 instance public IP and Jenkins work or 

**Jenkins Default port no. = 8080**

On Browser:--  " http://Public_IP : 8080 " (Connect Jenkins WebUI)

 - Note: 

AWS EC2 Instance have Firewall , for connect to EC2 we need allow security Group:

In security group >> edit inbound rule >> "Custom TCP  8080  myIP "

![Screenshot 2024-04-13 150813](https://github.com/Pratikshinde55/Jenkins/assets/145910708/05ad7d9f-e63e-49cf-95bb-448dfb4a1916)

Now Jenkins InterFace occurs on browser using Public_Ip of instance and 8080 port no. :

![Screenshot 2024-04-13 151042](https://github.com/Pratikshinde55/Jenkins/assets/145910708/1e827615-2005-46ef-8390-427624c5bb78)

- For Login jenkins Password is neccessary & Jenkins kept password at location **"/var/lib/jenkins/secrets/initialAdminPassword"**, Go Jenkins OS  and view 
password 
      
      cat /var/lib/jenkins/secrets/initialAdminPassword

- Copy password and paste on WebUI , now Select 'Install suggested plugins' Plugins start downloading:

![Screenshot 2024-04-13 151514](https://github.com/Pratikshinde55/Jenkins/assets/145910708/42353e64-69da-493d-9816-85153ec7e479)

- Create First Admin User Username Interface appers: Fill info and start jenkins:

![Screenshot 2024-04-13 152143](https://github.com/Pratikshinde55/Jenkins/assets/145910708/6765f294-f394-4223-8881-4755699dc96d)
































   
