# AMI Overview
Amazon Machine Image are a customization of an EC2 instance; you add your own software, configuration, operating system, monitoring. Results in faster boot / configuration time because all your software is pre-packaged. AMI are built for a specific region (And can be copied across regions).

You can launch EC2 instances from:
* A public AMI; AWS provided <br>
* Your own AMI; You make and maintain them yourself <br>
* An AWS marketplace AMI; An AMI someone else made (and potentially sells)

## AMI process
* Start an EC2 instance and customize it <br>
* Stop the instance (For data integrity) <br>
* Build an AMI; This will also create EBS snapshots <br>
* Launch instances from other AMIs