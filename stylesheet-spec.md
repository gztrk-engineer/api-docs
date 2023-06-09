# Stylesheet Specification  



At the top level, the stylesheet has the following structure:  

```javascript
{
    "styles": [styleObject1, styleObject2,...],
    "values": [variable1, variable2,...]
}
```

The table below provides a detailed description of the top-level properties: 

KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`styles` | Array | The array contains the style objects for all elements across application screens. | Requirement: each style object inside the array must contain a unique combination of tags.  
`values` | Object | The object provides a key-value pair for each style variable. | Style variables function similarly to [CSS variables (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties). The `values` object is not required, if the stylesheet doesn't use any variables.  

Style objects have the following structure: 

KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`rules` | Object.   | Provides a nested`tags` array.   | 
`tags` | Array | Array of style tags. Must be unique within the stylesheet. | Functions similarly to [CSS class selectors (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors).   
`properties` | Object | The app renders the elements using the properties for the matching `tags` array. | The key-value pairs must be separated with commas (`,`).      
property | Property name, subtype, and value.  | Object format: `propertyName: { subtype: value }`. Example: `"backgroundColor": { "hex": "#00dddd" }`. | Available properties depend on the element type. See [List of available properties]() for additional info. 

Here is an example of a property object:

```json
{
    "rule": {
        "tags": [ "list-item", "hover" ]
    },
    "properties": {
        "backgroundColor": { "hex": "#00dddd" },
        "tintColor": { "hex": "#ffffff" },
        "font": { "fontWeight": "400" }
    }
}
```


# Style Matching Logic  

If a





# Useful

To edit the styles