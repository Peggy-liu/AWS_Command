# Connect to an EC2 linux instance using SSH client
## change the access mode of the private key file: the pem file
$chmod 400 mykey.pem

## connect
$ssh -i "mykey.pem" ec2-user@[public ip DNS/address]

# Install http server on the EC2 instance
**Remember to expose port 80 in the inbound rules of the security group of the EC2 instance**
## install http server
$sudo yum install httpd -y
## start the server
$sudo service httpd start
## Add a welcome page for the web server
$sudo vi /var/www/html/index.html

# find out configuration of the security groups in amazon
## Step 1: manually create security groups and rules a through amazon user console
## Step 2: copy the security group ID, and run command AWSCLI in terminal:
$aws ec2 describe-security-groups --group-ids [security-group-id]

