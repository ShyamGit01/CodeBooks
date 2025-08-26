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
