# AZ-104
Study notes for the Azure Admin exam
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

<h3>Manage identities and governance in Azure</h3>
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


<p>
<ul>
<li></li>
<li></li>
<li></li></ul></p>

<p>
<ul>
<li></li>
<li></li>
<li></li></ul></p>


<p>
<ul>
<li></li>
<li></li>
<li></li>
</ul></p>


<p>
<ul>
<li></li>
<li></li>
<li></li>
</ul></p>



<p>
<ul>
<li></li>
<li></li>
<li></li>
</ul></p>
