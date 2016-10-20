# Use REST APIs to access mailboxes in Exchange hybrid deployments (preview)

Microsoft Graph has always provided access to customer mailboxes in the cloud on Exchange Online as part of Office 365.
Exchange 2016 Cumulative Update 3 (CU3), released in September 2016 for Exchange on-premises servers, adds support for 
REST API integration with Office 365. If your app uses v1.0 of the 
[Mail](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/message), 
[Calendar](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/calendar), or 
[Contacts](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/contact) API, you will now also find a seamless 
authentication and application experience in _hybrid_ deployments, regardless of whether the mailbox 
is on-premises or in the cloud, provided that the deployment meets specific [requirements](#requirements-for-rest-api-to-work-in-hybrid-deployments). 


Behind the scenes, when Microsoft Graph identifies that a REST API call is attempting to access an on-premises 
mailbox in a hybrid deployment, it proxies the REST request to an on-premises REST endpoint which then processes
the request. This discovery makes accessing the REST API possible.

>**Note:** The ability to use these REST APIs in hybrid deployments is currently in preview.

>Only v1.0 of the Mail, Calendar and Contacts API are available for mailboxes in hybrid deployments. Other v1.0 API sets, 
such as the [Groups](http://graph.microsoft.io/en-us/docs/api-reference/v1.0/resources/group) API, or APIs in other versions, 
are not. If you attempt to use an API that is not part of the supported set in a hybrid deployment, you will get the following error message:

>"REST APIs for this mailbox are currently in preview. You can find more information about the preview REST APIs at https://dev.outlook.com."

## Requirements for the REST API to work in hybrid deployments

Microsoft Graph provides openness (open standards support like JSON, OAUTH and ODATA, connecting from most popluar platforms)
and flexibility (granular, tightly scoped permissions to access user data). 
If your organization is interested in enabling Microsoft Graph app development and is currently in or considering a hybrid deployment, 
be aware of the following deployment requirements:

- Mailbox requirements

  - All on-premises mailboxes that will use the REST APIs must be located on databases located on Exchange 2016 CU3 servers. 

- Infrastructure requirements

  - All Exchange 2016 servers must be upgraded to CU3 or later.  
  - On-premises Active Directory must synchronize with Azure Active Directory.
  - Any Exchange 2013 servers coexisting in the same load-balanced array with Exchange 2016 servers must be removed from the array.

- Networking requirements

  - From a DNS perspective, the Autodiscover namespace and on-premises client namespace must have Internet DNS records. 
  - If you have a firewall or application gateway that inspects and restricts access, update the appropriate settings to allow discovery and access.


IT administrators can find more information in the following resources:

- [Exchange Server Hybrid Deployments](https://technet.microsoft.com/en-us/library/jj200581(v=exchg.150).aspx)
- [September 2016 Cumulative Update Release](https://blogs.technet.microsoft.com/exchange/2016/09/20/released-september-2016-quarterly-exchange-updates/) 
- [On-Premises Architectural Requirements for the REST API](https://blogs.technet.microsoft.com/exchange/2016/09/26/on-premises-architectural-requirements-for-the-rest-api/)
