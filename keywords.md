# High Performing
- network interface for clustered enviroments, high number of nodes > Elastic Fabric Adapter

# Resiliance
- Operational During Migration > AWS Database Migration Service
- Metric for scaling up/down queue > # of messages in SQS queue
- Storage volume snapshot once/day. He Transaction logs to S3 every 5 mins
- fully managed data store / MySQL & Postgres compatible
-  Disaster recovery for instances. AMI in another region
-  Data base migration compatibility issues > AWS Schema Conversion Tool
-  Collection of Logs OR Processing Logs > EMR
- Cloud formation drift not showing for certain values > Explicitly set property values (which can be same as default values)

# Secure
- Access to resources in private subnet > NAT Gateway
- -  Secure way for resources to access other resources > IAM Roles
-  Targeted access to coludfront content > Cloudfront origin w/ signed cookies
-  Fetch S3 files through CloudFront URL > Origin access identity
-  Social ienditity federation  (third party sign-in)> authenticate user with Federated identity provider and authorize user with Cognito
-  Real time threat detection > Kinesis
-  Federation (3rd sign in) works but access to resources doesnt > check IAM policies
-  KMS > Encryption at rest
-  Send traffic thru AWS resources > Enhanced VPC Routing
-  KMS in US-east-1 trying to use in EU-West-2 > KMS is region specific
-  Manage permissions in your organization > Service Control Policy
-  Access to resources for a limited time > Signed URLs
-  Share resources with different orgnaizations > Resource Access manager
-  Access to resources of files from a specific set of IPs Network or Object ACLs
-  Convert HTTP to HTTPs > "Viewer Protocol Policy of ..." = REdirect HTTP to HTTPS
-  Get IPSEC connectivity from on-prem to AWS >. AWS Site to Site VPN
-  

# Cost Optimized
- Savings Plans
  - you commit to a dollar amount per month within a specific family and AWS provides that
  - not dependent on a specific OS as long as the instances are in the same family
  - 
