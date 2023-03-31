# ⚒️ Deploying Web Application on AWS Elastic Cloud Compute(EC2) instance

Watch our YouTube video on this topic: https://youtu.be/xd_FjQClc7M

In this ReadMe, I will share the steps to deploy a Spring Boot web application on Amazon EC2 instance.


## 🤳Tech Stack used in the deployment

- [Java 8] - Java needs to be installed.
- [Sprint Boot Application] - A running Sprint Boot Application
- [Apache Tomcat] - Tomcat server for deployment

### 🔦 Steps for deploying the application
	1. Create a WAR file of your Spring Boot Project
	2. Create an EC2 instance on the AWS console
	3. Install Java and Tomcat server on EC2
	4. Give permission to the user in tomcat to access Manage apps on the GUI
	5. Remove default localhost URL in Tomcat settings
	6. Select the WAR file and deploy it


### 🔖Step 1: Create a WAR file of your Spring Boot Project
1. In pom.xml, add war packaging configuration.
2. Once you click on the Maven build, the “Edit Configuration” window will be opened. 
3. Write the command “clean install” in Goals and click on Run.
4. Maven Clean install on Eclipse<br />
5. The generated WAR file is present in the target folder in the project structure.


### 💻Step 2: Create an EC2 instance on the AWS console

1. Create a Linux EC2 instance in AWS management console. 

2. Add a rule in the security group for the port to host Spring Boot application. We are going to use the default port 8080.

### 👩‍💻Step 3: Install Java and Tomcat server on EC2
1. Firstly, update the EC2 instance that we created:
```sh
sudo yum update -y
```
2. Install Java 8 using the below mentioned command:
```sh 
yum install java-1.8.0-openjdk
```
3. Verify whether Java is installed properly by checking its version using the below mentioned command:
``` 
java -version
```

4. Visit the following link for downloading the Apache Tomcat :
Apache Tomcat®
Welcome to the Apache Tomcat ® 9.x software download page. This page provides download links for obtaining the latest tomcat.apache.org

(https://tomcat.apache.org/download-90.cgi)

5. Right-click on the tar.gz file and copy the link address of Tomcat <br/>

6. Download the tomcat on EC2 using the below mentioned command:
```sh 
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.64/bin/apache-tomcat-9.0.64.tar.gz
```

7. Unzip the downloaded .tar.gz:
```sh 
tar -zvxf apache-tomcat-9.0.72.tar.gz
```

8. Now we have successfully installed Java 8 and Apache Tomcat serveron the EC2 instance. 

9. Now, let us start the tomcat server and verify whether it is installed correctly by going to the below directory location.


```sh 
cd apache-tomcat-9.0.64/
```

```sh 
cd bin/
```

In the bin folder, startup.sh file is used to start the tomcat server. Run the following command to run the tomcat server.
```sh  
./startup.sh
```
Now, copy the public IPv4 address or public DNS address of your instance, paste it on the browser, and attach:8080 which is the port number we configured.
for example, 12.34.56.78:8080
The following page will get displayed, if the tomcat is installed properly.<br/>

### Step 4: Give permission to the user in tomcat to access Manage apps on the GUI
Now we will open tomcat-users.xml file which is available in the conf folder
```sh 
cd conf
```
Now, open the tomcat-users.xml. We can use vi editor for this task.
```sh 
vi tomcat-users.xml
```
Add the following code to this file for creating the user and assigning the role for using Manager App in GUI for deploying the application:
```
<user username="your-username" password="your-password" roles="manager-gui"/>
```


### 📸Step 5: Remove default localhost URL in Tomcat settings
Now we will remove the below mentioned code from context.xml which is available in webapps/manager/META-INF folder:

<Valve className="org.apache.catalina.valves.RemoteAddValve" allow="127\.\d+\.\d+|::1|0:0:0:0:0:0:0:1"/>

Now, we need to shut down the tomcat and then restart it.
```sh 
cd bin
./shutdown.sh
./startup.sh
```


### 🗃️Step 6: Select the WAR file and deploy it
1. Refresh the page and click on the Manager App.
2. It will prompt for the username and password.
3. Now we will uUse the username and password which you have used for creating the user.
4. Select the WAR file by clicking on “Choose file” in the “WAR file to Deploy” section under “Deploy”.

<br/>

5. Now verify the deployment of the  WAR file by attaching the WAR file name with the URL we created above and check it in the browser.
Now our Spring Boot application is successfully deployed!
