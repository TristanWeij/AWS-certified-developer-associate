# EC2 Instance Storage
An Elastic Block Store (EBS) Volume is a network drive you can attach to your instances while they run. It allows your instances to persist data, even after their termination. They can only be mounted to one instance at a time, they are bound to a specific availability zone

## EBS Volume
It's a network drive; It uses the network to communicate the instance, which means there might be a bit of latency. It can be detached from an EC2 instance and attached to another one quickly.

It's locked to an availability zone;
* An EBS Volume in us-east-1a cannot be attached to us-east-1b <br>
* To move a volume across, you first need to snapshot it.

Have a provisioned capacity (Size in GBs, and IOPS)
* You get billed for all the provisioned capacity <br>
* You can increase the capacity of the drive over time

### EBS; Delete on termination attribute
Controls the EBS behaviour when an EC2 instance terminates. By default, the root EBS volume is deleted. By default, any other attached EBS volume is not deleted. This can be controlled by the AWS console / AWS CLI. Use case: Preserve root volume when instance is terminated.

## EBS Snapshots
Make a backup (snapshot) of your EBS volume at a point in time. Not necessary to detach volume to do snapshot, but recommended. Can copy snapshots across AZ or region

## EC2 Instance Store
EBS volumes are network drives with good but limited performance. If you need a high-performance hardware disk, use EC2 instance store:
* Better I/O performance <br>
* EC2 Instance Store lose their storage if they're stopped (Ephemeral) <br>
* Good for buffer / cache / scratch data / temporary content <br>
* Risk of data loss if hardware fails <br>
* Backups and replication are your responsibility

## EBS Multi-Attach - io1/io2 family
Attach the same EBS volume to multiple EC2 instances in the same AZ. Each instance has full read & write permissions to the volume:
* Achieve higher availability in clustered Linux applications (ex: Teradata) <br>
* Applications must manage concurrent write operations

Must use a file system that's cluster aware (not XFS, EX4, etc)
