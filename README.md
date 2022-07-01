# PCoIP-Power-Tools-via-CFT
Deploy a Teradici AWS marketplace AMIs with additioanl tools when you deploy with a Cloud Formation templates

# CloudFormation Templates
## Introduction
This directory contains CloudFormation templates and related scripts for deploying HP Anyware (PCoIP) components on AWS. These templates can be downloaded and optionally modified before use.

__Note: These templates are suitable for creating reference deployments for demonstration, evaluation, or development purposes. The infrastructure created may not meet the reliability, availability, or security requirements of your organization.__

CloudFormation templates can be uploaded to the AWS CloudFormation via the console at https://console.aws.amazon.com/cloudformation/home or used with the AWS CLI. If no modifications are needed, a copy of these templates are also available on S3 location "https://teradici-public.s3.amazonaws.com/CloudFormation/{template name}"; this location can be referenced directly when using AWS CloudFormation console.

For more information about CloudFormation, please visit https://aws.amazon.com/cloudformation/

## List of Templates
- [Perforce clients tools on PCoIP Ultra Marketplace AMI](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-PF-CFT/PCoIP-PF-CFT.yml)
- [Perforce clients tools on  EPIC Unreal 4 PCoIP Ultra Marketplace AMI](https://github.com/ChadSmithTeradici/PCoIP-Power-Tools-via-CFT/blob/main/PCoIP-UR4-PF-CFT/PCoIP-UR4-PF-CFT.yml)
- [NVIDIA Omniverse and CloudXR tools on PCoIP Ultra Marketplace AMI]
---
## Perforce client tools on PCoIP Ultra Marketplace AMI
Creates a HP Anyware PCoIP Ultra Windows 2019 Perforce client tools and extra utilites. 

### Requirements
- Must already of accepted Terms and Conditions of [HP Anyware PCoIP Ultra on Windows Server 2019](https://aws.amazon.com/marketplace/pp/prodview-boeg6hiewus3o)
- must be deployed in an existing VPC with at least 1 public or private subnet;
- an existing EC2 Key pair

### Quick create stack
https://console.aws.amazon.com/cloudformation/home?#/stacks/quickcreate?templateURL=https://teradici-public.s3.amazonaws.com/CloudFormation/CASManager/CASManager.yaml&stackName=casm
