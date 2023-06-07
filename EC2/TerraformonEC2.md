# Terraform on EC2

### Install terraform


```
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```

### Install the HashiCorp GPG key

```
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
```

### Verify the key's fingerprint.

```
 gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```

### Add the official HashiCorp repository to your system
```
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```
```
sudo apt update

```
### Install Terraform from the new repository.
```
 sudo apt-get install terraform
 ```
 ```
 terraform --version
 ```
 
### Create a HCL file 
```
mkdir terraform_folder
cd terraform_folder
vim terraform_file.tf
```
 ### Add the below HCL to the file created above:
 
resource "local_file" "devops"{
		filename = "/home/terraform_folder/terraform_file.txt"
		content ="hey there"

}


### Validate the HCL file

```
terraform validate
```
 
 #### Always run the command terraform init when you write the configuration
 
 ```
 terraform init
 ```
 
  ```
 terraform plan
 ```
 
   ```
 terraform apply
 ```
 
 ### Created a docker tf file
 
 Made changes to docker_terraform.tf

terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 2.13.0"
    }
  }
}
provider "docker" {}
resource "docker_image" "nginx" {
  name         = "nginx:latest"
  keep_locally = false
}
resource "docker_container" "nginx" {
  image = docker_image.nginx.image_id
  name  = "tutorial"
  ports {
    internal = 80
    external = 80
  }
}

 
 
 ### Install docker
 ```
 sudo apt-get install docker.io
 
 sudo chown $USER /var/run/docker.sock
  ```
   ```
 terraform init
 
 terraform plan
 
 terraform validate
  ```
 ### Final command
  ```
 terraform apply
  ```
