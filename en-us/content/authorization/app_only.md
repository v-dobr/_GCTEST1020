﻿# Call Microsoft Graph in a service or daemon app

This article describes the minimum tasks required to connect your single-tenant service or daemon app to Office 365 and call the Microsoft Graph API.

> Note: This topic covers using Azure Active Directory as the authentication provider for your app. For implementing a service or daemon app using the Azure AD v2.0 endpoint, see <a href="https://azure.microsoft.com/en-us/documentation/articles/active-directory-v2-protocols-oauth-client-creds/" target="_newtab">v2.0 Protocols - OAuth 2.0 Client Credentials Flow</a>.

## Register the application in Azure Active Directory

Before you can start working with Office 365, you need to register your application at the [Azure portal](https://portal.azure.com). Keep in mind the following details:

- After you register the application, configure the application permissions that your service or daemon app requires.
- Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:
	* Application ID (unique to your application)
	* App key, or secret (unique to your application)
	* Your app's OAuth 2.0 token endpoint
	  * Find this value by clicking *View Endpoints* at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/<tenantId>/oauth2/token`.

## Request an access token from the token issuing endpoint

Unlike client apps, your service or daemon app is unable to have a user sign in and authorize your application. Instead, your application has to implement the OAuth 2.0 Client Credentials Grant Flow that lets it use its own credentials, its client ID and an application key, to authenticate when calling the Microsoft Graph instead of impersonating a user. For details about the authentication flow, see [Service to Service Calls Using Client Credentials](https://msdn.microsoft.com/en-us/library/azure/dn645543.aspx).

Make an HTTP POST request to the token issuing endpoint with the following parameters, replacing `<clientId>` and `<clientSecret>` with your app's client ID and application key, respectively.

```http
POST https://login.microsoftonline.com/<tenantId>/oauth2/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials
&client_id=<clientId>
&client_secret=<clientSecret>
&resource=https://graph.microsoft.com
```

The response will include an access token and expiry information.

```json
{ 
  "token_type": "Bearer",
  "expires_in": "3599",
  "scope": "User.Read",
  "expires_on": "1449685363",
  "not_before": "1449681463",
  "resource": "https://graph.microsoft.com",
  "access_token": "<token>"
}
```

## Use the access token in a request to the Microsoft Graph API

With an access token, your app can make authenticated requests to the Microsoft Graph API. Your app must append the access token to the **Authorization** header of each request.

For example, a service or daemon app can retrieve all the users in a tenant if it has the *Read all users' full profiles* permission selected in the Azure Management Portal. 

```http
GET https://graph.microsoft.com/v1.0/users
Authorization: Bearer <token>
```
