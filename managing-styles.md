# Personalizing the app    

XYZ White Label App (`the app`) enables your organization’s users or customers to {do something} thereby {value statement}. 
Normally, we deliver the app with all requested functionality. But the app comes with default appearance. That’s why you may want to update the UI styles and the styles before publishing the app on Google Play and in App Store.  

# How it works 

This appearance is defined in a JSON stylesheet file, located at: `assets/stylesheet.json` inside the project folder. The same file will be stored locally on your mobile app.  
As an engineer in charge of personalizing the app, you need to update the stylesheet file. To do so, you must be proficient in JSON.  
Also, the style matching logic is somewhat similar to HTML / CSS, so knowledge of these technologies is useful as well. 


## How the app defines the styles 

The app's user interface is defined in the view files (folder `assets/views`). Each element is defined by several tags, start with element type and context (location):  

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

## Updating the styles and the logo

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

After updating the stylesheet, you need to re-assemble the app and publish it on Google Play and in Apple Store.  

> **Learn more**:   
> * [Stylesheet Specification](stylesheet-spec.md#stylesheet-format)  
> * [Style Matching Logic](stylesheet-spec.md#style-matching-logic)  

# Stylesheet Specification 

The stylesheet provides the following two top-level fields:

| KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`styles` | Array of styleset objects | Provides the stylesets for all elements on all application screens. |  
`values` | Object | The object provides a key-value pair for each style variable. | Style variables work similarly to [CSS variables (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties). The object is not required, if the stylesheet uses no variables.   



# Style Matching Logic

1. If the 

