# AWS Lamda 

- AWS Lambda is a serverless, event-driven compute service provided by Amazon Web Services (AWS) that allows you to run code for applications or backend services without provisioning or managing physical or virtual servers. It automatically handles the underlying compute infrastructure, patch management, and auto-scaling from zero to thousands of concurrent requests.

- https://aws.amazon.com/lambda/
- https://aws.amazon.com/about-aws/whats-new/2025/08/aws-lambda-github-actions-function-deployment/
- https://docs.aws.amazon.com/lambda/latest/dg/deploying-github-actions.html
- https://docs.aws.amazon.com/lambda/
- https://docs.aws.amazon.com/lambda/
- https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html
- https://aws.amazon.com/blogs/aws/run-code-cloud/
- https://github.com/aws/aws-lambda-go
- https://github.com/awsdocs/aws-lambda-developer-guide
- https://github.com/aws/aws-lambda-dotnet
- https://github.com/marketplace/actions/aws-lambda-deploy
- https://github.com/marketplace/actions/invoke-aws-lambda
- https://github.com/aws/aws-lambda-builders

---

## How AWS Lambda Works
### Lambda operates on an Event-Driven Model which consists of three interconnected steps:
- The Trigger (Event Source): An event occurs within the cloud architecture.
- This could be a file uploaded to Amazon S3, a data record modified in Amazon DynamoDB, or an HTTP request routed through Amazon API Gateway.
- The Lambda Function: AWS spins up an isolated Firecracker micro-VM to execute the code you wrote. This code processes the incoming event object.
- The Destination (Downstream Service): The function performs its logic and passes the output downstream, such as updating a database, sending a notification, or delivering an HTTP response.
- [ Event Source / Trigger ] ──> [ AWS Lambda Function ] ──> [ Downstream Service / Output ]
(e.g., S3 Upload, API Call)     (Executes Code in Micro-VM)     (e.g., Save to DB, Send Email)

---

## Common Use CasesFile Processing: 

- Generating automated thumbnails or scanning attachments for malware immediately after they land in an storage bucket.
- Web Backends: Powering REST or GraphQL APIs dynamically without running dedicated server instances 24/7.
- Real-time Stream Processing: Filtering, transforming, and formatting high-volume data streams coming from Amazon Kinesis or Apache Kafka.
- Automation & Cron Jobs: Running scheduled maintenance scripts, database backups, or report generation via Amazon EventBridge triggers.

---

## Core Features & Technical Limits
- Supported Languages: Native support includes Python, Node.js, Java, Go, Ruby, C#, and PowerShell. It also offers a Runtime API to support custom languages like Rust or C++.
- Execution Limits: A single standard function execution can last for a maximum duration of 15 minutes.
- Memory Allocation: You can allocate memory ranging from 128 MB to 10,240 MB (10 GB). CPU power scales proportionally with the allocated memory.
- Pricing Model: You only pay for what you use. Billing is calculated based on the total number of Requests and the exact Duration of execution measured in milliseconds. It features a permanent free tier that includes 1 million requests and 400,000 GB-seconds of compute time per month.

## Key Features & Benefits
- Zero Server Management: AWS automatically handles underlying operating system updates, hardware provisioning, and security patches
- Automatic Elastic Scaling: Lambda scales seamlessly from handling a single request per day to tens of thousands of concurrent executions per second.
- True Pay-Per-Use Pricing: You are billed strictly for the number of requests and the execution duration measured in milliseconds. When your code is idle, you pay absolutely nothing.

## Common Limitations
- 15-Minute Timeout: A single function execution cannot run longer than 15 minutes, making it unsuitable for massive, long-running monolithic tasks.
- Cold Starts: If a function has not been called recently, there can be a slight delay (milliseconds to a few seconds) while AWS initializes a new container instance.
- Ephemeral Storage: Default execution environments have a limited scratch space (/tmp directory) ranging from 512 MB to 10 GB.

<img width="1270" height="732" alt="image" src="https://github.com/user-attachments/assets/90166259-3aa5-4af0-957a-a5001bc4bf5f" />

---


  
  
