I use the following premise: 

* XYZ (SaaS) provides the customer with an ERP system. 
* The ERP system includes a white label app (XYZ White Label App or *the App*). 
* The white label app is already configured for the customer’s use cases, but it needs to be personalized with custom styles and UX copy.  
* The customer’s admin configures the styles and UX copy via Admin API, say at `/update/styles`. The method is POST, and the admin passes the updated styles in the request body. 
* After the initial API / style update, XYZ can publish the app in Google Play and App Store. After this, the customer can share the links with their end users. 
* The customer’s admin can update the styles and the copy at any moment. 
* The app syncs the styles and the copy on each startup. 

# Before you start 

XYZ White Label App enables your organization’s users or customers to {do something} thereby {value statement}. 
Normally, we deliver the app with all requested functionality. But the app comes with default appearance and text. That’s why we need you to update the UX text, the styles, and the logo before we can publish the application on Google Play and in App Store. 

# How it works

Here at XYZ, we start by configuring the App for your organization's use cases. 
Then, you need to personalize the app: 
* Check the app emulator 
* Update the in-app text (UX copy) 
* Update the styles and the logo 
When done, contact your account manager and arrange the app to be published in App Store and on Google Play.
Now, the end users can install the app and use it.


# Personalizing XYZ White Label App

## How to use the app emulator 

TBD 

## How to update the UX text

TBD

## How to update the logo and the styles 

To update the logo and the styles, you need to use XYZ Admin API. 

To manage the styles, you'll need following endpoints:

* [Get default styles]() 
* [Get current styles]() 
* [Update current styles]() 
* [Reset styles]()

See [XYZ Admin API Reference]() for further information about the endpoints.  

>**Note**:  
>The app syncs the styles and the logo on each startup. 
That means you may change the styles / logo after the app publishing, and you won't need to get the app published again. 


## How to get the app published 

Contact your account manager and confirm that you have configured the styles, the logo, and the UX text. 


