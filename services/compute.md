# Elastic Cloud Compute (EC2)

## Instance Types
- **Genereal Purpose** (t, m, A, Mac): balance of compute and networking. Best for basic use cases such as web servers. the t instances are busrtable meaning they sit at a baseline of CPU utilization and accrue credits to burst higher when they are under the limit. If they burst and use up all credits, they will drop back to a minimum threshold. Credits will erase if instance is paused.
- **Compute Optimized** (C): best for compute intensive workloads such as batch processing, high traffic web servers, etc. 
- **Memory Optimized** (R, X, z): best for workloads that process large datasets in memory. Open source databases, in-memory caching, and real time big data analytics
- **Accelerated Computing** (P, G, F, Inf): GPU processing for deep learning, floating point number operations. 
- **Storage Optimized** (I, G, H): requires high sequential read/write acces to large data set on local storage. 10,000s I/O operations / second. Use cases such as NoSQL database

## Storage Options
### [EBS](https://github.com/CullenDolan/AWS-SAA/blob/master/services/storage.md#elastic-block-storage-ebs)
- easy to use virtual hard disk
- EBS persists independently from the EC2 instance
- Once it is attached, it can be used like any other physical hard disk
- General purpose, provisioned IOPS, and Magnetic

### Instance Store
- Hard disk is physicially attached to the processor
- Only persisted while the EC2 is running

### Performance Testing
1. Assess the requirements of your application
2. Identify how your application needs to compare to different instance families (compute, memory. general, etc)
3. Select the instance family
4. Size the workload
5. Test at and application level (but AWS would say this so start maller and size up, in my opinion)
