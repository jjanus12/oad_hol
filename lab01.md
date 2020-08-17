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

## **STEP 3.1:** Storage Overview

## **STEP 3.2:** Object Storage

Example text for Object Storage description.
![](images/lab01/img001.jpg)

Test

## **STEP 4.1:** Autonomous Database Overview

## **STEP 5.1:** Networking Overview

## **STEP 6.1:** Compute Overview

## **STEP 7.1:** Load Balancer Overview










