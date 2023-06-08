# Personalizing the app

## How it works 

XYZ White Label App (`the app`) enables your organization’s users or customers to {do something} thereby {value statement}. 
Normally, we deliver the app with all requested functionality. But the app comes with default appearance. That’s why you may want to update the UI styles and the styles before publishing the app on Google Play and in App Store. 
As an engineer in charge of personalizing the app, you must be proficient in JSON data format. 

# How it works 

This appearance is defined inside a JSON stylesheet file.   
Path to the stylesheet (inside the project): `assets/stylesheet.json` 
You need to update the stylesheet file to personalize the app. 

## How the App defines the styles 

The app's user interface is defined in the view files (folder `assets/views`). Each element is defined by several tags that start with element type and context (location):  

```python
["button", "login-screen"]
```

Then, the app searches inside the stylesheet and selects a set of styles with matching tags.  

Example styles for one element: 

```json
{
    "styles": [
        {
            "rule": {
                "tags": [
                    "button",
                    "login-screen"
                ]
            },
            "properties": {
                "backgroundColor": {
                    "hex": "#00dddd"
                },
                "tintColor": {
                    "hex": "#ffffff"
                },
                "font":  {
                    "fontWeight": "400",
                    "fontFamily": "Arial",
                    "fontSize": "123px"
                }
            }
        }
    ]
}
```

Once the app has gathered the entire selection of styles, it renders the current page.  

As an app engineer, you can change the stylesheet so the app renders updated styles. 

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

