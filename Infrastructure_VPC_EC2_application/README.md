# EC2-VPC-Infrastructure

This repository contains an AWS CloudFormation template for deploying a basic infrastructure stack on Amazon Web Services (AWS). The template defines various AWS resources, including a Virtual Private Cloud (VPC), Internet Gateway, Subnet, Security Groups, and EC2 Instances.

## Resources
1. **MyVPC**: This resource defines a VPC with a CIDR block of 10.0.0.0/16 and a name tag "Task VPC".
2. **MyInternetGateway:** An Internet Gateway attached to the VPC, labeled as "Task IG".
3. **MyInternetGatewayAttachment:** Attaches the Internet Gateway to the VPC.
4. **MyRouteTable:** A route table associated with the VPC, named "Task RT".
5. **MyRoute:** A default route in the route table directing traffic to the Internet Gateway.
6. **MySubnetRouteTableAssociation:** Associates the subnet with the route table.
7. **MySubnet:** Creates a subnet within the VPC with a CIDR block of 10.0.0.0/24 and a name tag "Task Subnet". The subnet allows for the automatic assignment of public IP addresses to instances launched within it.
8. **MySecurityGroup1:** A security group named "SG1" that allows incoming traffic on ports 22 (SSH), 80 (HTTP), 3001, and 443. Outgoing traffic on the same ports is also allowed.
9. **MySecurityGroup2:** Another security group named "SG2" that allows incoming ICMP, SSH, and HTTP traffic. Outgoing traffic on the same ports is also allowed.
10. **MyInstance1:** An EC2 instance using the Amazon Machine Image (AMI) ID "ami-0dfcb1ef8550277af" with instance type t2.micro. It is launched in the subnet defined earlier and associated with the first security group (SG1). The instance is named "My Instance 1" and runs a script to set up an Apache HTTP server and a React application on port 3001.
11. **MyInstance2:** Another EC2 instance using the AMI ID "ami-0557a15b87f6559cf" with instance type t2.micro. It is also launched in the same subnet but associated with the second security group (SG2). The instance is named "My Instance 2" and runs a script to set up an Apache HTTP server.

## Prerequisites

- An AWS account with appropriate permissions to create the required resources.
- Basic knowledge of AWS CloudFormation.

## Usage

### To deploy this CloudFormation template, follow these steps:

* Clone the repository: `git clone https://github.com/Jaylakhani37/AWS_CloudFormation_Templates.git`
* Navigate to the cloned repository: `cd AWS_CloudFormation_Templates/Infrastructure_VPC_EC2_application`
* Deploy the template using the AWS CloudFormation Console, AWS CLI, or AWS SDKs.
* Provide the necessary parameters, such as key pairs, AWS region, and stack name.
* Wait for the stack creation to complete.
* Once the stack is created, you can access the deployed resources, including the EC2 instances and associated services.