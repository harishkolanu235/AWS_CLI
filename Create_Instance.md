# Creating Instance

1. Creating Instance
   ~~~
   aws ec2 --run-instance --image-id ami-0a313d6098716f372 --instance-type t2.micro --key-name ohio --security --security-group-ids "sg-0332745dd0793883c" --subnet-id  subnet-09fd8052ec8966091 --associate-public-ip-address --count 1
   ~~~
   #### Note: Note down the Instance ID: "i-023c6bde8eb7f65f7" 