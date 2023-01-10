# rds-mysql-template

This project has a CloudFormation template which will create a MySQL- Version 8.0 RDS single instance.

As a precursor, a VPC with 3 private subnets 
Database will be created after that and it will be using the VPC and subnets for the same
RDS DB instance will be using the create VPC and subnet's, thereby ensuring that the RDS is secured internally.
A high level architecture diagram is shown below 

![image](https://user-images.githubusercontent.com/46040062/211634973-caecebda-3b43-4c84-aaaf-07348f55a6f0.png)


This set up is very useful for creating a Dev environment kind of database to configure and test applications.
To deploy all these services we can use aws cli. If "aws cli" is already configured in your system, please use below command to test the template creation yaml file

AWS CLI command to create the Database

aws cloudformation create-stack --stack-name POCDBStack --template-body file://AWS_VPC_RDS_MySQL_Template.yaml --parameters ParameterKey=MasterUserPassword,ParameterValue=password

The password has to be given as a parameter while creating the database. 
For the ParameterValue, we need to give our own password which will secured by the admin.

To delete the stack

aws cloudformation delete-stack --stack-name POCDBStack 

