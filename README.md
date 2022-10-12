# HP Anyware and Perforce Client tools for AWS GPIC instances
Curated Game Production in Cloud (GPIC) instance(s) that are pre-installed with HP Anyware, Perforce client tools, game engine(s) and utilities to get a developer up and running in AWS.

Deploy EC2-Nvidia graphics enabled instances based off a HP Anyware Windows 2019 Epic Unreal 4 AWS marketplace image. (or) HP Anyware with Windows 2019 AWS marketplace image. Perforce client tools (P4V) and other commonly used utilities are also provisioned automatically on instance start-up to streamline your deployment in the cloud.

Choose from four available templates and further customize to meeting your requirements
1. HP Anyware on Windows 2019 instance with EPIC unreal version 4
2. HP Anyware on Windows 2019 (no game engine pre-installed)
3. HP Anyware on Windows 2019 with Blender version 3.3.1
4. HP Anyware on Windows 2019 with O3DE (Open 3D Engine)

Note: templates will have the following additional open-source tools installed on the instances on initial launch.
- Perforce Client tools (P4V)
- Visual Studio 2017 community
- Google Chrome browser
- JetBrains Rider
- git
- 7zip
- notepad plus


# CloudFormation Templates
## Introduction
Have all your most used tools and utilities per industry workflow available in a single step with the performance and HP Anyware PCoIP Ultra by deploying via a cloud formation template. 
This directory contains CloudFormation templates and related scripts for deploying HP Anyware (PCoIP) components on AWS. These templates can be downloaded and optionally modified before use.

**Diagram below is a high-level overview of the Cloud Formation template:**

 ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/GPIC-CFT-Parts.png?raw=true)
 
   **Existing VPC / network**- Script will ask what Virtual Private Cloud (VPC) and what subnet should the instance be deployed in? These must be pre-existing resources and subnet MUST be apart of the VPC selected.

   **G4 / G5 Instance(s)** - Baseline images are built to be deployed on Nvidia technologies, GPUs are pre-selected that have various CPU, memory and GPU resouces. Please consult with following links to see what requirements are best. [AWS G4dn instance family](https://aws.amazon.com/ec2/instance-types/g4/)  and [AWS G5 instance family](https://aws.amazon.com/ec2/instance-types/g5/)

  **HP Anyware marketplace image** - Base on selected marketplace image you will have pre-built image with either HP Anyware on Window 2019 server (or) HP Anyware on Windows 2019 server + Epic unreal 4 and is available in every AWS region. You must agree to the AWS marketplace EULA before deploying the CFT.
  
  **Deployment Script** - A additional deployment script will run on instance creation that will install the extra utilities not already bundled in the image build. Also, if the Blender (or) O3DE cloud formation templates (CFT) where choosen, these game engines will be installed with this step. Becuase of this a deployment script may take an extra couple of minutes to finish. **Note:** the deployment script section of the CFT is customizable. Average deployment time is between 10 and 20 minutes.


__Note: These templates are suitable for creating reference deployments for demonstration, evaluation, or development purposes. The infrastructure created may not meet the reliability, availability, or security requirements of your organization.__

# Deployment of solution

## Objectives

+ Read and Agree the EULA agreement for the underlying marketplace offerings
+ Select one of the four game builds by selecting on of the URL(s)
+ By clicking on URL it will automatically open the Cloud Formation Template wizard
+ Configure the settings in the CFT (VPC, network, Instance Type, Key Name, Security Group)
+ Launch CFT, gather login credentials and IP address
+ Access EC2 Instance via HP Anyware client

## Costs

This tutorial uses billable components of AWS Cloud and assumes Teradici subscription, including the following:
+   [AWS EC2 Instance](https://aws.amazon.com/pm/ec2/), including vCPUs, memory, disk, and GPUs
+   [Internet egress and transfer costs](https://aws.amazon.com/blogs/architecture/overview-of-data-transfer-costs-for-common-architectures/), for PCoIP and other applications communications.

## Read and Agree to subcription for HP Anyware AWS marketplace offering
The cloud formation template leverages a baseline Teradici managed marketplace image that comes bundled with Base OS of Microsoft Windows Server 2019, HP Anyware remote desktop protocol. We have partnered with Epic to have Unreal version 4 game engine pre-installed on one as one of the deployment options. In order to gain access to these images, you must go to the AWS marketplace offering page and agree and subscribe before proceeding. If you have prevously agreed one of the two HP Anyware marketplace offering, you don't have to reregister. **Note:** When you sybscribe you will not be charged be until you build and run an instance.
 
**'CLICK ON'** the game-engine icon to subscribe to the correct HP Anyware marketplace version: 

[![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/Unreal-logo-small.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-mj35z5mqzmanm?sr=0-5&ref_=beagle&applicationId=AWSMPContessa)  &emsp; &emsp;  [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/blender-small.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)  &emsp; &emsp;  [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/o3DE-small.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)  &emsp; &emsp;  [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/HPA-small.png)](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)  

[![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/HPA-small.png)][(https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)][target="_blank"]

**NOTE:** HP Anyware build doesn't include a game-engine but includes Perforce client tools and utlities. 

From the marketplace page, select **Subscribe** to the offering to continue.

![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/Continue2Subscribe.png)

Use the back arrow to come back to this page to proceed to the next step.

## Launching the Cloud Formation Template


**'CLICK ON'** the game-engine icon to launch the cloud formation template: 

[![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/Unreal-logo-small.png?raw=true)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-UR4-PF-CFT.yml&stackName=hpaepic) &emsp; &emsp; [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/blender-small.png)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-Blender-PF-CFT.yml&stackName=hpablender) &emsp; &emsp; [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/o3DE-small.png)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-O3DE-PF-CFT.yml&stackName=hpao3de) &emsp; &emsp; [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/HPA-small.png)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-PF-CFT.yml&stackName=hpagpic)

**NOTE:** HP Anyware build doesn't include a game-engine but includes Perforce client tools and utlities.

## Setting parameters and configurations within the CFT

![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/CFT-Questions.png)

## Launch the CFT, gather IP and login credentials

## Access the EC2 Instance via HP Anyware client
