# AZ-104
Study notes for the Azure Admin exam
<p>https://learn.microsoft.com/en-us/certifications/exams/az-104</p>
<h1>Pre-reqs for Admins</h1>
<h3>Azure Resource Manager</h3>
<p>
<ul>
<li>Organizes the company's resources</li>
<li>Enables you to work with the resources in your solution as a group</li>
<li>Deploy, Update and Delete in a single corrdinated operation with templates</li>
<li>Use templates for deployment testing, staging, production</li>
<li>Provides security, auditing, & tagging</li>
<li>Consistent management layer for portal, PowerShell, CLI, Rest API</li>
<li>Apply access control to all services in your resource group because RBAC</li>
</ul></p>

<h3>Resource Groups</h3>
<p>
<ul>
<li>Resources can only exist in one group</li>
<li>Resource groups cannot be renamed</li>
<li>All resources should share the same lifecycle</li>
<li>Resources can be moved to different groups and be in different regions</li>
</ul></p>

<h3>ARM Locks</h3>
<p>
<ul>
<li>Locks can be associated with a subscription, resource group, or resources</li>
<li>2 types: Read-Only and Delete Locks</li>
<li>Only the owner or admin can create or delete locks</li>
</ul></p>

<h3>ARM Templates</h3>
<p>
<ul>
<li>Improves consistency</li>
<li>Helps express complex deployments</li>
<li>Reduce manual, error-prone tasks</li>
<li>Reuseable, linkable, simple orchestration</li>
<li>Written in JSON to express data stored as an object. Values can be a string, number, Boolean expression, list of values, or object</li>
<li>ARM templates allow you to specify your projects infrastructure.</li>
<li>Template structure: schema (required), contentVersion, apiProfile, parameters, variables, functions, resources, output (optional section)</li>
</ul></p>

<h3>Bicep Templates</h3>
<p>
<ul>
<li>Written in DSL(domain specific language)</li>
<li>Use instead of JSON to develop your ARM templates</li>
<li>You submit the Bicep template to resource manager which still requires JSON</li>
<li>Simples syntax, modules, auto dependency, IntelliSense</li>
<li>If resources already exists and no change is detected, no action is taken. If property is changes, the resource is updated</li>
</ul></p>

<h1>Manage identities and governance in Azure</h1>
<p>
<ul>
<li>Access to Azure resources is controlled through user accounts and identities that are defined in Azure AD. Every user needs an Azure user account for resource use.</li>
<li>Azure AD supports 3 types of user accounts: 1) Cloud Identity - defined only in Azure AD 2) Directory-Synced - defined in on-prem AD 3) Guest User - defined outside Azure</li>
<li>Several ways to add cloud identity user accounts in Azure AD: Azure portal, M365 Admin Center, Intune, Azure CLI</li>
<li>Bulk upload: Only Global admins or User admins have privileges to create/delete comma-separated values (CSV)</li>
<li>Group Accounts:</li>
<p><ol><li>Security groups: used to manage member and computer access; set permissions for all group members at the same time</li>
<li>M365 groups: provide collaboration opportunities; shared mailbox, calendar, files, SharePoint site, etc.</li></ol></p>
</ul></p>

<h3>Subscriptions</h3>
<p>
<ul>
<li>Subscriptions are a logical unit of Azure services that are linked to an Azure account.</li>
<li>Multiple subscriptions can be linked to the same Azure account. More than one Azure account can be linked to the same subscription.</li>
<li>Subscription types: Free, Pay-As-You-Go (monthly billing), Enterprise, Student</li>
<li>Cost Management: shows organizational cost and usage patterns with advanced analytics. Monitors subscription billing and resource usage.</li>
<li>Apply resource tagging to organize Azure resources by categories</li>
<li>Apply cost savings to help you gain significant cost savings for you: Reservations, Azure hybrid benefits, Azure credits, Budgets, Pricing calculator</li>
</ul></p>

<h3>Azure Policy</h3>
<p>
<ul>
<li>Create management groups to efficiently manage multiple subscriptions. You can create a management group with Axure Policy by using the Azure portal, PowerShell, or the Azure CLI.</li>
<li>Management groups have a directory unique identifier and a display name. This ID is used to submit commands on the management group. It cannot be changed after it's created.</li>
 <li>Specifiy the resource types that you can deploy with Azure Policy</li>
<li>Advantages:</li>
  <p><ol>
  <li>Enforce rules and compliance</li>
  <li>Apply policies at scale</li>
  <li>Perform remediation</li>
  <li>Exercise governance</li>
  </ol></p>
 <li>Policy definition - describes compliance and the actions to complete when the conditions are met. Multiple policy definitions are called initiative definitiion</li>
 <li>4 Steps to create policy definitions:</li>
 <p><ol>
  <li>Create policy definitions - some are built-in</li>
  <li>Create an initiative definition - use JSON format, also some built-in initiatives</li>
  <li>Scope the initiative definition - control how it is applied to resources; limit the scope</li>
  <li>Determine compliance</li>
</ol></p>
 </ul></p>

