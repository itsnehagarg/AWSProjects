# Installing Docker on an Amazon Linux EC2 Instance

This guide will walk you through the steps to install Docker on an Amazon Linux EC2 instance.

## Prerequisites

- An Amazon Linux EC2 instance
- SSH access to the instance

## Steps

### 🔖Step 1: Connect to the EC2 instance using SSH.

```
 ssh -i copykeypair.pem ec2-user@<EC2-INSTANCE-PUBLIC-IP-ADDRESS>
```

### 💻Step 2: Run the following command to update the package index:

```sh
sudo yum update -y
```

### 👩‍💻Step 3: Once the update is complete, run the following command to install Docker:

```sh
sudo yum install -y docker
```

### 🔦 Step 4: After the installation is complete, start the Docker service using the following command:

```sh
sudo service docker start
```
sudo service docker start



### ✌️Step 5: To verify that Docker is installed correctly, run the following command to check the version:

```sh
docker --version
```

This should install Docker on your EC2 instance and allow you to start using it.

