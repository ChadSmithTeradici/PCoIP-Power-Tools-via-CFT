# HP Anyware and Perforce Client tools for AWS GPIC instances
Curated Game Production in Cloud (GPIC) instance(s) that are pre-installed with HP Anyware, perforce client tools, game engine(s) and utilities to get a developer up and running in AWS.

Deploy EC2-Nvidia graphics enabled instances based off a HP Anyware Windows 2019 Epic Unreal 4 AWS marketplace image. (or) HP Anyware with Windows 2019 AWS marketplace image. Perforce client tools (P4V) and other commonly used utilities are also provisioned automatically on instance start-up to streamline your deployment in the cloud.

Choose from four available templates and further customize to meeting your requirements
1. HP Anyware on Windows 2019 instance with EPIC unreal version 4
2. HP Anyware on Windows 2019 (no game engine pre-installed)
3. HP Anyware on Windows 2019 with Blender version 3.1.1
4. HP Anyware on Windows 2019 with O3DE (Open 3D Engine)
Note: templates will have the following additional open-source tools installed on the instances on initial launch as well
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


__Note: These templates are suitable for creating reference deployments for demonstration, evaluation, or development purposes. The infrastructure created may not meet the reliability, availability, or security requirements of your organization.__
