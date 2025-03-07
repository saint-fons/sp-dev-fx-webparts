---
page_type: sample
products:
- office-sp
- skype
- office-skype-business
languages:
- javascript
- typescript
extensions:
  contentType: samples
  technologies:
  - SharePoint Framework
  createdDate: 12/1/2017 12:00:00 AM
---
# JavaScript Skype Status Web Part

## Summary
This sample demonstrates how to use the UCWA JS SDK for skype in the SharePoint Framework. It shows how to subscribe to status change of the different people of the organization but you can get much more information, checkout the [documentation](https://msdn.microsoft.com/en-us/skype/websdk/docs/generalreference?f=255&MSPPError=-2147217396)  
The goal is to demonstrate how you can leverage the SDK and to have the simplest approach, hence the usage of JQuery. No Framework (React, Angular, Knockout...) is used here but you can use that SDK in conjuction with any framwork.  
No branding has been applied to keep it simple but you could perfectly leverage Office Ui Fabric to display persona cards.

Allows you to properly display and subscribe to change of users' availability.  
See the demo:  
![demo](./images/demo.gif)


## Compatibility

![SPFx 1.8.0](https://img.shields.io/badge/SPFx-1.8.0-green.svg)
![Node.js v6 | v5](https://img.shields.io/badge/Node.js-v6%20%7C%20v5-green.svg) 
![Compatible with SharePoint Online](https://img.shields.io/badge/SharePoint%20Online-Compatible-green.svg)
![Does not work with SharePoint 2019](https://img.shields.io/badge/SharePoint%20Server%202019-Incompatible-red.svg "SharePoint Server 2019 requires SPFx 1.4.1 or lower")
![Does not work with SharePoint 2016 (Feature Pack 2)](https://img.shields.io/badge/SharePoint%20Server%202016%20(Feature%20Pack%202)-Incompatible-red.svg "SharePoint Server 2016 Feature Pack 2 requires SPFx 1.1")
![Local Workbench Compatible](https://img.shields.io/badge/Local%20Workbench-Compatible-green.svg)
![Hosted Workbench Compatible](https://img.shields.io/badge/Hosted%20Workbench-Compatible-green.svg)


## Applies to

* [SharePoint Framework Developer](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
* [Office 365 developer tenant](https://docs.microsoft.com/sharepoint/dev/spfx/set-up-your-developer-tenant)

## Solution

Solution|Author(s)
--------|---------
js-skype-status|[Vincent Biret](https://github.com/baywet)


## Version history

Version|Date|Comments
-------|----|--------
1.4|March 27th, 2019|Upgrade to SPFx 1.8.0
1.3|November 18th, 2018|Upgrade to SPFx 1.7.0
1.2|July 4th, 2018|Fixed a bug when subscribing to the current user's status
1.1|June 22nd, 2018|Upgraded to SPFx 1.5
1.0|December 1, 2017|Initial release

## Minimal Path to Awesome

### Authentication

Because the Skype API's are secured, you first need to register an Azure Active Directory application.  
To do that go to `portal.azure.com` and sign in as your tenant administrator.  
![azure active directory](./images/1.PNG)  
Click on `Azure Active Directory`.  
![app registrations](./images/2.PNG)  
Click on on `App Registrations` and then `New Application Registration`  
![app details entry](./images/3.PNG)  
Enter any name, select `Web app / API` in `Application Type` and in `Sign-In URL` enter `https://*.sharepoint.com/*`, then click on `Create`  
![app details display](./images/4.PNG)  
Take note of the `application ID`, we'll need it later. Click on `required permissions`.  
![skype permission](./images/5.PNG)  
Click on `add` then `select an API` and select `Skype for Business`.  
![skype scopes](./images/6.PNG)  
Select under `delegated permissions` both `Read/Write Skype user contacts and groups`,  `Read/Write Skype user information (preview)`, `Receive conversation invites (preview)` (the receive conversation permission is required to get access to the mePerson object and have access to the current user's presence information) then click `select`. Finish by clicking `Done`.  
![grant permission](./images/7.PNG)  
Don't forget to click on `Grant permissions` and `yes`.

### Updating the app
After copying that sample to your local machine and running `npm install` to install the depenencies, `/src/webparts/skypePresence/services/Constants.ts` open your favorite editor. Make sure you replace the value of `ApplicationIdKey` to the value application id we kept earlier.  

### Deploying the application

Start by running `gulp package-solution` and deploy the application to the app catalog. More information on how to do it [here](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/get-started/serve-your-web-part-in-a-sharepoint-page)  
**At the end select SkypePresence web part instead**  
Don't forget to run `gulp serve --nobrowser` to start the debugging server.

### Additional page required

Because Skype needs to silently redirect the user to a page for the authentication flow, you need to create an additional page called `skypepresence` in your site.  
You don't need to add anything on that page.  


## Help

We do not support samples, but we this community is always willing to help, and we want to improve these samples. We use GitHub to track issues, which makes it easy for  community members to volunteer their time and help resolve issues.

If you're having issues building the solution, please run [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/) from within the solution folder to diagnose incompatibility issues with your environment.

You can try looking at [issues related to this sample](https://github.com/pnp/sp-dev-fx-webparts/issues?q=label%3A%22sample%3A%20js-skype-status") to see if anybody else is having the same issues.

You can also try looking at [discussions related to this sample](https://github.com/pnp/sp-dev-fx-webparts/discussions?discussions_q=js-skype-status) and see what the community is saying.

If you encounter any issues while using this sample, [create a new issue](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Abug-suspected%2Csample%3A%20js-skype-status&template=bug-report.yml&sample=js-skype-status&authors=@baywet&title=js-skype-status%20-%20).

For questions regarding this sample, [create a new question](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Aquestion%2Csample%3A%20js-skype-status&template=question.yml&sample=js-skype-status&authors=@baywet&title=js-skype-status%20-%20).

Finally, if you have an idea for improvement, [make a suggestion](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Aenhancement%2Csample%3A%20js-skype-status&template=question.yml&sample=js-skype-status&authors=@baywet&title=js-skype-status%20-%20).


## Disclaimer

**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**


![tracking image](https://pnptelemetry.azurewebsites.net/sp-dev-fx-webparts/samples/js-skype-status)
