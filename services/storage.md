## Simple Storage Service (S3)
- Infinitely scalable storage solution 

## Elastic Block Storage (EBS) 
- easy to use block storage for EC2 (virtual hard disk)
- the data for your datbase is stored on EBS and your boot volume (the server OS). This is what you change depending on how much data you store in the db
- EBS snapshots provide a backup for your data. Good for Disaster Recovery (DR), migration, compliance
- There are 2 categories and 6 types on volumes:
    - SSD (General Purpose and Provisioned IOPS)
        
        - gp3: best for balancing price and performance (virtual desktop, medium sized single instance db)
        - gp2: default setting, not as good as gp3, 3 IOPS/GB
        - io2: designed for high I/O applications (No-SQL dbs) 
        - io1: similar but lower durability

    - HHD 
        - st1: Throughput optimized, good for big data and data warehousing
        - sc1: Cold storage, lowest cost per GB. Anything requiring fewer scans per day

## EFS