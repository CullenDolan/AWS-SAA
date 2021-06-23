### SNS (Simple Notitification Services)
- Sends notifications by the publisher-subscriber methodology for anything that relies on real time events
- Asynchronous messaging done with push messages and no polling required
- Pay as you go, no upfront costs
- best example is to send time critical notifications to mobile apps

<img src="https://github.com/CullenDolan/AWS-SAA/blob/master/images/sns.png" alt="SNS" height="200" style="vertical-align:top; margin:100px">

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
- Can be batched up to 10 messages at a time or 256KB 
- Billed per request and a data transfer fee (in 64 KB chunks)
- If data is transferred in the same region
- Use **Long Polling** to extend poll request up to 20 seconds to reduce cost and maximize the chance of getting a message
- Can be used with SNS, REdshift, DynamDB, RDS, EC2, ECS, Lambda, and S3
