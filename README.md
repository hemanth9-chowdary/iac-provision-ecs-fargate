# Terraform template for AWS ECS/Fargate

This terraform setup can be used to setup the AWS infrastructure
for a dockerized application running on ECS with Fargate launch
configuration.

## Resources

This setup creates the following resources:

- VPC
- One public and one private subnet per AZ
- Routing tables for the subnets
- Internet Gateway for public subnets
- NAT gateways with attached Elastic IPs for the private subnet
- Two security groups
  - one that allows HTTP/HTTPS access
  - one that allows access to the specified container port
- An ALB + target group with listeners for port 80
- An ECR for the docker images
- An ECS cluster with a service (incl. auto scaling policies for CPU and memory usage)
  and task definition to run docker containers from the ECR (incl. IAM execution role)


### Get Started building your own infrastructure

- Login to the Terraform Cloud
- Open the workspace if already configured , if not please create a workspace and integrate with this repo onGitHub 
- Configure the Variables - please check variables.tf file the list of variables and it's default values 
- Configure AWS Key and secrets as secret variables 
- Run the plan which will create entire infrastructure on AWS