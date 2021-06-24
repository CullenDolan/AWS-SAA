## VPC
VPC Endpoint
## Subnets
## Route Tables
## API Gateway
## Internet Gateway
## Security Group
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