<h3>RBAC</h3>
<p>
<ul>
<li>RBAC helps you manage who can access your Azure resources. For example, allowing users to manage VMs in a subscription and allow another to manage vnets</li>
 <li>Concepts: </li>
 <ol>
  <li>Security principal</li>
  <li>role definition - sets of permissions that are defined in a JSON file. Each permission set has a name: <b>Actions, NotActions, DataActions, AssignableScopes</b></li>
  <li>Scope - specify how the role can be assigned</li>
  <li>Assignment - limits permissions for a requestor (user, group, service principal)</li>
 </ol>
 <li>3 types of access management roles: </li>
 <ol>
  <li>Classic subscription admin roles - manage access to Azure resources</li>
  <li>Azure RBAC roles - defined for a requestor or resource; applied at multiple levels (root, subscriptions, resource group, etc)</li>
    <li>Azure AD admin roles - manage resources in Azure AD (users, groups, domains)</li>
 </ol>
</ul></p>

<h3>SSPR or self-service password reset</h3>
<p>
<ul>
<li>Reduces the load on admins by allowing users to fix password problems themselves</li>
<li>Customizable</li>
<li>Verify the identity of the user by: localization, notification, verification, authentication, password reset</li>
</ul></p>


<h3>Azure AD</h3>
<p>
<ul>
<li>Multi-tenant cloud-based directiory. Helps support user access to resources and apps internal and external</li>
<li>Secure access with SSO, MFA, Federation services</li>
<li>Self-service support. No organization units or group policy objects (GPOs) </li>
 <li>Azure AD editions</li>
 <ol>
  <li>Free - user and group management, SSO</li>
  <li>M365 apps -IAM for M365 apps </li>
  <li>P1 - on-prem and cloud resource access, dynamic groups, self-service group management</li>
  <li>P2 - Azure AD identity protections, conditional access, just-in-time access</li>
 </ol>
 <li><b>Azure AD join</b> - provides access to org apps and resources. Connect your device to Azure AD by registing and joining</li>
</ul></p>

<h1>Implement and Manage Storage in Azure</h1>
----------------------------
<h3>Storage Accounts</h3>
<p><ul>
 <li>Azure storage can be used to store files, messages, tables, etc. It is used by IaaS VMs and PaaS cloud services.</li>
 <li>2 tiers : Standard (HDD) and Premium (SSD)</li>
 <li><b>Storage services:</b> </li>
 <ol>
 <li>Azure Blob Storage (containers): A massively scalable object store for text and binary data; access using the NFS protocol; can be accessed from anywhere in the world</li>
 <li>Azure Files: Managed file shares</li>
 <li>Azure Queue Storage: A messaging store for reliable messaging between app components; 64 KB</li>
  <li>Azure Table Storage (Cosmos DB): A NoSQL store for schemaless storage of structured data or relational data</li>
 </ol>
 <li><b>Account Types: </b></li>
 <ol>
 <li>Standard general - purpose V2 </li>
 <li>Premium block blobs - Blob Storage </li>
 <li>Premium file share - Azure files</li>
 <li>Premium page blubs- Page blobs only</li>
 </ol>
 <li><b>Replication Strategies: </b></li>
 <ol>
 <li>Locally redundant storage (LRS) - data easily restructured after loss, constantly changing, app is restricted to replication with a country or region</li>
<li>Zone redundant storage (ZRS) - not available in all regions, requires physical data movement, resides in its own AZ</li>
<li>Geo-redundant storage (GRS) - replicates your data to another data center in secondary region, data is read-only, 16 9s durability</li>
<li>Geo-zone-redundant storage (GZRS) - high availability, data is durable during a complete regional outage or disaster</li>
</ol>
 <li>Configure custom domains to storage accounts with direct mapping (CNAME) or Intermediary domain mapping (asverify)</li>
 <li>Firewalls and vnets can restrict access to your storage account from specific subnets. Configure the service to allow acces to one or more public IP ranges. The subnets and vnets nust exist in the same Azure region or region pair as the storage account.</li>
</ul></p>

<h3>Azure Blob Storage</h3>
<p><ul>
 <li>Stores any type of text or binary data: text documents, images, video files and app installers</li>
 <li>Good for accessing data from anywhere. Ideal for streaming and random-access.</li>
 <li>3 resources to store and manage data: Azure storage account, containers, blobs in container</li>
 <li>All blobs must be in a container. Containers store an unlimited number of blobs. Azure accounts store an unlimited number of containers.</li>
 <li><b>3 tiers: </b></li>
  <ol>
 <li>Hot tier- frequent reads and writes of objects</li>
 <li>Cold tier - large amounts of data that is infrequently accessed</li>
   <li>Archive tier - offline, several hours of retrieval latency, data must remain in Archive for at least 180 days or it's deleted.</li>
  </ol>
 <li>Configure lifecycle management policy rules to transition or expire data based on needs <b>"If - Then"</b></li>
 <li><mark>Blob object replication</mark> requires blob versioning on source and destination accounts. Doesn't support blob snapshots.</li>
 <li><b>Blob Types: </b>Block blobs, Append blobs, Page blobs. After it's created, you cannot change the type</li>
   </ul></p>

