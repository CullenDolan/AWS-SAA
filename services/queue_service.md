### SQS (Simple Queue Services)
- Keyword: **Decouples** services
- Messages are stored on a queue until they are processed and deleted
- Standard Queue Features
    - "Unlimited" per second throughput
    - Delivery at least once, but could be delivered multiple times
    - No Guarunteed order 
-FIFO Queue Features
    - 300 send, receive, or delete messages per second
    - No duplicates and sits in the queue until consumer processes it
- Messages are kept for 14 days in the queue
- Can be batched up to 10 messages at a time or 256KB 
- Billed per request and a data transfer fee (in 64 KB chunks)
- If data is transferred to EC2 or Lambda in the same region, no data transfer costs
- Use **Long Polling** to extend poll request up to 20 seconds to reduce cost and maximize the chance of getting a message
- Can be used with SNS, Redshift, DynamDB, RDS, EC2, ECS, Lambda, and S3
- Standard queues cannot be converted to FIFO queues

### SNS (Simple Notitification Services)
- Sends notifications by the publisher-subscriber methodology for anything that relies on real time events
- Asynchronous messaging done with push messages and no polling required
- $0.50 per 1 million Amazon SNS Requests, $0.06 per 100,000 notification deliveries over HTTP, and $2.00 per 100,000 notification deliveries over email
- best example is to send time critical notifications to mobile apps
- can contain up to 256KB of data
<img src="https://github.com/CullenDolan/AWS-SAA/blob/master/images/sns.png" alt="SNS" height="200" style="vertical-align:top; margin:100px">


### SES (Simple Email Services)
