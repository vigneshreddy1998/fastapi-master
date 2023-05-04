1.Create an IAM user and grant necessary permissions
To interact with AWS services, we need to create an IAM user with appropriate permissions. We need to grant permissions for the following actions:

Creating and managing an RDS instance
Creating and managing an EC2 instance
Creating and managing a VPC and related resources
Creating and managing an S3 bucket
Creating and managing an IAM user and roles
Creating and managing Terraform resources
We can create a new IAM user and grant the necessary permissions using the AWS Management Console.

Create a Terraform configuration file
We need to create a Terraform configuration file that defines the infrastructure required to deploy the sample API. We will define the following resources in the configuration file:

A VPC with two public subnets and two private subnets
An RDS instance in one of the private subnets
An EC2 instance in one of the public subnets
An S3 bucket to store the Terraform state file
We will also use Terraform modules to manage the creation of each of these resources.

2.Set up CI/CD
To set up CI/CD, we need to use a continuous integration and continuous delivery (CI/CD) tool like Jenkins, CircleCI, or GitLab CI/CD. We will create a pipeline that automates the deployment of the sample API using Terraform.

The pipeline will include the following stages:

Build: Download dependencies and build the sample API
Test: Run unit tests and integration tests
Deploy: Use Terraform to deploy the sample API to AWS
We will also configure the pipeline to run automatically whenever changes are pushed to the GitHub repository.

3.Deploy the sample API
Once we have set up Terraform and CI/CD, we can deploy the sample API to AWS by running the pipeline. The pipeline will create the necessary infrastructure and deploy the sample API to the EC2 instance.


========================================================

Deploying the API and Setting Up the Backend
Clone the repository to your machine using the following command:
git clone https://github.com/marciovrl/fastapi.git


Navigate to the repository directory:
cd fastapi


Create a terraform.tfvars file in the terraform directory and populate it with the following variables:
aws_region = "your_aws_region"
db_name = "your_database_name"
db_username = "your_database_username"
db_password = "your_database_password"


Initialize Terraform by running the following command in the terraform directory and then apply the changes.
terraform init
terraform apply

Wait for the infrastructure to be deployed and note down the output values, which include the database endpoint, database name, and database username.
Update the config.py file in the app directory with the database endpoint, name, and username obtained in the previous step.
Commit and push the changes to the repository.


Note : By following the steps outlined in this document, you should now have a sample API deployed to AWS with a backend using RDS PostgreSQL, as well as a Jenkins pipeline set up for CI/CD. 