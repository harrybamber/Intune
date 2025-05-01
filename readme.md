# Group Membership and Service Health Report Script

This PowerShell script connects to Microsoft Graph and performs the following tasks:

1. Retrieves the member count for a predefined list of Microsoft 365 groups.
2. Generates a report summarizing the group names and their respective member counts.
3. Calculates the total member count across all groups.
4. Retrieves and displays service health issues with a status of `serviceDegradation`.

## Prerequisites

Before running this script, ensure the following:

1. **Microsoft Graph PowerShell Module**: Install the Microsoft Graph PowerShell module by running:
   ```powershell
   Install-Module Microsoft.Graph -Scope CurrentUser

   
App Registration: Register an app in Azure Active Directory and obtain the following:

Tenant ID
Client ID
Client Secret
Permissions: Grant the app the necessary permissions in Azure AD, such as:

Group.Read.All
ServiceHealth.Read.All
PowerShell Execution Policy: Ensure the execution policy allows running scripts:

Usage
Update Credentials: Replace the placeholder values in the script with your app's credentials:

TenantId: Replace with your Azure AD tenant ID.
ClientSecretCredential: Replace with your app's client secret.
Run the Script: Execute the script in PowerShell:

Output:

The script generates a report containing group names and member counts.
It calculates the total member count across all groups.
It retrieves and displays service health issues with a status of serviceDegradation.
Script Details
Group Membership Report
The script defines a list of group display names and retrieves their member counts using the Get-MgGroup and Get-MgGroupMemberCount cmdlets. The results are stored in a report object.

Service Health Issues
The script retrieves service health issues using the Get-MgServiceAnnouncementIssue cmdlet and filters for issues with a status of serviceDegradation.

Example Output
Group Membership Report
Group Name	Member Count
gO365_Lic_v2_Agency_Default	150
gO365_Lic_v2_Employee_Default	300
...	...
Total Member Count: 450

Service Health Issues
Notes
Ensure you have the necessary permissions to access group and service health data in Microsoft Graph.
The script uses the ConsistencyLevel parameter for eventual consistency when querying group member counts.
Disclaimer
Use this script at your own risk. Ensure you understand the operations it performs and have appropriate permissions before running it. ```