<h3>Storage Security</h3>
<p><ul>
 <li><b>Characteristics: </b></li>
 <ol>
 <li>Encryption - data is encrypted automatically and decrypted before it's retrieved. All data is encrypted through 256-bit advanced encryption standard (AES)</li>
 <li>Authentication</li>
 <li>Data in transit</li>
 <li>Disk encryption</li>
  <li>Shared access signatures - uniform resource identifier(URI) that grants <b>RESTRICTED</b> access rights to storage resources; time interval access, read & write permissions; <b>2 Types: </b>account level (delegates to multiple storage services) and service level (delegates in only one storage service). You can configure IP addresses and specific protocols to accept the SAS</li>
  <li>Authorization</li>
 </ol>
 <li> Always use HTTPS for creation and distribution. Require clients to auto renew the SAS. Define minimum access permissions for resources </li>
 <li>Use access keys for prod apps. <b>Access keys provide unrestricted access to the storage resources</b></li>
</ul></p>


<h3>Azure file shares and blob data</h3>
<p><ul>
 <li>Azure files uses SMB protocol port 445. Stores data as true directory objects in file shares. </li>
 <li>Apps that run in Az VMs or cloud services can mount an Azure files storage to access file data</li>
 <li>Supplement on-prem with Azure Files. Ideal for lift and shift application</li>
 <li>Enable secure transfer. Azure Files has the capability to share snapshots of file shares.</li>
 <li>Cloud tiering: File sync enables you to cache several Azure Files. Backs up your on-prem data. Restores file metadata immediately and recall rapidly</li>
 <li>Steps for deploying Azure File Sync:</li>
 <ol>
  <li>Deploy the storage sync service</li>
  <li>Prepare each Windows Server to use Azure File Sync</li>
  <li>Install Azure File Sync Agent</li>
  <li>Register each Windows Server with the Storage Sync service</li>
 </ol>
</ul></p>


<h3>Azure Storage Explorer</h3>
<p><ul>
<li>MAnage multiple storage accounts in multiple subscriptions and use the Storage Emulator or Azurite to connect to Azure Storage types.</li>
 <li>Requires both management and data layer permissions to allow full access to resources. Azure AD permissions need to allow full access. </li>
 <li>Connect to storage account associated with your Azure subscriptions, services that share other Azure subsciptions, manage local storage by using the Azure storage emulator</li>
 <li>Attach a storage account and a service with a SAS</li>
 <li>Attach external storage accounts so storage accounts can be easily shared - Account name and Account key is needed for connection</li>
 <li>Create Azure import/export job to import/export data from physical disks into Azure Blob and vice versa</li>
 <li>Securely transfer large amounts of data to Azure Blob Storage or Azure Files</li>
 <li>WAImportExport is used to prepare drives before importing data and repair corrupted and missing files after data transfer. </li>
 <li>AZCopy - method for transferring data, command-line utility for copying data to and from Azure Blob and Azure Files. Supports Azure data lake storage and is built into <b>Azure Storage Explorer</b></li>
</ul></p>


<h3>Azure Storage with SAS</h3>
<p><ul>
 <li>files are accessed by HTTP/HTTPS. </li>
 <li>4 options for blob storage: </li>
 <ol>
 <li>public access - anonymous public read access for containers and blobs</li>
 <li>Azure AD - securely access Azure storage without storing any credentials in your code. Takes a two-step approach by authenticating a token to pass to Azure Storage</li> 
 <li>shared key - 512 bit access keys for every storage account that is created</li> 
 <li>SAS - lets you grant read-only or read-write access, expiration time, etc. Permission to a storage resource.</li>
 </ol>
</ul></p>


---------------------------
<h1>Deploy and manage Azure compute resources</h1>
----------------------------
<h3>Configure VMs</h3>
<p><ul>
 <li>Azure VMS are the basis of IaaS. VMs provide their own OS, storage and networking.</li>
 <li>Quickly Scale up and Down on demand and pay for what you use.</li>
 <li>Running websites and applications can be less expensive</li>
 <li>VNets pride private connectivity between VMs. Services within the same vnet can access one another.</li>
 <li>Location can limit your options. Regions have different hardware available.</li>
 <li>You can resize the VM but be cautious as this can cause an outage</li>
  <li>All VMs have at least two disks, OS disk and temporary disk. All disks are stored as virtual hard disks (VHD)</li>
 <li>Choose Premium storage to gain high performance. Using multiple disks gives you up to 256 TB of storage per virtual machine.</li>
 <li>Use RDP to connect to Windows servers and SSH to connect to Linux-based VMs. The public key is placed on your Linux VM. Private key remains on your local system.</li>
 <li>Azure Bastion is a PaaS service that provides secure and seamless RDP?SSH connection to you VMs over SSL. You don't need a public IP address.</li>
 <li>Default network settings allows all outboud traffic but no inbound unless it's within the vnet.</li>
<li>Availability sets ensure that a group of VMs are deployed together and prevent single point of failure. All VMs in a set should perform an identical set of functionalities. VMs can only be added to an availability set when the VM is created. </li>
<li>Fault domains - group of nodes that represent a physical unit of failure. Defines a group of VMs that share a common set of hardware (or switches). Two fault domains work together to mitigate against hardware failures, network outages, updates, etc.</li>
<li>Availability Zones (AZs) - High availability that protects your apps and data from failures. This is a combinations of fault domains and and update domain. These are unique physical locations within a region, made up of one or more datacenters.</li>
<li>Vertical Scaling - Scaling up or down to decrease or increase the VM <b>size</b></li>
<li>Horizontal Scaling - Scale out or Scale in to adjust the <b>number</b> of VMs</li>
<li>Scale Sets - used to deploy and manage a set of identical VMs to auto increase the number of your VMs based on demand and decrease as demand decreases.</li>
<li>Autoscale - allows you to dynamically scale your configs to meet changing workload demands.</li>
</ul></p>


