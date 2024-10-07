# Summary of Project Objectives
## The project aimed to deploy and manage a highly available, scalable, and secure web application for EduConnect, an e-learning platform catering to students and teachers. The key objectives included
* Setting Up Azure App Service: Creating an Azure App Service tailored to the performance and cost needs of the application.
* Deploying the Web Application: Utilizing GitHub Actions for continuous integration and continuous deployment (CI/CD) to streamline updates and manage version control effectively.
* Custom Domain and SSL Implementation: Configuring a custom domain and implementing SSL to ensure secure communication between users and the application.
* Auto-Scaling Configuration: Setting up auto-scaling based on real-time performance metrics to handle varying traffic loads efficiently.
* Monitoring with Application Insights: Implementing Application Insights to monitor application performance, availability, and user engagement, ensuring proactive management and timely responses to issues

# Archutectural drawing



# Process using the Azure portal is in Stages
# Create an Azure App Service

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

# Deploy the Web Application Using GitHub Actions

After Deploying my App service, I went to the DEPLOYMENT CENTER selected GITHUB as my source, and Authorized it, I chose my repository and branch where my code will be hosted on GitHub.
![Screenshot 2024-10-07 092102](https://github.com/user-attachments/assets/0178e032-7c44-4d08-8027-e3f061aebd5e)

After setting up the DEPLOYMENT CENTER, I went to the DEPLOYMENT SLOT where I added a slot called STAGING and cloned the setting from the Production Slot, this allows me to test updates in Staging Slot before Pushing to production 
![Screenshot 2024-10-07 094319](https://github.com/user-attachments/assets/313af34d-a164-46c5-b507-2e6f8da55162)

# Configure Custom Domain and SSL
I selected the Custom Domain, then I added the educonnect domain name which is www.educonnect.org  after configuring my Custom Domain, I chose app service management and uploaded the SSL certificate Service after which had to bind the SSL certificate to my Custom Domain.
<img width="936" alt="Screenshot 2024-10-07 095514" src="https://github.com/user-attachments/assets/10e906f4-58db-41e4-b0ab-358db5fe88f2">

# Enable Auto-Scaling
For Auto-Scaling I navigated to Scale Out and added these Rules:
* Metric: CPU Percentage 
* Condition: if CPU usage > 70% for 5 minutes
* Action: increase by 1 instance
![Screenshot 2024-10-07 102548](https://github.com/user-attachments/assets/2aef12df-3dab-46ef-bc6f-9fc998abd184)

To Monitor Scaling I navigated to Metrics where I tracked the performance of the app using:
* CPU TIME
* RESPONSE TIME
* THREAD COUNT
![Screenshot 2024-10-07 103520](https://github.com/user-attachments/assets/ca2489ec-73e7-421b-9272-998723458944)

# Impement Application Insight
I Navigated to the Application insight of the web app and create an alert rule 
* **Condition**: Availability and failed Request
* **ActionGroup**: Application insight Smart detection
* **Severity**: Sev 3
![Screenshot 2024-10-07 112159](https://github.com/user-attachments/assets/19cd6f4d-5329-48b1-ab0e-518e7e5101b1)
![Screenshot 2024-10-07 111644](https://github.com/user-attachments/assets/2df5cb9f-98b4-4721-8974-3f0817c0f1d9)
