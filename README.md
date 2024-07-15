# Build a Bookstore Application with AWS Databases

## Project Description:
This project is an example built alongside an AWS Tutorial (https://aws.amazon.com/blogs/database/building-a-modern-application-with-purpose-built-aws-databases/) that allows you to build web storefornt, (a bookstore in this example) which is created on top of multiple databases, each addressing a different use case. Creating this demo bookstore web application allows you to learn various purpose-built AWS Databases such as DynamoDB, ElasticSeach Service, Elasticache for Redis and Neptune.

This is a great project to familiarize yourself with various database technologies offered within the AWS ecosystem, as well as using serverless and web deployment services in AWS, such as Lambda, API Gateway, and Cognito. You get to:

- Leverage DynamoDB as the durable system of record for the product catalog and learn the principles of NoSQL database design, scalability, and high availability.
- Integrate Amazon Elasticsearch to enhance search functionality, teaching you how to index and query data efficiently
- Use DynamoDB Streams with AWS Lambda for asynchronous updates to the Elasticsearch index and learn event-driven architecture and serverless computing concepts
- Implement Elasticache for Redis to manage a best sellers list to learn in-memory data storage techniques and performance optimization.
- Employing Amazon Neptune for social recommendations to gain insights into graph databases and personalized content delivery.
- Utilizing API Gateway and Lambda to handle various API calls highlights RESTful API design and serverless application development

## Architecture Diagram:
![Alt text](architecture.PNG)

## Components Description:

| Component     | Functionality |
| ------------- | ------------- |
| DynamoDB      | Stores the product catalog; provides a durable, scalable NoSQL database for managing item data  |
| Amazon Elasticsearch | Enables fast and accurate search functionality within the product catalog; indexes data for efficient querying  |
| DynamoDB Streams  |Captures changes made to the DynamoDB table, allowing for event-driven processing using AWS Lambda.  |
| AWS Lambda  |Executes code in response to events (e.g., DynamoDB Streams updates); used for updating Elasticsearch and handling API requests.|
| Elasticache for Redis  |Provides in-memory caching to quickly retrieve best sellers list and other frequently accessed data.  |
|Amazon Neptune  | Powers social recommendations through a graph database, facilitating complex queries on relationships and interactions  |
|API Gateway  | Manages API endpoints for the web storefront; provides a secure and scalable entry point for API requests. |
| Amazon S3 | Used to store the static web files |
| CloudFront | Cache the web static files at edge locations for faster accessibility  |
| Cognito  | Manage user management  |
| CloudWatch  | Monitor AWS resources based on defined metrics  |

## Functional Requirements:
- Search Functionality - Ensure books can be searched inside a search box and results can be returned to users quickly and accurately
- Product Catalog Management - Allow users to perform CRUD operations (Create, Read, Update, Delete) on the catalog
- Bestsellers List - Allow quick retrieval of best-selling items
- Personalized recommendations - Offer social recommendations based on user interactions and preferences

## Non-Functional Requirements:
- Scalability: The application must handle increasing loads automatically and without performance degradationby.
    - DynamoDB: Automatically scales up and down to accommodate varying loads without manual intervention
    - Amazon Elasticsearch: Scalable search capabilities to handle growing data and query volumes.
    - Elasticache for Redis: In-memory caching scales horizontally to manage increased demand.
    - API Gateway and Lambda: Serverless architecture that scales automatically with the number of API requests.
- Availability: The application must be available and operational 99.9% of the time or higher.
    - DynamoDB: Offers high availability with multi-AZ (Availability Zone) replication.
    - Amazon Elasticsearch: Provides multi-AZ deployment options to ensure search service availability.
    - Elasticache for Redis: Supports replication and automatic failover to ensure continuous availability.
    - Amazon Neptune: Multi-AZ architecture ensures high availability for the graph database.
    - API Gateway and Lambda: Both services are designed for high availability and reliability.
- Performance: The application must respond to user requests with minimal latency.
    - DynamoDB: Low latency response times with SSD-backed storage.
    - Amazon Elasticsearch: Fast and efficient search indexing and querying.
    - Elasticache for Redis: Provides sub-millisecond response times for frequently accessed data.
    - AWS Lambda: Executes code in milliseconds, ensuring quick processing of API requests and data updates.
    - API Gateway: Optimizes API request handling with low latency.
- Security: The application must ensure data security and integrity.
    - DynamoDB: Encryption at rest and in transit, along with fine-grained access control via IAM.
    - Amazon Elasticsearch: Secure data transmission with HTTPS and VPC-based access control.
    - Elasticache for Redis: Supports encryption in transit and at rest, with IAM authentication.
    - Amazon Neptune: Provides encryption at rest and secure access control mechanisms.
    - API Gateway: Supports SSL/TLS encryption, IAM roles, and API keys for secure access control.
    - AWS Lambda: Encrypted environment variables and IAM roles to manage permissions securely.
- Cost Efficiency: The application must optimize costs while delivering required performance and reliability
    - DynamoDB: Pay-per-use pricing model, with on-demand and provisioned capacity modes to manage costs.
    - Amazon Elasticsearch: Pricing based on the number of instances and storage used, with options to optimize search costs.
    - Elasticache for Redis: Pay for the resources consumed, with cost-effective scaling options.
    - AWS Lambda: Pay only for the compute time used, with no charges when the code is not running.
    - API Gateway: Pay-per-request pricing model, allowing cost management based on usage.


