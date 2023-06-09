# Stylesheet Specification  

## Top-level structure

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
`styles` | Array | The array contains **ruleset objects** for all elements across application screens. Requirement: each ruleset inside the array must contain a unique combination of tags.  | See [Ruleset objects](#ruleset-objects) for more information
`values` | Object | The object provides **style variables**. Style variables function similarly to [CSS variables (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties). | The `values` object is not required, if the stylesheet doesn't use any variables. See [Style variables](#style-variables) for more information. 

## Ruleset objects

Rulesets have the following structure: 

KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`rule` | Object | Provides a nested`tags` array.   | 
`tags` | Array | The array contains style tags (string values). The array may include tags for the element type, context or location, and / or element state. The array must be unique within the stylesheet. | The array of tags functions similarly to [CSS class selectors (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors).  
`properties` | Object | The app renders the elements using the properties for the matching `tags` array. | The key-value pairs must be separated with commas (`,`). To reuse style properties, use [variables](#style-variables).  

To specify properties, use the following format:
```python
{
    property1: {subtype1: value1},
    property2: {subtype2: value2}
}
```

Available properties depend on the element type. See [List of available properties]() for additional info. 

Here is a ruleset example:

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

## Style variables 

Style variables can be reused across the `styles` section. The variables are specified inside the `values` object. 

To specify variables, use the following format: 
```json
"values": {
    variableName: { scale: value },
    ....
}
```


Here is an example of a `values` section: 

```json
"values": {
    "primary_color": { "hex": "#00dd00" },
    "secondary_color": { "hex": "#ffdd00" }
}
```



# Style Matching Logic  

Example rulesets for this section:

```json
{
    "rule": {
        "tags": [ "button" ]
    },
    "properties": {
        "backgroundColor": { "hex": "#00dddd" },
        "tintColor": { "hex": "#ffffff" }
    }
},
{
    "rule": {
        "tags": [ "button", "login-screen", "hover" ]
    },
    "properties": {
        "backgroundColor": { "hex": "#0000ff" }
    }
}
    
``` 











# Useful

To edit the styles