<h3>Virtual machine extensions</h3>
<p><ul>
 <li>VM extensions are small apps that provide post-deployment confis and auto tasks for Azure VMs. They manage your VMs</li>
 <li>Use Azure CLI, PowerShell ARM templates and the portal to manage extensions</li>
 <li>Can be a subset of a larger deployment for your VM</li>
 <li>You can also use PowerShell command to run scripts with Custom Script Extensions. Requires URI.</li>
 <li>Desired state configs - management platform in Windows PowerShell to enable deploying and managing config data for software services and the environment. Provides a set of PowerShell language extensions, cmdlets and resources</li>
 <li>Custom scripts time out at 90 minutes</li>
</ul></p>


<h3>Azure App Service Plans</h3>
<p><ul>
 <li>App Service plan is the scale unit of App Service applications. Apps run and scale in a different manner</li>
 <li>Free or Shared tier - Apps can't scale</li>
 <li>Basic, Standard, Premium or Isolated - Apps run on all VM instances configured. Multiple apps in the same plan share the same VM instances.</li>
 <li>I solate your app in a new App Service plan when the app is resource-sensitive or you want to scale independently</li>
 <li>Scaling up increases the amount of CPU, memory and disk space but gives you extra features like dedicated VMs and custom domains and certs.</li>
 <li>Consider testing your web app by using Free Tier then move up manually. Autoscale to support users and reduce costs</li>
 <li>Autoscale allows you to have the right amount of resources to handle the load on your apps: There is metric-based and time-based rules (schedule-based)</li>
</ul></p>



<h3>Configure Azure App Service</h3>
<p><ul>
 <li>Provides Quickstarts for serveral products to help you deploy Windows and Linux apps.</li>
 <li>Multiple languages, DevOps optimization, Global scale with high availability, connections to SaaS platforms & on-prem data, security & compliance</li>
 <li>Names for apps must be unique, operating system can be Linux or Windows, the Region you choose affects the Service plans available</li>
 <li>Always on, encryption at rest and transmitted</li>
 <li>Continuous deployment pushing out new features & bug fixes in a fast and repetitive pattern w/ minimal impact on end users (Azure DevOps, GitHub, Bitbucket)</li>
 <li>Deployment slots - live apps that have their own hostnames. Available in Standard, Premium and Isolated App Service pricing tiers. Validate changes to your app in staging, restore last known good site, Auto Swap when you want to deploy your app continuously with zero cold starts and zero downtime for app customers</li>
   <ol><li>When you clone a configuration, connection strings follow the content</li></ol>
 <li>Azure Application Insights - lets you monitor live applications to contiuously improve the performance and usability of apps</li>
</ul></p>



<h3>Azure Container Instances</h3>
<p><ul>
 <li>Virtualize the Operating System to run multiple applications within the same instance of an OS while maintaining isolation</li>
 <li>Increased flexibility and speed. Simplifies testing</li>
 <li>Can be directly exposed to the internet with an IP address & FQDN</li>
 <li>Container Groups - collection of containers that share a lifecycle, resources, local network and storage volumes.</li>
 <li>Two common ways to deploy a multi-container group: ARM templates and YAML</li>
 <li>Container groups can share an external-facing IP address, one or more ports, and a DNS label with a FQDN</li>
 <li>Docker - enables developers to host apps within a container. A container in Docker is essentially a standalone package that contains everything needed to execute a pece of software. Available in both Linux and Windows. Dockerfile is a test file on how to build a Docker image. "docker build" command builds images. Pull/Push</li>
</ul></p>



<h3>Azure Kubernetes Service (AKS)</h3>
<p><ul>
 <li>Azure operates as a hosted Kubernetes service and performs critical functions like health monitoring and maintenance.</li>
 <li>Kubelet Agent - processes the orchestration requests from the Azure managed node</li>
 <li>ClusterIP service - create an internal IP address for use within the AKS cluster</li>
 <li>Pools - A group os nodes w/identical configuration</li>
 <li>Nodes - Individual VM that runs containerized apps</li>
 <li>Pods - Single instance of an app; can contain multiple containers</li>
 <li>Container - A lightweight & portable image that contains software and its dependencies</li>
 <li>Deployment - One or more identical pods</li>
 <li>Manifest - YAML file that describes a deployment</li>
 <li>Nodes are instances of Azure VMs. Connected to a virtual network which provides inboung and outbound connectivity</li>
 <li>Network traffic can be distributed by using a load balancer. Complex routing of app traffic can be achieved with Ingress Controllers.</li>
 <li>Your app workload uses local, fast data storage on a node that's not needed after the pods are deleted. Multiple pods share the same data volumes or reattach data volumes if the pod if rescheduled on a different node</li>
 <li>Azure Disks can use Azure Premium storage backed by a high-performance SSDs or Azure Standard storage. Azure Files to mount an SMB 3.0 share backed by an Azure storage account to pods. Backed by regular HDDs</li>
