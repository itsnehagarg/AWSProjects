## Monitoring AWS Resources using shell scripting

use AWS CLI to connect to AWS 

Use command to configure the aws connection using:
``
aws configure
``
## Tracking AWS Resource usage
 Note: set -x is used to enable debugging for the current shell session within the bash script.

Bash script code:

```
#!/bin/bash
set -x
###############
# author: Neha Garg
# version: v1.0
# Date: 5 Oct 2023
# This script describes the AWS resource usage
################

#list s3 buckets
echo "Print list s3 buckets"
aws s3 ls

#### #list EC2 instances
echo "Print list EC2 instances"
aws ec2 describe-instances

# list Lambda functions
echo "Print list Lambda functions"
aws lambda list-functions

# list IAM users
echo "Print list  IAM users"
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

#### list Lambda functions
aws lambda list-functions





