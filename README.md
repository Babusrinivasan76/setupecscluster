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
  2. clicke "Create" button in the "Application Load Balancer"
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/09-CreateServices-ApplLoadBalancer.png)
  3. Select the Name, Scheme, IP Address type, Listeners and Availability Zones
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/10-CreateServices-ApplLoadBalancer.png)
  4.Leave the "Configuration Security Settings" as default
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/11-CreateServices-ApplLoadBalancer.png)
  5.Create a new Security Group and assign the routing IP
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/12-CreateServices-ApplLoadBalancer.png)
  6.Configure the Target Grop and Health Checks in "Configure Routing"
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/13-CreateServices-ApplLoadBalancer.png)
  7.Select the VPC and Port in "Register Targets"
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/14-CreateServices-ApplLoadBalancer.png)
  8.Review the Details and click "Create"
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/15-CreateServices-ApplLoadBalancer.png)
  9.Ensure the Load Balancer is created successfully
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/16-CreateServices-ApplLoadBalancer.png)
  test
  ![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/17-CreateServices-ApplLoadBalancer.png)

### Step3: Create ECS Cluster

1. Search for "ECS" in the AWS Console and Select "Elastic Container Services"
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/00createECSCluster.png)
2.select the "Clusters" from the left side menu and click "Create"
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/01-CreateServices-ConfigServices.png)
3.Select "Fargate" and provide the configuration details
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/02-CreateServices-ConfigServices.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/03-CreateServices-ConfigServices.png)
4. After selecting the configurations, click "Next Step"
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/04-CreateServices-ConfigServices.png)

### Step4: Configure Services - Network, Load Balancer

5. Configure the Network Details
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/05-CreateServices-ConfigNetwork.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/06-CreateServices-ConfigNetwork.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/07-CreateServices-ApplLoadBalancer.png)

6. Select the Load Balancer from the drop down and configure other parameters. Click "Next Step"
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/18-CreateServices.png)

7. If the Application Load Balancer is not set up (shown in red) , click on the EC2 console and setup the Load balancer as instructed in Step2
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/application%20load%20balancer/08-CreateServices-ApplLoadBalancer.png)

8. Configure other parameters
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/19-CreateServices.png)
9. Configure the Auto-Scaling
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/20-CreateServices-AutoScaling.png)
10. Review the details and Click "Create Services"
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/21-CreateServices-Review.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/22-CreateServices-Completion.png)
11. Ensure all the services are created successfully
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/23-CreateServices-Completion.png)


### Step5: Configure Task
1.Navigate to "Task Definitions" and click "Create new Task definition"
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/01.createecscluster-task.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/02.createecscluster-task.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/03.createecscluster-task.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/04.createecscluster-task.png)
![](https://github.com/Babusrinivasan76/setupecscluster/blob/main/images/05.createecscluster-task.png)

### Step6: Review and Create

