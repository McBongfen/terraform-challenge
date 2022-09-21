Scenario

A company is looking to create a proof-of-concept environment in AWS.  They want a simple VPC as outlined below.  The company would also like to use Terraform to manage their infrastructure via code.

1 VPC – 10.1.0.0/16

4 subnets (spread evenly across two availability zones)
Sub1 – 10.1.0.0/24 (should be accessible from internet)
Sub2 – 10.1.1.0/24 (should be accessible from internet)
Sub3 – 10.1.2.0/24 (should NOT be accessible from internet)
Sub4 – 10.1.3.0/24 (should NOT be accessible from internet)

1 EC2 instance running Red Hat Linux in subnet sub2
20 GB storage
t2.micro

1 auto scaling group (ASG) that will spread out instances across subnets sub3 and sub4 
Use Red Hat Linux
20 GB storage
Script the installation of Apache web server (httpd) on these instances
2 minimum, 6 maximum hosts
t2.micro

1 application load balancer (ALB) that listens on TCP port 80 (HTTP) and forwards traffic to the ASG in subnets sub3 and sub4
Security groups should be used to allow necessary traffic

1 S3 bucket with two folders and the following lifecycle policies
“Images” folder - move objects older than 90 days to glacier
“Logs” folder - delete objects older than 90 days







