# HP Anyware and Perforce Client tools for AWS GPIC instances
Curated Game Production in Cloud (GPIC) instance(s) that are pre-installed with HP Anyware, Perforce client tools, game engine(s) and utilities to get a developer up and running in AWS.

Deploy EC2 Nvidia graphics enabled instances with  Windows 2019, game engine, HP Anyware, Perforce client tools and various game production utilities. Start with Epic Unreal 4 AWS marketplace image. (or) HP Anyware with Windows 2019 AWS marketplace images. Perforce client tools (P4V) and other commonly used tools are provisioned  on instance start-up to streamline your deployment in the cloud.

## Perforce Intergration
This solution only installs the Perforce client tools (P4V) and it is assumed a Perforce Helix Core Server is already stood-up either on-premises (or) in cloud. If you need purchase Perforce helix core server, you have the option of procuring the [perforce helix server](https://aws.amazon.com/marketplace/pp/prodview-koqs2fm5wwsos?sr=0-1&ref_=beagle&applicationId=AWSMPContessaom) from the AWS marketplace. 

## Templates Options
Choose from four available templates and further customize to meeting your requirements by modifying the templates
1. HP Anyware on Windows 2019 instance with EPIC unreal version 4
2. HP Anyware on Windows 2019 (no game engine pre-installed)
3. HP Anyware on Windows 2019 with Blender version 3.3.1
4. HP Anyware on Windows 2019 with O3DE (Open 3D Engine) version 22.10.0

Note: templates will have the following additional open-source tools installed on the instances on initial launch.
- Perforce Client tools (P4V)
- Visual Studio 2017 (or) 2019 community
- Google Chrome browser
- JetBrains Rider
- git
- 7zip
- notepad plus

# CloudFormation Templates
## Introduction
Have all your most used tools and utilities per industry workflow available in a single step with the performance and HP Anyware PCoIP Ultra by deploying via a cloud formation template (CFT) 
This GitHub repo contains the four CFT templates for deploying HP Anyware (PCoIP) components on AWS. These templates can be downloaded and optionally modified before use.

**Diagram below is a high-level overview of the Cloud Formation template:**

 ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/GPIC-CFT-Parts.png?raw=true)
 
   **Existing VPC / network**- Script will ask what Virtual Private Cloud (VPC) and what subnet should the instance be deployed in? These must be pre-existing resources and subnet MUST be apart of the VPC selected.

   **G4 / G5 Instance(s)** - Baseline images are built to be deployed on Nvidia technologies, GPUs are pre-selected that have various CPU, memory and GPU resources. Please consult with following links to see what requirements are best. [AWS G4dn instance family](https://aws.amazon.com/ec2/instance-types/g4/)  and [AWS G5 instance family](https://aws.amazon.com/ec2/instance-types/g5/)

  **HP Anyware marketplace image** - Base on selected marketplace image you will have pre-built image with either HP Anyware on Window 2019 server (or) HP Anyware on Windows 2019 server + Epic unreal 4 and is available in every AWS region. You must subscribe to the AWS marketplace offering before deploying a CFT.
  
  **Deployment Script** - A additional deployment script will run on instance creation that will install the extra utilities not already bundled in the image build. Also, if the Blender (or) O3DE cloud formation templates (CFT) where chosen, these game engines will be installed with this step. Because of this a deployment script may take an extra couple of minutes to finish. **Note:** the deployment script section of the CFT is customizable. Average deployment time is between 10 and 20 minutes.

__Note: These templates are suitable for creating reference deployments for demonstration, evaluation, or development purposes. The infrastructure created may not meet the reliability, availability, or security requirements of your organization.__

# Deployment of solution

## Objectives

+ Read and Subscriber too the EULA agreement for the underlying marketplace offerings
+ Select one of the four game builds by selecting on of the URL(s)
+ By clicking on URL it will automatically open the Cloud Formation Template wizard
+ Configure the settings in the CFT (VPC, network, Instance Type, Key Name, Security Group)
+ Gather login credentials / IP address and sccess EC2 Instance via HP Anyware client

## Costs

This tutorial uses billable components of AWS Cloud and assumes Teradici subscription, including the following:
+   [AWS EC2 Instance](https://aws.amazon.com/pm/ec2/), including vCPUs, memory, disk, and GPUs
+   [Internet egress and transfer costs](https://aws.amazon.com/blogs/architecture/overview-of-data-transfer-costs-for-common-architectures/), for PCoIP and other applications communications.

## Read and Agree to subscription for HP Anyware AWS marketplace offering
The cloud formation template leverages a baseline Teradici managed marketplace image that comes bundled with Base OS of Microsoft Windows Server 2019, HP Anyware remote desktop protocol. We have partnered with Epic to have Unreal version 4 game engine pre-installed on one as one of the deployment options. In order to gain access to these images, you must go to the AWS marketplace offering page and agree and subscribe before proceeding. If you have previously agreed one of the two HP Anyware marketplace offering, you don't have to reregister. **Note:** When you subscribe you will not be charged be until you build and run an instance.
 
**'CTRL + CLICK'** On the game-engine icon to open a new tab in browser and subscribe to the correct HP Anyware marketplace offering: 

[![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/Unreal-logo-small.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-mj35z5mqzmanm?sr=0-5&ref_=beagle&applicationId=AWSMPContessa)  &emsp; &emsp;  [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/blender-small.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)  &emsp; &emsp;  [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/o3DE-small.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)  &emsp; &emsp;  [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/HPA-small.png)](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o?sr=0-1&ref_=beagle&applicationId=AWSMPContessa)  

**NOTE:** HP Anyware build doesn't include a game-engine but includes Perforce client tools and utlities. 

From the marketplace page, select **Subscribe** to the offering to continue.

![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/Continue2Subscribe.png)

Use the back arrow to come back to this page to proceed to the next step.

## Launching the Cloud Formation Template

**'CTRL + CLICK'** On the game-engine icon to open a new tab in browser to launch the cloud formation template: 

[![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/Unreal-logo-small.png?raw=true)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-UR4-PF-CFT.yml&stackName=hpaepic) &emsp; &emsp; [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/blender-small.png)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-Blender-PF-CFT.yml&stackName=hpablender) &emsp; &emsp; [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/o3DE-small.png)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-O3DE-PF-CFT.yml&stackName=hpao3de) &emsp; &emsp; [![name](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/HPA-small.png)](https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://hpagpicbucket4scripts.s3.us-west-2.amazonaws.com/HPA-PF-CFT.yml&stackName=hpagpic)

**NOTE:** HP Anyware build doesn't include a game-engine but includes Perforce client tools and utlities.

## Setting parameters and launching the CFT

![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/CFT-Questions.png)

1.	**VcpId** : This field is the virtual private cloud within your AWS region in which you want to deploy the solution in. If no other VPC has been created, you can the *(Default)* VPC automatically created.
2.	**SubnetId:** This field you MUST select a subnet that has been generated in the same VPC associated above. If no other subnet has been created, you can use the *(Default)* subnet automatically.
3.	**Instance Type:** This drop-list is pre-populated with NVIDIA enabled instance types. Care must be taken to ensure that your selected instances IS available in your AWS region and Available Zone (AZ). As a general rule, almost all G4dn instance types are available in all regions, which G5 instances are available in most popular regions. Check these webpages to verify your instance resource requirements. [AWS G4dn instance family](https://aws.amazon.com/ec2/instance-types/g4/)  and [AWS G5 instance family](https://aws.amazon.com/ec2/instance-types/g5/)
4.	**KeyName:** Select the Key name of your Key Pair. The key pair will be used to generate your Windows Administrator password after the Instance has been started. If you haven’t generated a Key Pair, log into the [EC2 dashboard](https://console.aws.amazon.com/ec2), navigate to the left-side bar under Network & Security > Key Pairs > create new Key Pair
5.	**RDPLocation:** The automatically generated security group associated to the instance has a rule to allow a back-door RDP (port 3889) communications to the instance for troubleshooting and HP Anywhere patching. We recommend locking this port down by entering in your workstations IP address. This address can be seen [What Is My IP?](https://www.whatismyip.com/) Quickly See your IP Address. Once your external IP has been identified, you must append a */32* to create the security group. entry.

To Launch the CFT - Press the **Create Stack** button to continue.

## Gathering Login info IP / credentials and access the EC2 Instance via HP Anyware client

In this section, you will establish a connection to your instance using PCoIP. You will need to install a PCoIP client on your client system that will be used to initiate the session to the EC2 Instance in AWS. Depending on your network topology, use will either connect to the local IP (or) ephemeral/elastic Public IP (or) Fully Qualified Domain Names (FQDN)

1. [Download the client installer](https://docs.teradici.com/find/product/software-and-mobile-clients) based on your client OS. You don't need a login credentials to download client software and can have as many copys of various client OS as you need.

1. Install the PCoIP client software per the OSs Administration Guides installation instructions.

1. Locate the **IP address** or **FQDN** of the AWS EC2 instance via the [EC2 Dashboard](https://console.aws.amazon.com/ec2)

1. Identify the instance within the list of **Running Instances** in the EC2 Dashboard, check the **box** near the instance name, if it was named.

1. Under the **Details** tab you will see **Public IPv4 Address** (or) **Private IPv4 Address** (or) **Private IPv4 DNS** (or) **Public IPv4 DNS**

1. From the client system, start your PCoIP client per OS. Typically the PCoIP client will have a icon:

     ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP%20Client%20Icon.png?raw=true)
 
 7. When the PCoIP client starts for the first time, it will ask to **Add aconnection**. 
 
     ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-Client-new.png?raw=true)
 
 8. Enter in your **IP address or FQDN** previously identified in previous section. (optionally) enter a name to **Connection Name** field then **Add Connection**, if you want to save connection.

    ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-client%20-EnterInfo.png?raw=true)

  9. Next, you will get a 'Cannot verify your connection to IP' warning. This error is becuase a 3rd party trusted certificate has not been install on the host. You can select the **Connect Insecurely** option to continue. **Note:** you can modify this behavior by going into the client setting > Advanced > Security Modes


  10. Finally, enter in the OS login credentials for **Windows** it would be **Administrator** and the password can be [retreived](https://aws.amazon.com/premiumsupport/knowledge-center/retrieve-windows-admin-password/) via EC2 console after provisioning is complete
 
      ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-client-Login.png?raw=true)
 
 11. You will be promoted to select a host to connect, in this senerio you will only have one choice. *(When using a connection broker you have be entitled to muiltiple instances)* **Click** on the instance name to establish a connection to host.
 
     ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-Client-InstanceSelect.png?raw=true)
 
 12. The Launching session processes does take a few extra seconds on initial connection, subsequent connection start almost instantly. 
 
     ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-Client-Laucnhing.png?raw=true)
 
 13. Once presented your remote deskop, you will be presented a Anyware PCoIP Client menu to allow tasks like USB transfer, full screen and multiple monitor support.
 
     ![image](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-Client-Session.png?raw=true)