</ul></p>

<h1>Monitor and back up Azure resources</h1>
<h3>Configure file and folder backups</h3>
<p><ul>
 <li>Offers 2 types of replication: LRS and GRS</li>
 <li>Recovery Services vault (<b>REQUIRED</b>)-  storage entity that backups data for Azure services such as IaaS VMs and Azure SQL databases. Create up to 500 recovery services vaults per Region</li>
 <li>Steps:</li>
 <ol>
  <li>Create the recovery services vault</li>
 <li>Download the agent credential file</li>
 <li>Install and register agent</li>
  <li>Configure the backup</li> </ol>
 <li>Azure Backup relies on the Microsoft Azure Recovery Services (MARS) agent to be installed on the Windows client/server</li>
</ul></p>


<h3>Configure VM backups</h3>
<p><ul>
 <li>Several backup options: Azure Backup, Azure Site Recovery, Managed disk snapshots</li>
 <li>Images vs Snapshots: a snapshot is a copy of a disk at the point in time the snapshot was taken. An image includes all of the disks attached to the VM.</li>
 <li>Backup VMs:</li>
 <ol>
 <li>Create a recovery services vault</li>
 <li>Use the portal to define the backup</li>
  <li>Backup the VM</li> </ol>
 <li>MABS for snapshots, full flex</li>
 <li>Azure Site Recovery - ensures business continuity by keeping apps and workloads running during outages. Set up and manage replication and failover. </li>
 <li>Soft delete state only retains data for 14 days</li>
</ul></p>

<h3>Configure Azure Monitor</h3>
<p><ul>
 <li>Monitor and visualize metrics,Query and analyze logs, Setup alerts and actions.</li>
 <li>Azure Monitor log data is organized in tables</li>
 <li> data can be used to determine the performance, health, and availability of your business application and the resources that it depends on.</li>
 <li>Metrics are numerical values that describe some aspect of a system at a particular point in time. </li>
 <li>Logs contain different kinds of data organized into records with different sets of properties for each type. Stored in Log Analytics</li>
 <li>Azure Monitor can collect log data from any REST client using the Data Collector API.</li>
 <li>Azure Activity Log is a subscription log that provides insight into subscription-level events that have occurred in Azure. determine the ‘what, who, and when’ for any write operations (PUT, POST, DELETE) taken on the resources in your subscription </li>
 <li>Activity logs are kept for 90 days.</li>
</ul></p>


<h3>Configure Azure alerts</h3>
<p><ul>
 <li>Alerts use action groups that can be reused in multiple groups</li>
 <li>Alert creation across Azure Monitor, Log Analytics and Application Insight</li>
 <li>Alert States: New, Acknowledged, Closed</li>
 <li>Target can be any Azure resource (VM, storage account, VM scale set, Log Analytics workspace, etc)</li>
 <li>Signal - Metric, Activity Log, Application Insights, Log</li>
 <li>Alert rule consists of : Resource, Condition, Actions, Alert Details</li>
</ul></p>


<h3>Configure Log Analytics</h3>
<p><ul>
 <li>Log Analytics is a service in that helps you collect and analyze data generated by resources in your cloud and on-premises environments</li>
 <li>Log queries help you to use the data collected in Azure Monitor Logs. </li>
 <li>To get started with Log Analytics you need to add a workspace.</li>
 <li>The basic structure of a query is a source table followed by a series of operators separated by a pipe character |. </li>
 <li>Some common query tables are: Event, Syslog, Heartbeat, and Alert.</li>
 <li>The Heartbeat table reports on agent health.</li>
 <li>count - Returns the number of records in the input record set.</li>
 <li>limit - Return up to the specified number of rows.</li>
 <li>top - Returns the first N records sorted by the specified columns.</li>
</ul></p>

<h3>Configure Network Watcher</h3>
<p><ul>
 <li>Network Watcher provides tools to monitor, diagnose, view metrics, and enable or disable logs for resources in an Azure virtual network</li>
 <li>Monitor and diagnose networking issues without logging in to your virtual machines (VMs) using Network Watcher. </li>
 <li>Gain insight into your network traffic using flow logs.</li>
 <li>Diagnose VPN connectivity issues.</li>
 <li>Verify IP Flow - Checks if a packet is allowed or denied to or from a virtual machine. enables you to specify a source and destination IPv4 address, port, protocol (TCP or UDP), and traffic direction (inbound or outbound).</li>
 <li>Next Hop Purpose: To determine if traffic is being directed to the intended destination. Next hop information will help determine if network routing is correctly configured.  returns the route table associated with the next hop</li>
</ul></p>


<h3>Montior performance with Azure Monitor VM Insights</h3>
<p><ul>
 <li>Azure Monitor VM Insights is a feature of Azure Monitor that relies on Azure Monitor Logs. Allows deeper performance analysis of a virtual machine without query building.</li>
 <li>Azure Monitor VM Insights use a table named InsightsMetrics.</li>
 <li>Azure Monitor captures monitoring data from the following sources:</li>
