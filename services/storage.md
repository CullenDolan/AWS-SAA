## Simple Storage Service (S3)
- Infinitely scalable storage solution 

## Elastic Block Storage (EBS) 
- easy to use block storage for EC2 (virtual hard disk)
- the data for your database is stored on EBS and your boot volume (the server OS). This is what you change depending on how much data you store in the db
- There are 2 categories and 6 types on volumes:
    - SSD (General Purpose and Provisioned IOPS)
        - gp3: best for balancing price and performance (virtual desktop, medium sized single instance db)
        - gp2: default setting, not as good as gp3, 3 IOPS/GB
        - io2: designed for high I/O applications (No-SQL dbs) 
        - io1: similar but lower durability

    - HHD 
        - st1: Throughput optimized, good for big data and data warehousing
        - sc1: Cold storage, lowest cost per GB. Anything requiring fewer scans per day
- EBS snapshots provide a backup for your data. Good for Disaster Recovery (DR), migration, compliance
- You can take a snapshot while the instance is running but...
- Stop the instance before taking snapshot of the root volume
- AMIs can be created with the volume or snapshot
- **Instance Store Volumes** are temporary storage volumes, physically accted to the host device. They can't be stopped and if the host fails the data is lost.
- EBS backed instances can be stopped 
## Elastic File System (EFS)
- Allows you to share data w/o provsioning or managing storage
- stored across multiple AZs by default within 1 region
- creates moint points in all VPC subnets so you can mount from anywhere in the VPC
- provides read after write consistency

[Best Explanation Ever in the differences](https://stackoverflow.com/questions/29575877/aws-efs-vs-ebs-vs-s3-differences-when-to-use)
