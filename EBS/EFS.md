# Elastic File System (EFS)
Managed network file system (NFS) that can be mounted on many EC2 instances. EFS works with EC2 instances in multi-AZ;
* Highly available <br>
* Highly scalable <br>
* Expensive (3x gp2) <br>
* Pay-per-use

Uses NFSv4.1 protocol. Uses security group to control access to EFS. Compatible with Linux based AMI (not Windows). Encryption at rest using KMS.

POSIX file system (~Linux) that has a standard file API. File system scales automatically, pay-per-use, no capacity planning

## Use cases
* Content management <br>
* Web serving <br>
* Data sharing <br>
* WordPress

## EFS Performance & storage classes
* EFS scale:
    * 1000s of concurrent NFS clients, 10GB+ /s throughput
    * Grow to Petabyte-scale network file system, automatically
* Performance mode (Set at EFS creation time)
    * General purpose (default): Latency-sensitive use cases (Web server, CMS)
    * MAX I/O: Higher latency, throughput, highly parallel (Big data, media processing)
* Throughput mode
    * Bursting (1TB = 50MiB/s + burst of up to 100MiB/s)
    * Provisioned: Set your throughput regardless of storage size, ex: 1 GiB/s for 1TB storage
* Storage tiers (lifecycle management feature; Move file after N days)
    * Standard: for frequently accessed files
    * Infrequent access: (EFS-IA); cost to retrieve files, lower price to store

## EBS vs EFS - Elastic Block Storage
* EBS volumes:
    * Can be attached to only one instance at a time <br>
    * Are locked at the availability zone <br>
    * gp2: I/O increases if the disk size increases <br>
    * io1: Can increase I/O independently
* To migrate an EBS volume across AZ
    * Take a snapshot
    * Restore the snapshot to another AZ
    * EBS backups use I/O and you shouldn't run them while your application is handling a lot of traffic
* Root EBS volumes of instances get terminated by default if the EC2 instance gets terminated (you can disable that)

* EFS:
    * Mounting 100s of instances across AZ
    * EFS share website files (WordPress)
    * Only for Linux instances (POSIX)
* EFS has a higher price point than EBS
* Can leverage EFS-IA for cost savings