<ol>
 <li>Application</li>
 <li>Guest OS</li>
 <li>Azure resources</li>
 <li>Azure subscriptions</li>
<li>Azure tenant</li>
 </ol>
 <li>Compute resources in Azure require many agents to help collect monitoring data inside Log Analytics and Azure Monitor</li>
</ul></p>

<h1>Configure and Manage VNets</h1>
<h3>Network Security Groups</h3>
<p><ul>
 <li>Contain a list of security rules that allow/deny inbound or outbound network traffic</li>
 <li>Associated with a subnet or network interface card (NIC)</li>
 <li>Source: controls inbound traffic.</li>
 <li>Destination: controls outbound traffic</li>
 <li>Service: destination protocol and port range</li>
 <li>DMZ acts as a buffer between resources within you VNet and the internet</li>
 <li>Default rules deny all inbound and allow all outbound. You cannot remove the default security rules.</li>
 <li>Each rule has a priority value. <b>The lower the number, the higher the priority.</b></li>
 <li>For inbound traffic, NSG rules are processed then any associated network interfaces. Outbound traffic is the opposite.</li>
 <li>Inbound traffic: rules on the NIC or subnet, overrule the NSG in the same VM. Must define a rule on the NIC and subnet to deny all inbound traffic</li>
 <li>Outbound traffic: Default allows all outbound to the internet. If an NSG is on the subnet or NIC, these rules override the default. Must define a rule on the NIC and subnet to deny all outbound traffic.</li>
</ul></p>

<h3>Azure Firewall</h3>
<p><ul>
 <li>cloud-based network security service that protects your Azure Virtual Network resources. It's a fully stateful firewall </li>
 <li>Azure Firewall uses a static public IP address for your virtual network resources. External firewalls identify traffic originating from your virtual network by the IP address.</li>
 <li>Azure Firewall lets you limit outbound HTTP/S traffic or Azure SQL traffic to a specified list of fully qualified domain names (FQDN) including wild cards</li>
 <li> the recommended approach is to implement a hub-spoke network topology. The hub is a virtual network in Azure that acts as a central point of connectivity to your on-premises network. Spokes are virtual networks that peer with the hub, and can be used to isolate workloads</li>
 <li> three kinds of rules you can configure for Azure Firewall: NAT, network, and application</li>
 <li>An application rule to filter traffic based on an FQDN address</li>
</ul></p>

<h3>Configure Azure DNS</h3>
<p><ul>
 <li>Azure DNS enables you to host your DNS domains in Azure. Azure applies an initial domain name to your initial domain instance. Custom domain name provides a simplified form of your domain name to support specific users or tasks. Must be globally unique</li>
 <li>DNS record can be MX - mail exchange or TX - text </li>
 <li>Azure DNS - reliable and secure DNS service to manage and resolve domain names in a VNet. Multiple DNS zones can have the same name, but must exist in different suscriptions or resource groups</li>
 <li>DNS record set- collection of records in a DNS Zone</li>
 <li>Azure Private DNS </li>
 <li>A or AAAA maps an IP address to a domain. </li>
</ul></p>


<h3>Azure VNet Peering</h3>
<p><ul>
 <li>Enables you to seamlessly connect two Azure VNets. Afterwards, the 2 VNets operate as a single network for connectivity purposes.</li>
 <li>Two types:</li>
 <ol>
 <li>Regional - connects Azure VNets that exist in the same region</li>
 <li>Global - connects Azure VNets that exist in different regions. Not permitted in Azure Govt.</li></ol>
 <li>Azure VPN Gateway - VNet can only have one VPN Gateway. Gateway transit is supported for both regional and global vnet peering.</li>
 <li>Must be Network Contributor or Classic Network Contributor to implement VNets</li>
</ul></p>


<h3>Azure VPN Gateway</h3>
<p><ul>
 <li>VPN gateway is a VNet gateway that send encrypted traffic between your Azure VNET and on-prem location over the <b>public</b> internet. It can also send encrypted traffic between Azure VNets</li>
 <li>Applies encryption BEFORE it reaches the internet through a VPN Tunnel</li>
 <li>Multiple connections can use the same VPN gateway to share the available gateway bandwidth</li>
 <li>VNet gateway is composed of 2 or more VMs that are deployed in a subnet = <b>Gateway Subnet</b>. They cannot be directly configured. The VMs contain routing tables and specific gateway services.</li>
   <ol><li>Gateway subnet contains the IP addresses that are used by your virtual network gateway resources and services</li>
    <li>Network security groups (NSGs) can't be used to create the gateway subnet.</li>
   </ol>
 <li>Site-to-Site config: Create vnets and subnets, Specifiy the DNS server, Configure the VPN device</li>
 <li>Gateway Types:</li>
 <ol>
  <li>Route-based VPNs (Most Common) use routes in the IP forwarding or routing table to direct packets into their corresponding tunnel interfaces. The tunnel interfaces then encrypt or decrypt the packets in and out of the VPN tunnels</li>
  <li>Policy-based VPNs (Only one VPN Tunnel) encrypt and direct packets through IPsec tunnels based on the IPsec policies. The policies are configured with the combinations of address prefixes between your on-premises network and the Azure virtual network.</li>
 </ol>
 <li>Azure VPN Gateway SKU is the most significant implementation decision for the VPN gateway performance</li>
 <li>The shared key provided from the site-to-site VPN connection is required to set up on-prem VPN gateway</li>
