## Elastic Compute Cloud (EC2) Instance Types
You can use different types of EC2 instances that are optimised for different use cases. <br>
AWS has the following naming convention:
* m5.2xlarge
    * m: instance class
    * 5: generation (AWS improves them over time)
    * 2xlarge: size within the instance class

## Example

| Instance    | vCPU | Memory (GiB) | Storage          | Network performance | EBS bandwidth |
| ----------- | ---- | ------------ | ---------------- | ------------------- | ------------- |
| t2.micro    | 1    | 1            | EBS-only         | Low to moderate     | /             |
| t2.xlarge   | 4    | 16           | EBS-only         | Moderate            | /             |
| c5d.4xlarge | 16   | 32           | 1 x 400 NVMe SSD | Up to 10 Gbps       | 4750          |
| r5.16xlarge | 64   | 512          | EBS-only         | 20 Gbps             | 13600         |
| m5.8xlarge  | 32   | 128          | EBS-only         | 10 Gbps             | 6800          |

## EC2 Instance Types (General Purpose)
Great for a diversity of workloads such as web servers or code repositories. Balance between:
* Compute <br>
* Memory <br>
* Networking

### EC2 Instance Types (Compute Optimized)
Great for compute-intensive tasks that require high performance processors:
* Batch processing workloads <br>
* Media transcoding <br>
* High performance web servers <br>
* High performance computing (HPC) <br>
* Scientific modeling & machine learning <br>
* Dedicated gaming servers <br>

### EC2 Instance Types (Memory Optimized)
Fast performance for workloads that process large data sets in memory:
* High performance, relational/non-relational databases <br>
* Distributed web scale cache stores <br>
* In-memory databases optimized for business intelligence <br>
* Applications performing real-time processing of big unstructured data

### EC2 Instance Types (Storage Optimized)
Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage:
* High frequency online transaction processing (OLTP) systems <br>
* Relational & NoSQL database <br>
* Cache for in-memory databases <br>
* Data warehousing applications <br>
* Distributed file systems
