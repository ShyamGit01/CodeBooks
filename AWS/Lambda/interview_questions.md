# 🧠 AWS Lambda Interview Questions & Answers

### 1. What is AWS Lambda?
AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers. You just write the code, upload it, and AWS takes care of the infrastructure.

### 2. What languages does AWS Lambda support?
- Node.js
- Python
- Java
- Go
- .NET (C#)
- Ruby
- Custom runtimes via Lambda Runtime API

### 3. What is the maximum timeout limit for an AWS Lambda function?
**15 minutes (900 seconds).**

### 4. Can Lambda run background tasks or long-running processes?
Lambda is not ideal for tasks exceeding 15 minutes. For long-running jobs:
- Use **Step Functions**
- Or offload to **ECS/Fargate/EC2**

---

### 5. How can a Lambda function be triggered?
- API Gateway
- S3
- DynamoDB Streams
- EventBridge / CloudWatch Events
- SQS, SNS, Kinesis
- Cognito, IoT, Lex, Alexa

### 6. What is the default memory and timeout for a Lambda?
- **Memory**: 128 MB
- **Timeout**: 3 seconds  
(Can increase up to 10 GB memory and 15 min timeout)

### 7. How does Lambda scale?
Lambda scales **automatically** by running multiple isolated instances in parallel based on incoming requests.

### 8. Can you attach EFS to Lambda?
Yes. AWS Lambda can mount **Amazon EFS** to share files or load large dependencies.

### 9. What is a cold start?
A **cold start** happens when a new Lambda container is initialized, adding latency. It occurs when:
- The function hasn’t been used in a while
- New concurrency demand is triggered

### 10. What is provisioned concurrency?
**Provisioned concurrency** keeps a number of Lambda instances pre-warmed to avoid cold starts.

### 11. What are cold starts and how can they be mitigated?
- A **cold start** happens when AWS provisions a new container to serve a function after idle time.
- Causes: new deployment, increase in traffic, no recent invocations
- Mitigations:
  - **Provisioned Concurrency**
  - Keep-alive pings
  - Keep memory allocation higher (improves startup)

### 12. How does AWS Lambda handle scaling?
- Lambda scales **automatically** per request
- Each new request gets a new container (if existing ones are busy)
- There are account-level limits on concurrent executions

### 15. How would you handle a Lambda that takes more than 15 minutes?
 - Lambda max timeout: 15 minutes
 - Use Step Functions to break the task into smaller steps
 - Or use ECS/Fargate for long-running tasks

---

### 11. How can you deploy Lambda functions?
- AWS Console
- AWS CLI / SDK
- CI/CD (GitHub Actions, CodePipeline, etc.)
- Serverless Framework
- AWS SAM (Serverless Application Model)

### 12. How do you manage dependencies in Lambda?
- Include `node_modules` in ZIP
- Use **Layers** for common dependencies
- Use EFS for very large or binary dependencies

### 13. What is a Lambda Layer?
A **Layer** is a ZIP archive of libraries or custom code shared across multiple Lambda functions.

---

### 14. What IAM permissions are required to run a Lambda?
Lambda needs:
- Execution role to access AWS services
- `logs:*` permissions for CloudWatch logging

Example:
```json
{
  "Effect": "Allow",
  "Action": ["logs:*", "s3:*"],
  "Resource": "*"
}
```

### 15. Can Lambda access private VPC resources?
Yes. AWS Lambda can be configured to access private resources in a **VPC** such as RDS databases, EC2 instances, etc. You need to:
- Attach the Lambda to a VPC
- Provide appropriate **subnets** and **security groups**

### 10. How do you ensure a Lambda function only connects to specific VPC resources?
 - Attach Lambda to a VPC with:
    - Subnets (preferably private)
    - Security groups (least-privileged)
 - Ensure NAT Gateway for outbound traffic (if needed)

### 16. How do you monitor Lambda functions?
You can monitor Lambda using:
- **Amazon CloudWatch Logs**: Automatically stores logs via `console.log`, `print`, etc.
- **Amazon CloudWatch Metrics**: Tracks invocations, errors, duration, throttles, etc.
- **AWS X-Ray**: Provides distributed tracing and performance visualization.

### 17. How do you handle errors in Lambda?
- Use `try-catch` blocks in code to capture errors
- Return structured error responses (especially with API Gateway)
- Use **Dead Letter Queue (DLQ)** with SQS/SNS for failed async executions
- Apply **retry strategies** for asynchronous Lambda invocations

### 8. How do you process SQS messages with Lambda?
- Attach Lambda as a trigger to an SQS queue
- Lambda polls messages in batches (max 10)
- Failed messages can be routed to DLQ (Dead Letter Queue)

### 12. How to debug Lambda locally?
- Use AWS SAM CLI or Serverless Framework to simulate Lambda environment
- Tools: sam local invoke, serverless invoke local

---

### 18. What are concurrency limits in Lambda?
- **Default concurrent execution limit**: 1,000 per region (can be increased)
- **Reserved concurrency**: Guarantees execution capacity for critical functions
- **Provisioned concurrency**: Keeps functions pre-warmed to avoid cold starts


### 19. What’s the difference between synchronous and asynchronous Lambda invocations?

| Type         | Examples                | Behavior                         |
|--------------|-------------------------|----------------------------------|
| Synchronous  | API Gateway, SDK calls  | Caller waits for result          |
| Asynchronous | S3, EventBridge, SNS    | Lambda queues the request, retries if needed |


### 20. How do you handle large payloads in Lambda?
Lambda has payload size limits:
- **6 MB** for synchronous invocations
- **256 KB** for asynchronous events

To handle large payloads:
- Store data in **Amazon S3**
- Pass the S3 URI or reference in the event


### 21. How does AWS Lambda work under the hood?
- Lambda creates an **execution environment** (a lightweight container).
- For each request, it checks if a container is warm (reused) or needs a cold start.
- The code runs in an isolated environment with its own CPU, memory, storage, and runtime.

### 22. What is the `/tmp` directory in Lambda?
- Lambda functions get 512 MB of **ephemeral disk space** in `/tmp`
- Use it for temporary caching or file manipulation during a single invocation

### 17. How do you reduce the size of Lambda deployment package?
 - Use Layers
 - Use webpack or esbuild for bundling
 - Avoid including unnecessary node_modules

### 12. What is reserved concurrency in Lambda?
 - Limits the number of concurrent executions for a specific function
 - Prevents it from consuming all available concurrency of the account

### 20. How can you test Lambda functions?
 - Unit testing using frameworks like Jest or Mocha
 - Integration testing using SAM CLI or Test Events in AWS Console

### 21. How do you secure environment variables in Lambda?
 - Encrypted at rest using KMS
 - Use Secrets Manager or SSM Parameter Store for sensitive data

### 22. How does Lambda billing work?
 - Charged based on:
   - Number of invocations
   - Duration (in ms)
   - Memory allocated
- First 1M invocations and 400,000 GB-seconds are free each month

### 23. How do you use Lambda with DynamoDB Streams?
 - Enable DynamoDB Stream on a table
 - Attach Lambda to stream
 - Lambda gets triggered on table changes (INSERT, MODIFY, REMOVE)

### 24. What is the difference between Runtime and Handler in Lambda?
 - Runtime: The environment where your function runs (e.g., Node.js 18.x)
 - Handler: Entry point for the function (index.handler = index.js and exports.handler)

### 25. Write Your Lambda Function (index.js)
```
exports.handler = async (event) => {
  console.log("Event Received:", event);

  return {
    statusCode: 200,
    body: JSON.stringify({ message: "Hello from Lambda!" }),
  };
};

```

### 26. Test It Locally (Optional)
 - Option A: Simple Local Test File
    ```
const { handler } = require("./index");

const mockEvent = {
  key1: "value1",
};

handler(mockEvent).then(response => {
  console.log("Lambda Response:", response);
});

```
 - Option B: Using AWS SAM (Advanced Local Testing)
Install SAM CLI and use `sam local invoke` for realistic AWS emulation.
