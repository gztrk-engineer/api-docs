# Stylesheet Example 

```javascript
{
    // All styles must be specified inside the 'styles' object
    "styles": [
        // The tag(s) must match for the style property to be applied. 
        {
            "rule": {
                "tags": [ "list-item" ]
            },
            "properties": {
                "backgroundColor": { "hex": "#00dddd" },
                "tintColor": { "hex": "#ffffff" }
            }
        },
        {
            "rule": {
                "tags": [ "list-item", "hover" ]
            },
            "properties": {
                // The subtype 'ref' indicates a style variable. 
                "backgroundColor": { "ref": "primary_color" }
            }
        },

        {
            // This is how images are specified. Use the same format to update the app's logo. 

            "rule": {
                "tags": [ "control-StylableProgressBar" ]
            },
            "properties": {
                "imageUrl": "file://c:/spinner-test4.gif"
            }
        }
    ],
    // Reusable values (variables)
    "values": {
        // Variable name
        "primary_color": {
            // Scale / subtype and the value
            "hex": "#00dd00"
        },
        "secondary_color": {
            "hex": "#ffdd00"
        }
    }
}
```
