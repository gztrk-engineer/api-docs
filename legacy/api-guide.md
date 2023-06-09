# XYZ Admin API Guide 

To access the API, you need the base URL and the API key. 

PARAMETER |	VALUE |	COMMENTS  
---|---|---
Base URL  |	`https://{organization}.xyz-api.com` | 	
`API_KEY` | `your-secret-key` | Include the value in each request header. 

You can manage the API key via [XYZ Admin portal](). See [Managing the API key]() for further info.  

## How to use the API  

To update the styles, you'll need the following endpoints:

ENDPOINT | DESCRIPTION | COMMENTS 
---|---|---  
[Update current styles](#update-current-styles) | Updates the current stylesheet.   |   
[Get default styles](#get-default-styles) | Returns the JSON with default styles.  |   
[Get current styles](#get-current-styles) | Returns the JSON with default styles.  |   
[Reset styles](#reset-styles) | Resets the stylesheet to defaults.  |   

## How the App defines the styles 

The app's user interface is defined in the view files (folder `assets/views`). Each element is defined by several tags, that must start with element type context (location):

```
["button", "login_screen"]
```

The app's backend provides a stylesheet, that is stored in JSON format.  
The app requests the backend, gets a set of styles for each element, and renders the elements on the form. 
As an admin, you can change the stylesheet, so the backend returns updated styles. 

```
 -------                         -------------
|       |   getStyles([tags])   |             |
|       | --------------------> | stylesheet. |
|  App  | <-------------------- |    json     |
|       |  {style properties}   |             |
 -------                         -------------    
                                     ^
                                     |
   ( )                               |
  -----                              |
    |    ---------------------------- 
   / \       update the styles
  Admin
    
```



## Stylesheet description



## Endpoints 

### Update current styles  

**Request URL**: {BASE_URL}/update/styles/

Request method: `POST`

This API call accepts styles updates and adds it to the Breach Report account. The BR account must be associated with the secret API key (needs to be included in the request header).

The API call returns a response code and a status message.

How to construct the request:

1. Include the API key in the request header.
2. Include the style updates in the request body. See [How to specify the styles]() for additional information. 

### Get default styles 

**Request URL**: {BASE_URL}/get/defaults/

Request method: `GET` 

**TBD**

### Get current styles  

**Request URL**: {BASE_URL}/get/styles/

Request method: `GET` 

**TBD**

### Reset styles  

### Get current styles  

**Request URL**: {BASE_URL}/reset/styles/

Request method: `GET` 

**TBD**


