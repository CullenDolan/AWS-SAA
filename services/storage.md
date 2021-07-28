## Simple Storage Service (S3)
- Infinitely scalable storage solution with 99.99% availabilty and 11 9's of durability
- Standard, Intelligent-Tiering, Infrequent Access, Glacier, Glacier Deep Archive
- Object based storage (a file) from 0 - 5 TB in size
- made of a key (name of object), value (data w/in the file), version ID, metadata, access control lists, and policies
- strong read after write consistency **for all operations** on new objects (update happens immediately)
- eventual consistency for overwrite PUTS and DELETES (takes time to propogate)
- Life cycle management to move or delete objects
- if you delete an object thru CLI is will immediately delete
- S3 File Gateway: on-prem applications but storage in the cloud. good for low latency requirements
- with versioning enabled and an object is delete, the file is still in S3 but AWS pretends it is not there and returns a 404 error
- folders inside buckets can have different sotarge classes (eg folder 1 = standard and folder 2 = glacier)

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


| Volume Type | EBS Provisioned IOPS SSD (io2) | EBS Provisioned IOPS SSD (io1) | EBS General Purpose SSD (gp3) | EBS General Purpose SSD (gp2) |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| Short Description | High performance SSD volume designed for business-critical latency-sensitive applications | High performance SSD volume designed for latency-sensitive transactional workloads |General Purpose SSD volume that balances price performance for a wide variety of transactional workloads | General Purpose SSD volume that balances price performance for a wide variety of transactional workloads |
| Use Cases | I/O-intensive NoSQL & relational databases | I/O-intensive NoSQL & relational databases | virtual desktops, medium sized single instance databases such as MSFT SQL Server and Oracle DB, low-latency interactive apps, dev & test, boot volumes | Boot volumes, low-latency interactive apps, dev & test |
| Volume Size | 4 GB – 16 TB | 4 GB – 16 TB | 1 GB – 16 TB | 1 GB – 16 TB |
| Durability | 99.999% | 99.8% - 99.9% | 99.8% - 99.9% | 99.8% - 99.9% |
| Max IOPS*/Volume | 64,000 | 64,000 | 16,000 | 16,000 |
| Max Throughput**/Volume | 1,000 MB/s | 1,000 MB/s | 1,000 MB/s | 250 MB/s |
| Max IOPS/Instance | 160,000 | 260,000 | 260,000 | 260,000 |
| Max IOPS/GB | 500 IOPS/GB | 50 IOPS/GB | n/a | n/a |
| Max Throughput/Instance | 4,750 MB/s | 7,500 MB/s | 7,500 MB/s | 7,500 MB/s |
| Latency | single digit millisecond | single digit millisecond | single digit millisecond | single digit millisecond |

## Elastic File System (EFS)
- Allows you to share data w/o provsioning or managing storage
- stored across multiple AZs by default within 1 region
- creates moint points in all VPC subnets so you can mount from anywhere in the VPC
- provides read after write consistency

[Best Explanation Ever in the differences](https://stackoverflow.com/questions/29575877/aws-efs-vs-ebs-vs-s3-differences-when-to-use)

## IOPS vs Throughput
- IOPS is the number of read or write operations per second and device can perform
- Throughput is the number of bits read or written per second

## Amazon FSx for Lustre
- Fully managed service that provides high performance, scalable storage for compute workloads
- best for machine learning, HPC, and video rendering
- Can be linked to S3 buckets to access and process data directly

## Amazon FSx for Windows File Server
- fully managed, highly reliable, and scalable storage accessible over Server Message Block (SMB) protocol
- single or multi-AZ deployment options
- can span multple VPCs, regions, or accounts with VPN, VPC Peering, or AWS transit gateway

## Kinesis
- Real time streaming of data
- default is to store data for 24 hours
