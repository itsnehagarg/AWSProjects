# Installing Jenkins on AWS

This guide will walk you through the steps for installing Jenkins on an Amazon Web Services (AWS) EC2 instance running Ubuntu Linux.

## Prerequisites

Before you begin, you'll need the following:

- An AWS account
- An EC2 instance running Ubuntu Linux
- SSH access to the EC2 instance

## Step 1: Update your system packages

First, connect to your EC2 instance via SSH and update your system packages:

```sh
sudo yum update -y
```

## Step2 : Add the Jenkins repo using the following command:

```sh 
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo 
```

## Step 3: Import a key file from Jenkins-CI to enable installation from the package:

```sh 
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
```


## Step 4a : Install Java (Amazon Linux 2):
```sh 
sudo amazon-linux-extras install java-openjdk11 -y
```

## Step 4b :Install Java (Amazon Linux 2023):

```sh 
sudo dnf install java-11-amazon-corretto -y
```


## Step 5: Install Jenkins:

```sh 
sudo yum install jenkins -y
```

## Step 6: Enable the Jenkins service to start at boot:

```sh 
sudo systemctl enable jenkins
```

## Step 7: Start Jenkins as a service:

```sh 
sudo systemctl start jenkins
```

## Step 8: You can check the status of the Jenkins service using the command:

```sh 
sudo systemctl status jenkins
```

## Step 9: Access Jenkins

Jenkins will be available on port 8080 of your EC2 instance's public IP address. To access Jenkins, open a web browser and navigate to `http://[your-ec2-instance-public-ip]:8080`. You will be prompted to enter an initial admin password, which can be found in the file `/var/lib/jenkins/secrets/initialAdminPassword` on your EC2 instance.

That's it! You now have Jenkins installed and running on your AWS EC2 instance.🙌✌️
