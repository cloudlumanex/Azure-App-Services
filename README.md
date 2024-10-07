# Azure-App-Services
Deploying and Managing a Web Application Using Azure App Service

# Project Overview
Azure App Service is a Platform For Hosting Web Applications, Mobile Backends, REST API, and Azure Functions. To set up The App service you will need an App Service Plan. This App Service plan specifies the OPERATING SYSTEM, REGION, INSTANCE SIZE, SCALE COUNT, and SKU / PRICING TIER. It provides 99.95% SLA, which translates to 43 seconds downtime per day, 5 minutes per week, and 22 hours per month downtime. It has stagging and deployment slots which are separate environments for deploying either to test or stage and then swapping with production. it consists of 3 main pricing tier 
1. Shared - Free, shared tier
2. Dedicated - Basic, Standard, Premium tier
3. Isolated

The pricing tier differs in: 
- CPU, Memory, Storage,
- Auto-Scale
- Backups
- Staging Slots
- Custom Domain

It supports applications developed in the following languages and frameworks:
- C#
- .NET
- .NET CORE
- PHP
- JAVA
- RUBY
- NODE JS
- PYTHON

Authentication and authorization are built into Azure App Service, so no extra code is required. It integrates with major login providers such as  Facebook, Google, or any OpenID Connect provider


# Process using the Azure portal in 5 STEPS
# STEP 1

I created a Resource group "EduConnectWebAppRG" that will house all the resources for this project and be hosted in the North Europe Region. Azure Resource Group holds resources in a logical folder for easy management of the resources.
After creating a resource group I searched for Azure App Service and chose Web App. I then proceeded to set up and configure the web app: 
* **Name**: educonnect-webapp
* **Runtime Stack**:NET8(LTS)
* **Operating System**: windows
* **Region**: North Europe
* **Pricing plan**: Standard S1 (100 total ACU, 1.75 GB memory, 1 vCPU)
* **Continous Deployment**: Enable
* **Basic Authentication**: Disable
* **Public Access**: Enable
* **Application Insight**: Enable

After carefully reviewed the setup I then CREATED my Webapp.
![Screenshot 2024-10-07 090927](https://github.com/user-attachments/assets/429cad2d-1b78-47a9-b100-0739d42243e9)





