# AWS CloudFormation Template

This is a CloudFormation template to create an AWS RDS database instance. It allows you to configure various parameters for the database.

## Parameters

- **DBName** (String): Name of the database to create.
- **DBUsername** (String): Username for the database.
- **DBPassword** (String): Password for MySQL database access. Must contain only alphanumeric characters, with a length between 8 and 41 characters.
- **DBInstanceClass** (String): RDS instance type for the database. Default is `db.t3.micro`.
- **DBStorageSize** (Number): Allocated storage size for the database in GB. Default is 10.
- **MultiAZ** (String): Enable multi-AZ deployment (true/false). Default is `true`.
- **DBBackupRetentionPeriod** (Number): Number of days for which automatic database snapshots are retained for backup. Must be between 0 and 35 days. Default is 7.
- **VpcId** (AWS::EC2::VPC::Id): ID of the VPC in which to create the database.
- **SubnetIds** (`List<AWS::EC2::Subnet::Id>`): List of subnet IDs in the VPC for the database.
- **CreateReadReplica** (String): Specifies whether to create a read replica or not. Default is `false`.
- **RRBackupRetentionPeriod** (Number): Number of days for which automatic database snapshots are retained for backup on the read replica. Must be between 0 and 35 days. Default is 7.
- **DBPubliclyAccessible** (String): For publicly accessible (true/false). Default is `false`.
- **DBStorageEncrypted** (String): For storage encrypted (true/false). Default is `false`.
- **DBDeletionProtection** (String): For deletion protection (true/false). Default is `false`.

## Resources

- **DBInstance**: AWS RDS DBInstance resource that represents the database instance.
- **ReadReplicaInstance**: AWS RDS DBInstance resource for creating a read replica. Only created if `CreateReadReplica` is set to `true`.
- **DBSecurityGroup**: AWS EC2 SecurityGroup resource for the RDS database.
- **DBSubnetGroup**: AWS RDS DBSubnetGroup resource for the database subnet group.
- **Secret**: AWS Secrets Manager Secret resource for storing the database password.

## Outputs

- **RDSInstanceIdentifier**: The identifier of the RDS instance created.

## Prerequisites

- An AWS account with appropriate permissions to create the required resources.
- Basic knowledge of AWS CloudFormation.

## Usage

### To deploy this CloudFormation template, follow these steps:

* Clone the repository: `git clone https://github.com/Jaylakhani37/AWS_CloudFormation_Templates.git`
* Navigate to the cloned repository: `cd AWS_CloudFormation_Templates/RDS`
* Deploy the template using the AWS CloudFormation Console, AWS CLI, or AWS SDKs.
* Provide the necessary parameters as required.
* Wait for the stack creation to complete.
* Once the stack creation is complete, you can access the created resources such as the RDS database instance. The outputs section of the CloudFormation stack will provide the necessary information, such as the RDS instance identifier, to access the resources.