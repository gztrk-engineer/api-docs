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
[Update current styles]() |   |   
[Get default styles]() |   |   
[Get current styles]() |   |   
[Reset styles]() |   |   

## How to specify the styles 



## Endpoints 

### Update current styles  

**Request URL**: {BASE_URL}/update/styles/

Request method: `POST`

This API call accepts an email address and adds it to the Breach Report account. The BR account must be associated with the secret API key (needs to be included in the request header).

The API call returns a response code and a status message including the Email ID.

How to construct the request:

1. Include the API key in the request header.
2. Include the style updates in the request body. See [How to specify the styles] for additional information. 

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


