# PCoIP-Power-Tools-via-CFT
Deploy a Teradici AWS marketplace AMIs with additioanl tools when you deploy with a Cloud Formation templates

# CloudFormation Templates
## Introduction
Have all your most commonly used tools and utilities per industry workflow available in a single step with the performacce of HP Anyware PCoIP Ultra. 

This directory contains CloudFormation templates and related scripts for deploying HP Anyware (PCoIP) components on AWS. These templates can be downloaded and optionally modified before use.  Select AMIs based on Game Development with Perforce, Blende or Unreal, Cloud Access Connector for brokering functionality or Nvidia Omniverse / CloudXR software. 

__Note: These templates are suitable for creating reference deployments for demonstration, evaluation, or development purposes. The infrastructure created may not meet the reliability, availability, or security requirements of your organization.__

CloudFormation templates can be uploaded to the AWS CloudFormation via the console at https://console.aws.amazon.com/cloudformation/home or used with the AWS CLI. If no modifications are needed, a copy of these templates are also available on S3 location "https://teradici-public.s3.amazonaws.com/CloudFormation/{template name}"; this location can be referenced directly when using AWS CloudFormation console.

For more information about CloudFormation, please visit https://aws.amazon.com/cloudformation/

## List of Templates
- [HP Anyware Cloud Access Connector AMI- EVAL](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/HPAnyware-CAC/HPAnyware-CAC-Eval.yml)
- [HP Anyware Cloud Access Connector AMI - PROD]
- [Perforce clients tools on PCoIP Ultra Marketplace AMI](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-PF-CFT/PCoIP-PF-CFT.yml)
- [Perforce clients tools on  EPIC Unreal 4 PCoIP Ultra Marketplace AMI](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-UR4-PF-CFT/PCoIP-UR4-PF-CFT.yml)
- [NVIDIA Omniverse and CloudXR tools on PCoIP Ultra Marketplace AMI]
- [Black Magic Resolve 17 Markeplace AMI with PCoIP Ulta BYOL license](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP_BMR17_CFT/PCoIP_BMR17_CFT.yml)
- [Black Magic Resolve 17.4.3 on PCoIP Ultra Marketplace Win2019 AMI](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP_BMR17_CFT/PCoIP_Win19_BMR17_CFT)
- [Black Magic Resolve 17.4.3 on PCoIP Ultra Marketplace Centos7 AMI](
---
## Perforce client tools on PCoIP Ultra Marketplace AMI
Creates a HP Anyware PCoIP Ultra Windows 2019 Perforce client tools and extra utilites. 

### Requirements
- Must already of accepted Terms and Conditions of [HP Anyware PCoIP Ultra on Windows Server 2019](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o) on AWS.
- must be deployed in an existing VPC with at least 1 public or private subnet.
- an existing EC2 Key pair

### Quick create stack
https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://teradici-public.s3.amazonaws.com/CloudFormation/CASManager/CASManager.yaml&stackName=casm

---
## Perforce client tools on Unreal 4 engine PCoIP Ultra Marketplace AMI
Creates a HP Anyware PCoIP Ultra Windows 2019 with Epic unreal 4, Perforce client tools and extra utilites. 

### Requirements
- Must already of accepted Terms and Conditions of [HP Anyware PCoIP Ultra on Windows Server 2019 with Unreal 4](https://aws.amazon.com/marketplace/pp/prodview-mj35z5mqzmanm?sr=0-4&ref_=beagle&applicationId=AWSMPContessa) on AWS.
- must be deployed in an existing VPC with at least 1 public or private subnet.
- an existing EC2 Key pair
- An existing Unreal accoutn (or) sign-in for a new account before access is granted

### Quick create stack
https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://teradici-public.s3.amazonaws.com/CloudFormation/CASManager/CASManager.yaml&stackName=casm
