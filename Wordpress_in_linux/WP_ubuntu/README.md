# WordPress Website Stack for Ubuntu Linux

This CloudFormation template creates a WordPress website stack on AWS. It provisions an Amazon RDS database instance, an EC2 instance running the WordPress application, and the necessary networking components.

## Parameters

- **VpcId**: The ID of the VPC.
- **SubnetA**: The ID of Subnet A.
- **SubnetB**: The ID of Subnet B.
- **DBName**: The name of the WordPress database (default: wordpress).
- **DBIdentifier**: The identifier for the WordPress database (default: wordpress-id).
- **DBUsername**: The username for the WordPress database (default: admin).
- **DBPassword**: The password for the WordPress database (minimum length: 8, maximum length: 41).
- **DBSubnetGrp**: The name of the DB subnet group (default: wordpress-subnet-group).

## Resources

- **SecurityGroup**: AWS EC2 Security Group allowing HTTP access on port 80, MySQL access on port 3306, and SSH access on port 22.
- **DBSubnetGroup**: AWS RDS DB Subnet Group for the WordPress RDS instance.
- **DBInstance**: AWS RDS DB Instance running MySQL, used as the WordPress database.
- **EC2Instance**: AWS EC2 Instance running the WordPress application.

## Outputs

- **WordPressURL**: The URL of the WordPress website.

## Prerequisites

- An AWS account with appropriate permissions to create the required resources.
- Basic knowledge of AWS CloudFormation.

## Usage

### To deploy this CloudFormation template, follow these steps:

* Clone the repository: `git clone https://github.com/Jaylakhani37/AWS_CloudFormation_Templates.git`
* Navigate to the cloned repository: `cd AWS_CloudFormation_Templates/WP_amazon_inux_2/`
* Deploy the template using the AWS CloudFormation Console, AWS CLI, or AWS SDKs.
* Provide the necessary parameters as required.
* Wait for the stack creation to complete.
* Once the stack creation is complete, access the WordPress website using the provided URL in the CloudFormation stack outputs.