</ul></p>


<h3>Azure ExpressRoute and Azure Virtual WAN</h3>
<p><ul>
 <li>Azure ExpressRoute lets you extend your on-premises networks into the Microsoft cloud</li>
 <li>Microsoft network operates the primary and secondary connections of Azure ExpressRoute circuits in active-active mode</li>
 <li>Create private connections between Azure datacenters and infrastructure for your on-premises resources</li>
 <li>ExpressRoute connections enable access to Microsoft Azure services, Microsoft 365 services, and Microsoft Dynamics CRM</li>
 <li>Azure Virtual WAN (wide-area network): networking service that provides optimized and automated branch connectivity to, and through, Azure. Azure regions serve as hubs that you can choose to connect your branches to.</li>
 <li>Azure Virtual WAN brings together many Azure cloud connectivity services, such as S2S VPN, User VPN (P2S), and Azure ExpressRoute</li>
 <li>There are two types of virtual WANs</li>
 <ol>
     <li>Basic: implemented only in an S2S VPN connection</li>
     <li>Standard: implemented with Azure ExpressRoute and a User VPN (P2S). You can also use a Standard WAN with an S2S VPN</li>
 </ol>
</ul></p>



<h3>Configure Routing and Endpoints</h3>
<p><ul>
 <li>Azure uses system routes to control traffic for virtual machines</li>
 <li>A route table contains a set of rules (called routes) that specifies how packets should be routed in a virtual network</li>
 <li>UDRs control network traffic by defining routes that specify the next hop of the traffic flow. Uses route tables. Network virtual appliance (NVA)</li>
 <li> <b>service endpoint</b> provides the identity of your virtual network to the Azure service. After service endpoints are enabled in your virtual network, you can secure Azure service resources to your virtual network by adding a virtual network rule to the resources.Service traffic switches to use virtual network private addresses as the source IP addresses when accessing the Azure service from a virtual network</li>
 <li>Azure Private Link provides private connectivity from a virtual network to Azure platform as a service (PaaS), customer-owned, or Microsoft partner services. Eliminates data exposure to the public internet. keeps all traffic on the Microsoft global network. There's no public internet access. </li>
 <li>Valid "next hop" type would be virtual appliances, internet, virtual network, or none</li>
 <li>Virtual network endpoints - extend the private address space in Azure and restrict the flow of traffic</li>
</ul></p>

<h3>Virtual Networks</h3>
<p><ul>
<li>An Azure virtual network is a logical isolation of the Azure cloud that's dedicated to your subscription. You can use virtual networks to provision and manage VPNs in Azure.</li>
 <li>Subnets - logical divisions within your virtual network to help improve security and performance. IP address space for a subnet must be specified by using CIDR notation </li>
 <li><b>Private IP addresses</b> enable communication within an Azure virtual network and your on-premises network.</li>
 <li><b>Public IP addresses</b> allow your resource to communicate with the internet</li>
 <li>IP addresses are never managed from within a virtual machine. Can be statically assigned or dynamically assigned</li>
 <ol>
 <li>Dynamic addresses are assigned only after a public IP address is associated to an Azure resource</li>
 <li>Static addresses are assigned when a public IP address is created. Static addresses aren't released until a public IP address resource is deleted</li>
 </ol>
</ul></p>

