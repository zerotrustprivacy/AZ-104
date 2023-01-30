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
<li>Consistent management layer for portal, PowerShell, CLE, Rest API</li>
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

<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>




<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>




<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>




<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>



<p><ul>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
 <li></li>
</ul></p>

