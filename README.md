# Aws_Infrastruture-Terraform
This code is written in terraform to setup an infrastructure in aws

## Prerequesties:

- For creating an AWS infrastructure I have used my IAM account with programmatic access 
(Login credentials are given in 'provider.tf' file)

## Steps used in this code for creating the AWS Infrasturcture
1) First it will create a new VPC in aws and one public subnet and one private subnet using the new VPC. 
2) Creating an Internet gateway which will be assigned to the public subnet and a Nat gateway which will be assigned to the private subnet.
3) Create an elastic IP for the nat gateway and associate it with the created nat gateway. 
4) Then create 2 ec2 instance. First one will be the webserver which will be created under the public subnet.
5) The next one will be database server which will create under private subnet. So that these two instances can communicate each other but no other servers can communicate with the database from outside since there won't be any public IP assigned to the database server.
Webserver can communicate with the Database server using the private IP
