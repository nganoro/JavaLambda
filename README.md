# JavaLambda

Steps: Cold start, invokation, shut down

## Initializing
  - cold start
      - sets up execution environment, allocatesd memory and sets up network
      - downloads your code
      - initiliazes runtime/ installs libraries and dependencies
      - start up code like statis initializers and constructors run
  - warm start
      - then aws reuses the same execution environment for subsequent requests
      - bypasses initialization and executes handler
   
## Features
  - Concurrency Control
      - the ability to manage how many instances of a function can run at the same time
      - to ensure the application is highly available and responsive
  - Provisioned Concurrency keeps a specified number of instances warm, so they respond instantly without cold start delays.
      - good for api's
### AWS Lambda Concurrency Control

| **Concurrency Type**       | **Description** | **Best Use Case** |
|---------------------------|----------------|--------------------|
| **Unreserved Concurrency** | Default behavior, scales automatically based on incoming requests. | General workloads where auto-scaling is acceptable. |
| **Reserved Concurrency**   | Sets a hard limit on the number of concurrent executions for a function. | Prevents overloading databases or downstream services. |
| **Provisioned Concurrency** | Pre-warms a fixed number of function instances to avoid cold starts. | Latency-sensitive applications like APIs and real-time processing. |


## Environment
  - execution environment
      - the isolated runtime environment where your function runs. It includes everything needed to execute your function, such as the OS, runtime, dependencies, and temporary storage.
      - secure lightweight containers
  - wrapper scripts
    - used to customize the runtime startup behavior of your lambda function.
    - enables you to set configuration parameters that cannot be set through language-specific environement variables

## maven dependencies
  - aws-lambda-java-core
    - Provides the core interfaces required to write a Lambda function in Java.
    - Without this dependency, your Java class won’t compile because it wouldn't recognize Lambda-specific interfaces
  - aws-lambda-java-events
    - Provides predefined event classes for AWS services that trigger Lambda (e.g., API Gateway, S3, DynamoDB, SNS, SQS).
  - aws-lambda-java-log4j2
    - Provides Log4j2-based logging optimized for AWS Lambda
    - Reduces cold start latency by pre-configuring Log4j2 for Lambda

## Resources
  - https://docs.aws.amazon.com/lambda/latest/dg/java-samples.html



 
  
