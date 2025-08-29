Ques- Which resource automates the creation, retention, and deletion of Amazon Elastic Block Store (Amazon EBS) snapshots and AMIs backed by Amazon EBS?

`Amazon Data Lifecycle Manager` `Amazon S3 Intelligent Tiering` `AWS Config` `AWS Systems Manager`

Ans- `Amazon Data Lifecycle Manager (DLM)`

Explanation:
`Amazon Data Lifecycle Manager (DLM)` automates the creation, retention, and deletion of Amazon EBS snapshots and Amazon Machine Images (AMIs) backed by EBS.
`Amazon S3 Intelligent-Tiering` is for optimizing S3 storage costs by automatically moving objects between storage tiers.
`AWS Config` is used to track configuration changes of AWS resources.
`AWS Systems Manager` helps manage and automate operational tasks across AWS resources but not specifically EBS snapshot lifecycle automation.

Ques- Which AWS Pricing Calculator path can be used to generate an estimate for the Amazon EC2
instances with an hourly snapshot requirement?

`Quick`   `Express`  `Detailed`   `Advanced`

Ans-   `Advanced`

Explanation
The Advanced path in the AWS Pricing Calculator is used when you need to include additional configurations such as hourly snapshots, detailed storage requirements, or other specific usage parameters for Amazon EC2 instances.

Ques- What can be used to restrict access to specific Amazon EC2 instances? (Select TWO.)

`VPC route tables`  `VPC peering`  `Security groups`  `Private subnets`

Ans- 
`Security groups` – They act as virtual firewalls for your EC2 instances to control inbound and outbound traffic.
`Private subnets` – Placing instances in private subnets restricts direct internet access, limiting who can reach them.


Que- What should users do if their Amazon RDS queries seem to be running slowly?(Select THREE.)

`Enable enhanced monitoring on the database instance.`
`Review the slow query logs for MariaDB or MySQL.`
`Review the client-side SQL Server traces.`
`Modify the DB instance to run as a Multi-AZ deployment.`

Ans-  
`Enable enhanced monitoring on the database instance` – This helps you analyze resource usage and identify bottlenecks.
`Review the slow query logs for MariaDB or MySQL` – Helps in identifying inefficient queries causing delays.
`Review the client-side SQL Server traces` – Useful for SQL Server to detect problematic queries or delays.

Modifying the DB instance to run as a Multi-AZ deployment will improve availability and failover capability, but it will not directly improve query performance.


Que- Which functions does Amazon RDS perform on the behalf of users? (Select THREE.)

`Provision the infrastructure capacity.`
`Install the database software.`
`Automate data backups.`
`Create database users`

Ans:
`Provision the infrastructure capacity` – Amazon RDS provisions and manages the infrastructure for your database.
`Install the database software` – RDS installs and manages the database engine for you.
`Automate data backups` – RDS can automatically back up your database as per configured policies.

Creating database users is your responsibility as the database administrator, not RDS.


Que- What should users do if their Amazon RDS queries seem to be running slowly? (Select THREE.)

`Enable enhanced
monitoring on
the database
instance.`

`Review the slow
query logs for
MariaDB or
MySQL.`

`Review the
client-side SQL
Server traces.`

`Modify the DB
instance to run as
a Multi-AZ
deployment.`

ans-
Enable enhanced monitoring on the database instance.
Review the slow query logs for MariaDB or MySQL.
Review the client-side SQL Server traces.
