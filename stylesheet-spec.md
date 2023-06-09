# Stylesheet Specification  

## Top-level structure

The top level structure of the stylesheet is as follows:  

```javascript
{
    "styles": [styleObject1, styleObject2,...],
    "values": [variable1, variable2,...]
}
```

The table below provides a detailed description of the top-level properties: 

KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`styles` | Array | An array of [**ruleset objects**](#ruleset-objects) that define the styles for all elements across application screens.  | Each ruleset within an array must have a unique combination of tags.
`values` | Object | The object that provides [**style variables**](#style-variables), functioning similarly to [CSS variables (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties). | The `values` object is not required, if the stylesheet doesn't use any variables. 

## Ruleset objects  

Here is an example of a ruleset:

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

Ruleset structure is outined below: 

KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`rule` | Object | Provides a nested `tags` array.   | 
`tags` | Array | An array of style tags (string values). It can include tags for the element type, context or location, and / or element state.  | The array of tags functions similarly to [CSS class selectors (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors).  
`properties` | Object | The app renders the elements using the properties for the matching `tags` array. |  

To specify properties, follow this pattern:
```python
{
    property1: {subtype1: value1},
    property2: {subtype2: value2}
}
```

To reuse properties, utilize [style variables](#style-variables). 

The available properties depend on the element type. Refer to [List of available properties]() for more information. 


## Style variables 

Style variables can be reused throughout the `styles` section. These variables are defined within the `values` object.

To specify variables, follow this pattern: 
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

We illustrate this section using the following example rulesets:

```json
{
    // Ruleset 1
    "rule": {
        "tags": [ "button" ]
    },
    "properties": {
        "backgroundColor": { "hex": "#00dddd" },
        "tintColor": { "hex": "#ffffff" }
    }
},
{
    // Ruleset 2
    "rule": {
        "tags": [ "button", "login-screen" ]
    },
    "properties": {
        "backgroundColor": { "hex": "#0000ff" }, 
        "font": {"fontWeight": "400px" }
    }
},
{
    // Ruleset 3
    "rule": {
        "tags": [ "button", "signin-button" ]
    },
    "properties": {
        "font": {"fontWeight": "500px" }
    }
}
``` 

The example element matches all three rulesets:  

```javascript
["button", "login-screen", "signin-button"] 
```

The style matching principles are outlined below:

PRINCIPLE | DESCRIPTION | EXAMPLE   
---|---|---  
Aggregate the properties. | An element aggregates properties from all matching rulesets. | As the element matches all example rulesets, it will have all properties: `backgroundColor`, `tintColor`, and `font`.  
Count the tags. | If multiple ruleset matches contain the same property (different values), the match with more tags prevails. In  | Rulesets 1 and 2 have the same property: `backgroundColor`, but ruleset 2 includes more tags. Therefore, the element will use the property from ruleset 2: `"backgroundColor": { "hex": "#0000ff" }` 
The order matters. | If the element matches multiple ruleset | Rulesets 2 and 3 include the same property (`font`) and the same number of tags (two). In this case, the last declared matching ruleset is applied (`"font": {"fontWeight": "50px"}`).  

