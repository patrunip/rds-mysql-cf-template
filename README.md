# rds-mysql-template

This project has a CloudFormation template which will create a MySQL- Version 8.0 RDS single instance.
As a precursor, a VPC with 3 private subnets will be created and post that the database will be created. 
RDS DB instance will be using the create VPC and subnet's, thereby ensuring that the RDS is secured internally.

To deploy all these services we can use aws cli. If "aws cli" is already configured in your system, please use below command to test the template creation yaml file

aws cloudformation create-stack --stack-name POCDBStack --template-body file://AWS_VPC_RDS_MySQL_Template.yaml --parameters ParameterKey=MasterUserPassword,ParameterValue=password

For the ParameterValue, we need to give our own password which will secured by the admin.

To delete the stack

aws cloudformation delete-stack --stack-name POCDBStack 
