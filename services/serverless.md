## Lambda
- Serverless compute to run code without managing servers
- Run by either uploading zip files, containers, or writing code in the console
- Has to be less than 15 minutes and file has to be less tha 3008 MB
- Cold starts can be an issue if you need very fast responses
- Don't run in a VPC by default so if using with RDS, they have to be in the same VPC as instance
- can scale to 1000 concurrent functions by default
- 1M request per month are free (at least for the first year)
