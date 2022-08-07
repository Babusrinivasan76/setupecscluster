# Set up the AWS ECS Cluster

## Summary
  This is a technical document to show step by step process to setup the AWS ECS Cluster
  
## Step by Step Process for ECS Cluster

### Step1: Verify the NAT Gateway and Security Group permission

  1. Ensure the NAT Gateway is created and configured for the public subnet of the VPC.
  2. Ensure the Route Table for the Public subnet is configured for the IGW
  3. Ensure the Route Table for the Private Subnet is configured for the NAT GW
  4. Ensure the Security group created have the adequate inbound privileges.
  5. Ensure the NACL are configured for inbound and outbound permissions.

### Step2: Create Application Load Balancer

  1. Select  "Load Balancers" on the left side menu of EC2 services.
  2. 

### Step3: Create ECS Cluster

### Step4: Configure Services

### Step5: Configure Task

### Step6: Review and Create
