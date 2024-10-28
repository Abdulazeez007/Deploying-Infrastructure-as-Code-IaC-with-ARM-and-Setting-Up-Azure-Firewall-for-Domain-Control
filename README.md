# Deploying-Infrastructure-as-Code-IaC-with-ARM-and-Setting-Up-Azure-Firewall-for-Domain-Control
This project focuses on setting up Infrastructure as Code (IaC) using Azure Resource Manager (ARM) templates to automate and streamline the deployment of Azure resources. Additionally, I'll configures Azure Firewall to manage and control outbound traffic to specific domains, enhancing security and ensuring compliance with organizational policies. This approach provides scalable, consistent deployments and precise traffic filtering to designated destinations.

**KEY OBJECTIVES**  

1. 🛠️ Use ARM Template to deploy the Lab Environment  
2. 🔥 Deploy and Configure Azure Firewall  
3. 🚦 Create Firewall Route and Associate with Subnet  
4. 📜 Configure Firewall Application and Network Rules  
5. 🌐 Configure DNS Servers  
6. ✅ Test the Firewall  

**NETWORK TOPOLOGY**  
![SOC]()

## STEP 1
- Use ARM Template to Deploy Lab Environment.
- First, I launched my Azure portal, then in the Azure portal, search Deploy a custom template and press the Enter key.
- On the Custom deployment blade, click the Build your own template in the editor option.
- click on load file, and select the ARM template which is a .json file.
- Upload ARM template (Download template fromAzure AZ500 Github Lab ***https://github.com/MicrosoftLearning/AZ500-AzureSecurityTechnologies/blob/master/Allfiles/Labs/08/template.json***)

![SOC]()

