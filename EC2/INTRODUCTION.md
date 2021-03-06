# Elastic Compute Cloud (EC2) Introduction
Infrastructure as a service (IaaS), it mainly consists in the capability of:
* Renting virtual machines (EC2) <br>
* Storing data on virtual drives (EBS) <br>
* Distributing load across machines (ELB) <br>
* Scaling the services using an auto-scaling group (ASG)

## Sizing & configuration options
* Operating system:
    * Linux
    * Windows
    * Mac OS
* How much compute power & cores (CPU) <br>
* How much random-access memory (RAM) <br>
* How much storage space:
    * Network-attached (EBS & EFS) <br>
    * Hardware (EC2 Instance store)
* Network card: Speed of the card, public IP address <br>
* Firewall rules: Security group <br>
* Bootstrap script (configure at first launch): EC2 User data

## EC2 User Data
It is possible to bootstrap our instances using an EC2 User Data script. <br>
Bootstrapping means launching commands when a machine starts; that script is only run once at the instance first start. EC2 User data is used to automate boot tasks such as:
* Installing updates <br>
* Installing software <br>
* Downloading common files from the internet <br>
* Anything you can think of

The EC2 User Data script runs with the root user