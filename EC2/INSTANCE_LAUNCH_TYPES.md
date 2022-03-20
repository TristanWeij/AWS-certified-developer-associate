# Elastic Compute Cloud (EC2) Instances Purchasing Options
* On-Demand Instances; Short workload, predictable pricing <br>
* Reserved Instances; Minimum 1 year.
    * Reserved Instances; Long workloads.
    * Convertible Reserved Instances; Long workloads with flexible instances.
    * Scheduled Reserved Instances (Deprecated); Every thursday between 3 and 6 pm.
* Spot Instances; Short workloads, cheap, can lose instances (less reliable) <br>
* Dedicated Hosts; Book an entire physical server, control instance placement

## On-Demand Instances
Pay for what you use:
* Linux or Windows; Billing per second, after the first minute <br>
* All other operating systems; Billing per hour <br>

Has the highest cost, but no upfront payment, no long-term commitment. <br>
Recommended for short-term and un-interrupted workloads, where you can't predict how the application will behave.

## Reserved Instances
Up to 75% discount compared to On-Demand Instances:
* Reservation period:
    * 1 Year (= + discount)
    * 3 Years (= +++ discount)
* Purchasing options:
    * Partial upfront (= + discount)
    * All upfront (= ++ discount)
* Reserve a specific instance type <br>
* Recommended for steady-state usage applications (think database)

Reserved instance types:
* Convertible Reserved Instance
    * Can change the EC2 instance type
    * Up to 54% discount
* Scheduled Reserved Instances (deprecated)
    * Launch within ttime window you reserve
    * When you require a fraction of day / week / month
    * Still commitment over 1 to 3 years

## Spot Instances
Can get a discount of up to 90% compared to On-Demand. Instances that you can lose at any point of time if your max price is less than the current spot price. The most cost-efficient instances in AWS.
* Useful for workloads that are resilient to failure
    * Batch jobs
    * Data analysis
    * Image processing
    * Any distributed workloads
    * Workloads with a flexible start and end time
* Not suitable for critical jobs or databases

## Dedicated Hosts
An Amazon EC2 Dedicated Host is a physical server with EC2 instance capacity fully dedicated to your use. Dedicated Hosts can help you address compliance requirements and reduce costs by allowing you to use your existing server-bound software licenses.

Allocated for your account for a 3-year period reservation, more expensive. <br>
Useful for software that have complicated licensing model (Bring Your Own License), or for companies that have strong regulatory or compliance needs.

## Dedicated Instances
Instances running on hardware that's dedicated to you, may share hardware with other instances in same account. No control over instance placement
