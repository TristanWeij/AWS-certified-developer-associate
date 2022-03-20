# Elastic Compute Cloud (EC2) Security Groups
Security groups are the fundamental of network security in AWS.They control how traffic is allowed into or out of our EC2 instances:
* Security groups only contain allow rules <br>
* Security groups rules can reference by IP or by security group <br>

Security groups are acting as a firewall on EC2 instances, they regulate:
* Access to ports <br>
* Authorised IP ranges - IPv4 and IPv6 <br>
* Control of inbound network (from other to the instance) <br>
* Control of outbound network (from the instance to other)

## Good to know
* Can be attached to multiple instance <br>
* Locked down to a region / VPC combination <br>
* Does live outside of the EC2 instance; if traffic is blocked the instance won't see it <br>
* It's good to maintain one separate security group for SSH access <br>
* If your application is not accessible (time out), then it's a security group issue <br>
* If your application gives a "connection refused" error, then it's an application error or it's not launched <br>
* All inbound traffic is blocked by default <br>
* All outbound traffic is authorised by default

## Classic ports to know
* 22 = SSH (Secure Shell); Log into a Linux instance <br>
* 21 = FTP (File Transfer Protocol); Upload files into a file share <br>
* 22 = SFTP (Secure File Transfer Protocol); Upload files using SSH <br>
* 80 = HTTP (Hypertext Transfer Protocol); Access unsecured websites <br>
* 443 = HTTPS (Hypertext Transfer Protocol Secure); Access secured websites <br>
* 3389 = RDP (Remote Desktop Protocol); Log into a Windows instance