<h3>Load Balancer</h3>
<p><ul>
 <li>Efficiently distribute incoming network traffic across back-end servers and resources. A load balancer is implemented by using load-balancing rules and health probes</li>
 <li>Azure Load Balancer can be used for inbound and outbound scenarios.</li>
 <li>Load-balancing rules are used to specify how to distribute specific types of traffic across multiple virtual machines or services. To configure a load-balancing rule, you need to have a frontend, backend, and health probe for your load balancer</li>
 <li>External load balancers or public load balancers map the public IP addresses and port numbers of incoming traffic to the private IP addresses and port numbers of virtual machines</li>
 <li>internal load balancers direct traffic to resources that reside in a virtual network, or to resources that use a VPN to access Azure infrastructure. VMs must be in the same Virtual Network</li>
 <li>load balancer uses a five-tuple (source IP, source port, destination IP, destination port, and protocol type) hash to map traffic to available servers.</li>
 <li> Azure Load Balancer supports three SKU options: Basic, Standard, and Gateway</li>
  <li>back-end pools contain the IP addresses of the virtual NICs that are connected to your load balancer. When you configure the back-end pools, you can connect to availability sets, virtual machines, or Azure Virtual Machine Scale Sets</li>
 <li> health probe allows your load balancer to monitor the status of your application. The probe dynamically adds or removes virtual machines from your load balancer rotation based on the machine response to health checks</li>
 <ol>
  <li> TCP probe relies on establishing a successful TCP session to a defined probe port</li><li>HTTP probe - the load balancer probes your back-end pool endpoints every 15 seconds. A virtual machine instance is considered healthy if it responds with an HTTP 200 message within the specified timeout period (default is 31 seconds</li></ol>
</ul></p>

<h3>Application Gateway</h3>
<p><ul>
 <li>Azure Application Gateway is a load balancer for web traffic</li>
 <li>An application gateway listens for incoming traffic to web apps and checks for messages sent via protocols like HTTP. Gateway rules direct the traffic to resources in a back-end pool.</li>
<li> Application Gateway distributes requests across multiple servers by using a round-robin technique. uses the hostname, port, and URL path to route requests to a web server</li>
 <li>two primary methods for routing traffic:</li>
 <ol>
 <li>Path-based routing sends requests with different URL paths to different pools of back-end servers</li>
 <li>Multi-site routing configures more than one web application on the same application gateway instance.</li></ol>
 <li>front-end IP address receives the client requests. One or more listeners receive the traffic and route the requests to the back-end pool.</li>
 <li>Routing rules define how to analyze the request to direct the request to the appropriate back-end pool.</li>
<li>A back-end pool contains web servers for resources like virtual machines or Virtual Machine Scale Sets. Each pool has a load balancer to distribute the workload across the resources.</li>
<li>Health probes determine which back-end pool servers are available for load-balancing</li>
</ul></p>

<h3>IP Addressing Schema</h3>
<p><ul>
 <li>On-premises IP addressing</li>
 <ol>
 <li>Routers,Firewalls,Switches,Network segmentation</li>
 </ol>
 <li>Azure IP addressing</li>
 <ol>
 <li>Virtual networks,Subnets,Network security groups,Firewalls,Load balancers</li>
 </ol>
 <li>three ranges of non-routable IP addresses that are designed for internal networks that won't be sent over internet routers:</li>
<ol>
 <li>10.0.0.0 to 10.255.255.255</li>
 <li>172.16.0.0 to 172.31.255.255</li>
<li>192.168.0.0 to 192.168.255.255</li>
 </ol>
 <li>By default, all subnets in an Azure virtual network can communicate with each other. </li>
</ul></p>

<h3>Network Peering</h3>
<p><ul>
 <li>You can use virtual network peering to directly connect Azure virtual networks together. When you use peering to connect virtual networks, virtual machines (VMs) in these networks can communicate with each other as if they're in the same network.</li>
 <li> traffic between virtual machines is routed through the Azure network.</li>
 <li>The traffic uses only private IP addresses. It doesn't rely on internet connectivity, gateways, or encrypted connections</li>
 <li> Using gateway transit, you can enable on-premises connectivity without deploying virtual network gateways to all your virtual networks.Allow gateway transit option  </li>
</ul></p>

<h3> Azure DNS</h3>
<p><ul>
  <li>Azure DNS lets you host your DNS records for your domains on Azure infrastructure</li>
 <li>DNS, or the Domain Name System, is a protocol within the TCP/IP standard. DNS serves an essential role of translating the human-readable domain names, </li>
 <li>When you connect by using your on-premises network, the DNS settings come from your server. When you connect by using an external location, like a hotel, the DNS settings come from the internet service provider (ISP).</li>
 <li>IPv4 is composed of four sets of numbers, in the range 0 to 255, each separated by a dot.</li>
 <li>IPv6 is a relatively new standard and will eventually replace IPv4. It's made up of eight groups of hexadecimal numbers, each separated by a colon.</li>
 <li>record types:</li>
 <ol>
 <li>A - host record, and is the most common type of DNS record. It maps the domain or host name to the IP address. [Multiple]</li>
 <li>CNAME - Canonical Name record that's used to create an alias from one domain name to another domain name.</li>
  <li>MX -  mail exchange record. It maps mail requests to your mail server, whether hosted on-premises or in the cloud</li>
  <li>TX -  text record used to associate text strings with a domain name. Azure and Microsoft 365 use TXT records to verify domain ownership.</li>
 </ol>
</ul></p>



<p><ul>
 <li>Network traffic in Azure is automatically routed across Azure subnets, virtual networks, and on-premises networks. This routing is controlled by system routes</li>
 <li>You can't create or delete system routes, but you can override the system routes by adding custom routes to control traffic flow to the next hop.</li>
 <li>Next hop type</li>
 <ol>
 <li>Virtual Network</li>
 <li>Internet</li>
 <li>None</li>
 </ol>
 <li>A network virtual appliance (NVA) is a virtual appliance that consists of various layers</li>
 <li>A network virtual appliance acts like a firewall. It checks all inbound and outbound traffic, and it secures your environment by allowing or denying the traffic. Customers often create network virtual appliances.</li>
</ul></p>



<p><ul>
 <li> Azure Load Balancer can spread user requests across multiple virtual machines or other services, allowing you to scale the app to larger sizes than a single virtual machine can support, and ensuring that users get service even when a virtual machine fails</li>
 <li>scale applications and create high availability for your virtual machines and services.</li>
 <li>supports inbound and outbound scenarios, provides low latency and high throughput, and scales up to millions of flows for TCP and UDP applications</li>
 <li>you can use availability sets and availability zones to ensure that virtual machines are always available</li>
 <li> availability set is a logical grouping that you use to isolate virtual machine resources from each other when they're deployed</li>
 <li>Availabilty sets allow virtual machines to remain available when a physical server fails.</li>
</ul></p>
