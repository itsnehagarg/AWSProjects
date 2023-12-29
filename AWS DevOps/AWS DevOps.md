## AWS DevOps

Services used:

1. AWS IAM & AWS KMS (Security related- Authentication / Authorization services)
3. AWS CodeArtifact & S3 (Storage services)
4. CodeCommit, Code Build, Code Deploy & Code Pipeline (DevOps services)
5. EC2, ECS and Lambda (Deployment services)

Steps involved:

1. CodeCommit Repo is similar to Github repo and developer commits the code to Code Commit Repo.
2. Once the code is committed it needs to build, test and deployed so, Code Build service will be responsible for building the code.
3. Once the code is build successfully then the artifact will be placed in AWS CodeArtifact service.
4. Code Deploy will help us in deploying the code on one of the services  EC2, ECS or Lambda.
5. Now use Code Pipeline to Automate continuous delivery pipelines for fast and reliable updates.

### CodeCommit

1. Create a new CodeCommit repository
![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/01722f0c-d69d-4b75-adb6-435fb224eed3)

2. Click on Clone HTTPS

   ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/aad95d09-907a-4810-919b-8404e7740742)

3. Copy the URL
4. Go to your local machine and use the below command:
  ``
git clone URL copied
  ``
6.  It will ask for your credentials.
7.  Go to IAM service. Configure the User and security_credentials. Click on "HTTPS Git credentials for AWS CodeCommit" and generate credentails.
8.  Use these credentials to connect to CodeCommit from your local machine and clone the repo.
   ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/cd9a3453-3bef-4935-b054-fcd0aff305a2)

9. Push the code on CodeCommit repo.
![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/e79c9558-dd8b-4dac-8e35-ab692f959515)








   

   
