# Deploying a Django Application on EC2, Dockerizing, and Configuring Jenkins 

In this tutorial, we'll go through the process of deploying a Django application on an EC2 instance, Dockerizing it, and configuring Jenkins to automate the deployment process.

## Prerequisites

Before getting started, make sure you have the following:

- An EC2 instance running with SSH access
- Docker and Jenkins installed on the EC2 instance
- A Django application ready for deployment

## Lets install the required tools on EC2 for this deployment:

# GitHub

```sh
sudo yum install git
```

# Django
```sh
	sudo yum install python3-pip
	pip install django
	python3 manage.py migrate
  python manage.py runserver 0.0.0.0:8001
```

# Docker

```sh
sudo yum install -y docker
```

### After the installation is complete, start the Docker service using the following command:

```sh
sudo service docker start
```


### To verify that Docker is installed correctly, run the following command to check the version:

```sh
sudo docker --version
```

This should install Docker on your EC2 instance and allow you to start using it.

You can also use the below commands to check if the docker is in active status or not on your machine:

```sh
sudo systemctl is-active docker
```
# Jenkins

```sh 
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo 
```

## Import a key file from Jenkins-CI to enable installation from the package:

```sh 
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
```


## Install Java (Amazon Linux 2):
```sh 
sudo amazon-linux-extras install java-openjdk11 -y
```

## Install Java (Amazon Linux 2023):

```sh 
sudo dnf install java-11-amazon-corretto -y
```


## Install Jenkins:

```sh 
sudo yum install jenkins -y
```

## Enable the Jenkins service to start at boot:

```sh 
sudo systemctl enable jenkins
```

## Start Jenkins as a service:

```sh 
sudo systemctl start jenkins
```

## You can check the status of the Jenkins service using the command:

```sh 
sudo systemctl status jenkins
```

## Deploying a Django Application on EC2

To deploy your Django application on the EC2 instance, follow these steps:

1. Copy your application files to the EC2 instance using SCP or any other file transfer method.
2. SSH into the EC2 instance and navigate to the project directory.
3. Create a virtual environment for the project and activate it.
4. Install the project dependencies using pip.
5. Run the Django development server to make sure the application is working properly.

## Dockerizing the Django Application

To Dockerize your Django application on the EC2 instance, follow these steps:

1. Create a Dockerfile in the project directory.
2. Build the Docker image using the Dockerfile and tag it with a name.
3. Run the Docker container on the EC2 instance and map the container port to the host port.

## Configuring Jenkins to Run the Django Application

To configure Jenkins to automate the deployment process of your Django application, follow these steps:

1. Create a new Jenkins job.
2. Configure the job to pull the code from your Git repository.
3. Add build steps to build the Docker image and run the container on the EC2 instance.
4. Configure post-build actions to transfer the application files to the EC2 instance using SSH.

🙌🙌 That's it! With these steps, you can deploy your Django application on an EC2 instance, Dockerize it, and configure Jenkins to automate the deployment process.

