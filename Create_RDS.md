# Creating MySQL RDS

1. Create a DB Subnet Group
   ~~~
   aws rds create-db-subnet-group --db-subnet-group-name "mysqldbsubnetgroup"  --db-subnet-group-description "this is group created from cli" --subnet-ids "subnet-09fd8052ec8966091" "subnet-0989683895e0accf3" "subnet-055647ec6d17a0d85" --tags "Key=Name,Value=mysqlsubnetgroup"
   ~~~

2. Create a Security Group
   ~~~
   aws ec2 
   ~~~

3. Create Security Group Rules

4. Create a RDS DB
   ~~~
   aws rds create-db-instance --db-name "mysqlrds" --db-instance-identifier "sql-rds-cli" --allocated-storage 20 --db-instance-class db.t2.micro --engine mysql --master-username root --master-user-password root1234 --db-subnet-group-name mysqldbsubnetgroup --backup-retention-period 0 --publicly-accessible 
   ~~~


###Note: If you want to delete RDS 
   ~~~
   aws rds delete-db-instance --db-instance-identifier sql-rds-cli --skip-final-snapshot --delete-automated-backups
   ~~~
