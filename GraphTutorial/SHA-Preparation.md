# My Preparation Notes

## My Personal Outlook.com Account
Account name: stefan.hannuschke@outlook.com
tbc...

## My Omada Entra ID Account
tbd...

## GitHub "msgraph-sample-aspnet-core" Project

From "[README > Microsoft Graph sample ASP.NET Core app > Prerequisites > Register a web application with the Azure Active Directory admin center](https://github.com/microsoftgraph/msgraph-sample-aspnet-core#register-a-web-application-with-the-azure-active-directory-admin-center)"

### .NET Core SDK (10.0)
SHould be installed since we already have VS 2026 installed, but we can check with `dotnet --version` in a terminal.
```
PS ...> dotnet --version
10.0.101
```
OK. Is installed

### Using "My Outlook.com Account"
Using "My Outlook.com Account" from above for now ...

#### Register a web application with the Azure Active Directory admin center
Open "[Azure Active Directory admin center](https://aad.portal.azure.com)" in Edge "InPrivate" mode.
1. Approve the sign-in with "stefan.hannuschke@outlook.com" in MS Authenticator app on mobile.
1. ![Entra Portal](Images\Entra Portal.png)\
   **Note**: Not sure why this is "Hugo Troll" :(.\
   1.1. Login using "htroll83@gmail.com".\
   1.2. OK. He's the admin for the "Entra ID" tenant ("5b562b96-9706-4648-bac7-a453e65c038b") we need to use for this sample app.\
        The "stefan.hannuschke@outlook.com" seems to be a **guest account** in this tenant. It has the "stefan.hannuschke@gmail.com" email address (which used to be the MS account "primary email address").\
        Let's try to make this (guest) account a "Global Administrator" in this tenant.\
        OK. That's better. We now see (e.g.) "Users" as well as "App registrations" in the left-hand menu and can proceed with registering a new application.\
1. Open "Entra ID" in the left-hand menu, select "App registrations", "New registration" and register a new "ASP.NET Core Graph Tutorial" application.\
   ![Entra App Registration](Images\Entra App Registration.png)\
   Application (client) ID: 654a40bf-c1cd-426d-904a-465116966304\
   Follow steps 4 to 9 in the "[README > Microsoft Graph sample ASP.NET Core app > Prerequisites > Register a web application with the Azure Active Directory admin center]".\
   Save client secret in LastPass "live.com - htroll83" entry.

#### Configure the sample

```
PS ...\msgraph-sample-aspnet-core\GraphTutorial> dotnet user-secrets init
The MSBuild project '...\msgraph-sample-aspnet-core\GraphTutorial\GraphTutorial.csproj' has already been initialized with a UserSecretsId.
PS ...\msgraph-sample-aspnet-core\GraphTutorial> dotnet user-secrets set "AzureAd:ClientId" "654a40bf-c1cd-426d-904a-465116966304"
Successfully saved AzureAd:ClientId to the secret store.
PS ...\msgraph-sample-aspnet-core\GraphTutorial> dotnet user-secrets set "AzureAd:ClientSecret" "<from LastPass>"
Successfully saved AzureAd:ClientSecret to the secret store.
```

# Notes

There is another Entra tenant "sapmeisteraad" where "stefan.hannuschke@outlook.com" is the owner (and global admin). Thenant ID is "e7eae31d-1251-4641-9f39-db13f5e88fba" and Primary domain "stefanhannuschkegmail.onmicrosoft.com".
