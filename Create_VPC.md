# Creating VPC with CLI

1. Creating a VPC

   ~~~sh
   aws ec2 create-vpc  --cidr-block 10.10.0.0/16
   ~~~
      #### Note: Note down the VPC ID: "vpc-0a04dbbb0b09ab041"

2. Creating a Subnet
   I want to create 3 subnets

   ~~~sh
   aws ec2 create-subnet --cidr-block 10.10.1.0/24 --availability-zone us-east-2a --vpc-id vpc-0a04dbbb0b09ab041

   aws ec2 create-subnet --cidr-block 10.10.2.0/24 --availability-zone us-east-2b --vpc-id vpc-0a04dbbb0b09ab041

   aws ec2 create-subnet --cidr-block 10.10.3.0/24 --availability-zone us-east-2c --vpc-id vpc-0a04dbbb0b09ab041
   ~~~   
   #### Note: Note down the subnets IDs
   "subnet-09fd8052ec8966091"
   "subnet-0989683895e0accf3"
   "subnet-055647ec6d17a0d85"

3. Create IGW and attach to VPC 
   ~~~sh
   aws ec2 create-internet-gateway 
   ~~~
   #### Note: Note down the IGW Id: "igw-09fedd5a556bd2ed5"
   ~~~sh
   aws ec2 attach-internet-gateway --internet-gateway-id igw-09fedd5a556bd2ed5 --vpc-id vpc-0a04dbbb0b09ab041
   ~~~

4. Create Route Table and add subnet to it
   ~~~sh
   aws ec2 create-route-table --vpc-id vpc-0a04dbbb0b09ab041 
   ~~~
   #### Note: Route Table Id: "rtb-09db61346e72e9467"

5. Create a Route towards IGW for Route Table
   ~~~sh
   aws ec2 create-route --route-table-id rtb-09db61346e72e9467 --gateway-id igw-09fedd5a556bd2ed5 --destination-cidr-block 0.0.0.0/0
   ~~~

6. Associate Route Table to Subnets
   ~~~sh
   aws ec2 associate-route-table --route-table-id rtb-09db61346e72e9467 --subnet-id subnet-09fd8052ec8966091

   aws ec2 associate-route-table --route-table-id rtb-09db61346e72e9467 --subnet-id subnet-0989683895e0accf3

   aws ec2 associate-route-table --route-table-id rtb-09db61346e72e9467 --subnet-id subnet-055647ec6d17a0d85 
   ~~~ 
   #### Note: note down the three AssociationID
      "rtbassoc-064c9e7373181edca"
      "rtbassoc-0750e85e619085dd6"
      "rtbassoc-0c809f933c777e161"