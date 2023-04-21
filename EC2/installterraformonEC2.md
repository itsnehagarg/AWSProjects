# 👩‍💼 Installing Terraform on Amazon Linux EC2 Instance using yum-config-manager

This guide will walk you through the process of installing Terraform on an Amazon Linux EC2 instance using yum-config-manager.

## 😎 Prerequisites

- An Amazon Linux EC2 instance with Internet connectivity
- SSH access to the EC2 instance

## ✌ Installation Steps

1. Connect to your EC2 instance via SSH.

2. Update the package list:

```sh
sudo yum update
```

3. Install yum-config-manager:

```sh
sudo yum install -y yum-utils
```

4. Use yum-config-manager to add the official HashiCorp Linux repository:

```sh
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
```

5. Install Terraform:

```sh
sudo yum -y install terraform
```

6. Verify that Terraform is installed correctly:

```sh
terraform version
```

This should display the installed version of Terraform.

Congratulations, you have successfully installed Terraform on your Amazon Linux EC2 instance using yum-config-manager!

