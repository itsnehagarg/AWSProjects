## Monitoring AWS Resources using shell scripting

use AWS CLI to connect to AWS 

Use command to configure the aws connection using:
``
aws configure
``
## Tracking AWS Resource usage

Bash script code:

```
#!/bin/bash

###############
# author: Neha Garg
# version: v1.0
# Date: 5 Oct 2023
# This script describes the AWS resource usage
################
#### #list s3 buckets
aws s3 ls

#### #list EC2 instances
aws ec2 describe-instances

# list Lambda functions
aws lambda list-functions

# list IAM users
aws iam list-users


```

## Lets give the permissions for the script to be executed
```
chmod 777 aws-script.sh
```
### Run the script
```
./aws-script.sh
```

```
./aws-script.sh | more
```

### Commands used in bash script

#### #list s3 buckets
aws s3 ls

#### #list EC2 instances
aws ec2 describe-instances

# list Lambda functions
aws lambda list-functions





