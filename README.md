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

## STEP 1:  Use ARM Template to Deploy Lab Environment.
- First, I launched my Azure portal, then in the Azure portal, search Deploy a custom template and press the Enter key.
- On the Custom deployment blade, click the Build your own template in the editor option.
- click on load file, and select the ARM template which is a .json file.
- Upload ARM template (Download template fromAzure AZ500 Github Lab ***https://github.com/MicrosoftLearning/AZ500-AzureSecurityTechnologies/blob/master/Allfiles/Labs/08/template.json***)

![SOC]()

- Edit Template
- Review and Create

![SOC](Deployment successful)


## STEP 2: Configure and Deploy Azure Firewall
- In the Azure Portal, Search Firewall, In the Firewall blade, click Create.

**Configure Firewall settings:**
- Deploy Firewall to specific VNET that was deployed with the ARM Template, and configure public IP and other neccesary settings.

![SOC](Firewall VNET)

## STEP 3: Create a default route for our workload subnet, (this route will configure outbound traffic throught the firewall.)
- In the Azure Portal, Search Route Tables, and create a new route.
- configure and create new route Table.
- click create, and wait for the provisioning to complete.

![SOC](Route Table)


**NEXT** Associate the Firewall Route to a Subnet ***Workload-SN***  
- On the Route tables blade, click Refresh, and, in the list of route tables, click the Firewall-route entry.
- On the Firewall-route blade, in the Settings section, click Subnets and then, on the Firewall-route | Subnets blade, click + Associate.
- On the Associate subnet blade, specify the following settings:
- Click OK to associate the firewall to the virtual network subnet.

![SOC]( ASSOciate Subnet)

**NEXT** Associate The Firewall Route to a Route
- Back on the Firewall-route blade,
- In the Settings section, click Routes and then click + Add.
- On the Add route blade, specify the following settings: ***This route, automatically lists the Firewall’s private IP Address as the next hop address when sending out traffic out of the subnet.***
- This way, all traffic gets routed through the Azure Firewall first.
-  Click Add to add the route.

![SOC]( Add Route)

## STEP 4: Configure the Application and Network rule on the Azure Firewall to specifically allow certain applications and send request to specific DNS Servers.

** I'll be creating an application rule that allows outbound access to www.bing.com.**
- Now back to the Test-FW01 firewall, On the Test-FW01 blade, in the Settings section, click Rules (classic).
- click the Application rule collection tab, and then click + Add application rule collection.
- In the Application rule, I set the target FQDN to bing.com, ***since it’s the only domain we want every machine on our Subnet to be able to connect to, with source IP being the Subnet IP address range.***
- Click Add to add the Target FQDNs-based application rule.

![SOC](App Rule for Bing)

**NEXT** Create and Configure a Network Rule
- 





  

