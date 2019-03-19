# Creating VPC with CLI

Step 1: Creating a VPC

~~~
aws ec2 create-vpc  --cidr-block 10.10.0.0/16

~~~

Step 2: Creating a Subnet
i want to create 3 subnets

~~~
aws ec2 create-subnet --cidr-block 10.10.1.0/24 --availability-zone us-east2-a --vpc-id vpc-0a04dbbb0b09ab041

aws ec2 create-subnet --cidr-block 10.10.2.0/24 --availability-zone us-east2-b --vpc-id vpc-0a04dbbb0b09ab041

aws ec2 create-subnet --cidr-block 10.10.3.0/24 --availability-zone us-east2-c --vpc-id vpc-0a04dbbb0b09ab041
~~~
