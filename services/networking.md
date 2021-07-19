## VPC
- locally isolated section to launch resources.
- region specific and connt span to another region, with 5 VPCs per region
- Defined by IP ranges, or **CIDR Blocks**, that cannot be changed after creation
- **VPC Peering** connects one VPC to another
- **VPC Endpoint** privately connect to AWS services w/o internet gateway

## NACL (Network Access Control List)
- Allows inbound/outbound trafic to a subnet
- once is automatically created w/ a VPC
- Virtual firewall at a subnet level
- You **can** block specific IP addresses

## Subnets
- different sections within a VPC to isolate resources further (publc & private subnets)
- split further by CIDR blocks

## NAT (Network Access Translation)
### NAT Gateway
- sits in a public subnet and allows resources in a private subnet access to the internet
- One NAT gateway per AZ
- Route tables have to be updated manually

### NAT Instance
- Legacy method created by launching an EC2 instance with a specific AMI
- Must be in public subnet

## Route Tables
- used to determine where traffic can be directed
- listed by CIDR block ranges
- Can allow traffic b/t subnets in a VPC, but everything is allowed by default
- Ther can be one route table but many subnets

## Elastic IP Address
- One is assigned to your AWS account to be able to route traffic to different instances if one fails
- Static and does not change over time
- 
## Internet Gateway
- VPC side of a connection to the internet
- like the highway to the rest of the world

## Security Group
- Firewall at the instance level
- all inbound is blocked by default unless specified
- all aoutboun dis allowed by ddefault unless specified
- You **cannot** block specific IP addresses with an SG, use a NACL
- EC2 can be in multiple SGs and SGs can contain multiple EC2s 

## Route53
## ELB
- Automatically distributes incoming traffic accross multiple targets
- Also known as a ***Reverse Proxy**
- Techniques can include"
    - Round Robin: distributes across servers sequentially
    - Least Connections: sent to server w/ fewest connections 
    - Hash: distributes request based on key you define (use client IP as the key to route traffic)
    - Least Time: sends request to server (fasted response time + fewest connections
    - IP Hash: IP address of client is used to determine which server gets the request
    - Random w/ Two Choices: picks 2 servers at random, then applies the least connection algoritm to route traffic
- Can be accessed w/o public IP b yusing a VPC Endpoint
- You cannot change load balancer types after one is deployed
- No ELBs can cross regions
### Application Load Balancer
- balance HTTP and HTTP requests. Good for modern apps, target is instances, lambda, or IP address
- you are required to have at least 2 AZs
- you can attach a Web Application Firewall (WAF) ti this type only
- charged per hour or partial hour the ALB is running and the number of Load Balncer Capacity Units (LCU) used per hour
### Network Load Balancer
- TCP, TLS, UDP. Good for ultra high performance. Targets like instances created inside instance group
- Also known as layer 4 listener
- charged per hour or partial hour the NLB is running and the number of Network Load Balncer Capacity Units (NLCU) used per hour
### Gateway Load Balancer
- scale out and deploy 3rd party appliances (security hardware) instance or IPs
- charged per hour or partial hour the GWLB is running and the number of Network Load Balncer Capacity Units (GLCU) used per hour and for the Gateway Load Balancer Endpoint (GWLBE)
### Classic Load Balancer
- HTTP(S) and TCP but this is legacy
- charged per hour or partial hour the CLB is running and each GB of data that passes thru the LB

## Elastic Network Interface
- Represents a virtual network card
- each network has a primary network interface
- 

## API Gateway
