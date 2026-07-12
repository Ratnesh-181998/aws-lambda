# AWS Lambda
AWS Lambda is a serverless, event-driven compute service provided by Amazon Web Services (AWS) that lets you run code for virtually any application or backend service without provisioning or managing servers. You simply upload your code, and Lambda automatically handles the compute capacity, scaling, operating system patching, and monitoring

- https://aws.amazon.com/lambda/
- https://docs.aws.amazon.com/lambda/latest/dg/welcome.html
- https://docs.aws.amazon.com/lambda/
- https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html
- https://docs.aws.amazon.com/lambda/latest/dg/deploying-github-actions.html
- https://aws.amazon.com/about-aws/whats-new/2025/08/aws-lambda-github-actions-function-deployment/
- https://github.com/aws/aws-lambda-go
- https://github.com/marketplace/actions/aws-lambda-deploy
- https://github.com/aws/aws-lambda-dotnet
- https://github.com/awsdocs/aws-lambda-developer-guide
- https://github.com/marketplace/actions/invoke-aws-lambda


---

## Core ConceptsServerless: 
- No infrastructure to manage. AWS handles the underlying hardware.
- Event-Driven: Code executes only when triggered by specific events (e.g., file uploads, HTTP requests).
- Sub-second Billing: You pay strictly for the milliseconds your code runs and the number of requests.
- Automatic Scaling: Scales seamlessly from zero to thousands of concurrent requests per second.

##  How AWS Lambda Works

- Every execution follows simple three-part pipeline:
- [ Trigger / Event Source ]  ──>  [ AWS Lambda Function ]  ──>  [ Destination / Downstream ]
- Trigger (Event Source): An action occurs in another service, like an image uploaded to Amazon S3 or an API call via Amazon API Gateway.
- Lambda Function: AWS immediately spins up an isolated micro-VM (Firecracker) to execute your code.
- Destination: Your code finishes its task, such as saving processed data to Amazon DynamoDB or returning an HTTP response.

<img width="1160" height="722" alt="image" src="https://github.com/user-attachments/assets/388724c0-8d13-4a11-95da-e967e86fb535" />

## Common Use CasesFile Processing: 
- Automatically generating thumbnails immediately after photos land in an S3 bucket.
- Web Backends: Serving REST or GraphQL APIs when combined with Amazon API Gateway.
- Scheduled Automation: Running cron-like tasks (e.g., nightly database cleanups via Amazon EventBridge).
- IoT & Stream Processing: Filtering data streams coming from connected devices via Amazon Kinesis.

## Known LimitationsCold Starts 
- Initial execution takes slightly longer if a function hasn’t been run recently.
- State Management: Functions are completely stateless; data must be saved to an external database.

  
---

