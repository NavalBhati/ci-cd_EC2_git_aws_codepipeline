# ci-cd_EC2_git_aws_codepipeline
CI/CD Deployment with EC2 instance and aws codepipeline
-------------
First We Need two IAM roles
-------------
1. AmazonEC2RoleforAWSCodeDeploy --> this role will attach to EC2
2. AWSCodeDeployRole --> this for aws code deploy

While creating EC2 instance assign IAM role and add this bash script in user data

User Data for Dependencies installations for AMAZON Linux 2:-

```bash
#!/bin/bash
sudo yum -y update
sudo yum -y install ruby
sudo yum -y install wget
cd /home/ec2-user
wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install
sudo chmod +x ./install
sudo ./install auto
sudo yum install -y python-pip
sudo pip install awscli
```


Open all ports for a while - #This is for testing only not recommend in production server
![Alt Text](output.png)
