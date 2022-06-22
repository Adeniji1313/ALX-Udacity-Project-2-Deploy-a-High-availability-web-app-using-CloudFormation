# ALX-Udacity-Project-2-Deploy-a-High-availability-web-app-using-CloudFormation

![Project](https://user-images.githubusercontent.com/71105480/175111700-4a85d7e2-bf05-4c4d-b3c8-13a19235414e.jpeg)

A High Availability WebApp is deployed using a Launch Configuration to order to deploy four servers, two located in each private subnets created in a separate stack. The launch configuration will be used by an auto-scaling group.


The Instance type will two vCPUs and at least 4GB of RAM. The Operating System used is Ubuntu 20.04 LTS. 10GB of Disk Space is also allocated to each Web Servers.


A Bastion Host is also created in a Public Subnet to enable us SSH into the Web Servers for Troubleshooting and Maintenance. A security group that allows an SSH only from the workstation Ip


A S3 Read Only Role is also created and attached to the Web Servers to enable us our web template stored in an S3 Bucket

Change the `ParameterValue` of myIP in the Project.Json file to your workstation IP to be able to SSH into the Bastion Host
## Resources Created
- Security Groups (LoadBalancer, Web Servers, Bastion Host)
- Launch Configurations
- Auto Scaling Group
- EC2 Instance
- Load Balancer
- Listener
- Listener Rule
- Target Group
- IAM Role, Policy, Instance Profile

## Outputs
- Load Balancer 

## Stack Creation

```
aws cloudformation create-stack --stack-name Project --template-body file://Project.yml  --parameters file://Project.json --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --region=us-east-1
```
## Load Balancer Link









