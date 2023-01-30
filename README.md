# AZ-104
Study notes for the Azure Admin exam
<p>https://learn.microsoft.com/en-us/certifications/exams/az-104</p>
<h2>Pre-reqs for Admins</h2>
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

<h2>Manage identities and governance in Azure</h2>
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
