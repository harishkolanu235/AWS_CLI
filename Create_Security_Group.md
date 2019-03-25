# Creating Security Group

1. Creating Security Group
   ~~~
   ec2 ec2 create-security-group --group-name MySecurityGroup --description "Creating Security Group For Webapp" --vpc-id vpc-0a04dbbb0b09ab041
   ~~~ 
   #### Note: Note down the Security Group ID: "sg-0332745dd0793883c"

2. Authorize-Security-group-ingress
   ~~~
   aws ec2 authorize-security-group-ingress --group-id sg-0332745dd0793883c --protocol tcp --port 22 --cidr 0.0.0.0/0

   aws ec2 authorize-security-group-ingress --group-id sg-0332745dd0793883c --protocol tcp --port 80 --cidr 0.0.0.0/0
   ~~~
