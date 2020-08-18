## Before You Begin

- Ensure you have supported browser version installed on your machine before you start. See [Supported Browsers](https://docs.cloud.oracle.com/en-us/iaas/Content/GSG/Tasks/signingin.htm?browser#supported_browsers)

# Always Free Resources - Application Development

### Introduction

This hands-on, instructor-led workshop supplements live presentations and demos in order to cover both technical architecture and educational use cases, strategies when using Oracle Cloud Infrastructure's Always Free Resources.

No expertise or previous experience is required.

### Objective

The objective of this Hands-on lab is to deploy a simple web application on Always Free resources inside the Oracle Cloud Infrastructure (OCI). The deployment will be manual, so you can understand better each step and relations between different OCI resources.

Contents
- Architecture
-	Identity & Access Management
-	Storage
- Autonomous Database
- Networking
- Compute
- Load Balancer

## **STEP 1:** Architecture

## **STEP 2.1:** Identity & Access Management Overview

Overview of Oracle Cloud Infrastructure Identity and Access Management
Oracle Cloud Infrastructure Identity and Access Management (IAM) lets you control who has access to your cloud resources. You can control what type of access a group of users have and to which specific resources. This section gives you an overview of IAM components. 

### Components of IAM 

• RESOURCE: The cloud objects that your company's employees create and use when interacting with Oracle Cloud Infrastructure. For example: compute instances, block storage volumes, virtual cloud networks (VCNs), subnets, route tables, etc.

• USER: An individual employee or system that needs to manage or use your company's Oracle Cloud Infrastructure resources. Users might need to launch instances, manage remote disks, work with your virtual cloud network, etc. End users of your application are not typically IAM users. Users have one or more IAM credentials.

• GROUP: A collection of users who all need the same type of access to a particular set of resources or compartment.

• DYNAMIC GROUP: A special type of group that contains resources (such as compute instances) that match rules that you define (thus the membership can change dynamically as matching resources are created or deleted). These instances act as "principal" actors and can make API calls to services according to policies that you write for the dynamic group.

• NETWORK SOURCE: A group of IP addresses that are allowed to access resources in your tenancy. The IP addresses can be public IP addresses or IP addresses from a VCN within your tenancy. After you create the network source, you use policy to restrict access to only requests that originate from the IPs in the network source.

• COMPARTMENT: A Compartment is a collection of related resources (VCN, Compute Instances, etc). Compartments are a fundamental component of Oracle Cloud Infrastructure for organizing and isolating your cloud resources. You use them to clearly separate resources for the purposes of measuring usage and billing, access (through the use of policies), and isolation (separating the resources for one project or business unit from another). A common approach is to create a compartment for each major part of your organization. 

• TENANCY: The root compartment that contains all of your organization's Oracle Cloud Infrastructure resources. Oracle automatically creates your company's tenancy for you. Directly within the tenancy are your IAM entities (users, groups, compartments, and some policies; you can also put policies into compartments inside the tenancy). You place the other types of cloud resources (e.g., instances, virtual networks, block storage volumes, etc.) inside the compartments that you create.

• POLICY: A document that specifies who can access which resources, and how. Access is granted at the group and compartment level, which means you can write a policy that gives a group a specific type of access within a specific compartment, or to the tenancy itself. If you give a group access to the tenancy, the group automatically gets the same type of access to all the compartments inside the tenancy. 

• HOME REGION: The region where your IAM resources reside. All IAM resources are global and available across all regions, but the master set of definitions reside in a single region, the home region. You must make changes to your IAM resources in your home region. The changes will be automatically propagated to all regions. For more information, see Managing Regions.

• FEDERATION: A relationship that an administrator configures between an identity provider and a service provider. When you federate Oracle Cloud Infrastructure with an identity provider, you manage users and groups in the identity provider. You manage authorization in Oracle Cloud Infrastructure's IAM service. Oracle Cloud Infrastructure tenancies are federated with Oracle Identity Cloud Service by default.

## **STEP 2.2:** Create your Compartment

Welcome to the main page of your Oracle Cloud account. Here you can see shortcuts of how to quickly provision various cloud resources, along with information regarding your account. 

![](images/lab01/img22001.png)

Click on the **Menu** icon on the top left side. Scroll all the way down to Governance and Administration section. Click on the menu item **Identity** and then click on **Compartments**.

![](images/lab01/img22002.png)

This will bring up the Compartments administration page. Any Compartments created will be listed here along with information related to each Compartment such as: status, OCID, Authorized, the number of subcompartments and creation date. 

![](images/lab01/img22003.png)

**Note:** You can create subcompartments in compartments to create hierarchies that are six levels deep. For the purposes of this workshop we will not use subcompartments.

![](images/lab01/img22004.png)

Click on **Create Compartment**

![](images/lab01/img22005.png)

**Name**: Give your Compartment a name, for example: oad-hol
**Description**: Provide a short description about your compartment, for example: **Oracle Academy Day - Hands on Lab** 

As mentioned earlier we will not use subcompartments so keep the Parent Compartment as: **root**

We will not use Tags so leave the fields empty.

Click on **Create Compartment**

![](images/lab01/img22006.png)

The new compartment is now available in the compartment list.

![](images/lab01/img22007.png)

## **STEP 3.1:** Autonomous Database Overview



## **STEP 4.1:** Storage Overview

## **STEP 4.2:** Object Storage

Example text for Object Storage description.
![](images/lab01/img001.jpg)

Test

## **STEP 5.1:** Networking Overview

## **STEP 6.1:** Compute Overview

## **STEP 7.1:** Load Balancer Overview

The Oracle Cloud Infrastructure Load Balancing service provides automated traffic distribution from one entry point to multiple servers reachable from your virtual cloud network (VCN). The service offers a load balancer with your choice of a public or private IP address, and provisioned bandwidth.

A load balancer improves resource utilization, facilitates scaling, and helps ensure high availability. You can configure multiple load balancing policies and application-specific health checks to ensure that the load balancer directs traffic only to healthy instances. The load balancer can reduce your maintenance window by draining traffic from an unhealthy application server before you remove it from service for maintenance.

The Load Balancing service enables you to create a public or private load balancer within your VCN. A public load balancer has a public IP address that is accessible from the internet. A private load balancer has an IP address from the hosting subnet, which is visible only within your VCN. You can configure multiple listeners  for an IP address to load balance transport Layer 4 and Layer 7 (TCP and HTTP) traffic. Both public and private load balancers can route data traffic to any backend server that is reachable from the VCN.

In this first exercise, you will create your first Load Balancer. 

Before creating a Load Balancer you need to have the following cloud resources:
•	Virtual Cloud Network (VCN) 
•	A Public Subnet
•	An Internet Gateway
•	A Route Table
•	A security list 
and for that you will use the network resources that you have already created in the previews exersices.  

![](images/lab01/img71001.png)

To create a Load Balancer click on the **Menu** icon on the top left side.

Navigate to **Networking**  and then click on **Load Balancers**

![](images/lab01/img71002.png)

Make sure to select the same compartment where the rest of your cloud resources reside, and create your Load Balancer

Click on **Create Load Balancer**

![](images/lab01/img71003.png)

First provide a **Name** for your Load Balancer and select the type: **Public**. Then choose its Maximum Total Bandwidth: **Micro** or **Small**.

Below select the **Virtual Cloud Network** and the **Subnet** created in the previous exersices. 

Click **Next**

![](images/lab01/img71004.png)

Here you need to specify the load balancing policy. Choose **Weighted Round Robin** policy.

Below click on **Add Backends** button and select the compute instances that host the web application. 

![](images/lab01/img71005.png)

At the **Specify Health Check Policy** section choose the following: 
•	**Protocol: HTTP**
•	**Port: 80**
The rest of the parameters are optional and you may use the pre-existing values.

![](images/lab01/img71006.png)

Click on **Show Advanced Options** and choose the **Security List** tab. 
Here you may choose to configure the security list mannually or automatically. 

In case that you have not allowed any port rules to your subnet the Automatic method will automatically apply the Egress and Ingress rules for you. In this case on port 80.

![](images/lab01/img71007.png)

In the last step of creating a Load Balancer, you will configure the Listener. 

•	Provide a **Name** for your listener
•	Choose Type of traffic: **HTTP**
•	Port:**80**

Click **Submit** 

![](images/lab01/img71008.png)

Your Load Balancer is now in creating state...

![](images/lab01/img71009.png)

After a few minutes your Load Balancer will become Active. 

Copy its IP Address and paste it on a different web browser tab or window. You should be able to reach your Web Application. 

![](images/lab01/img71010.png)

**Note:** Wait a few minutes and you will notice that the Overall Heath will become green ✅ OK

The **Backend Sets Health** will also become green with no critical, warning or unknown errors.

![](images/lab01/img71011.png)
