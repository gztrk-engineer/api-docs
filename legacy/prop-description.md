Collection of properties associated with the style tags. 
<br>

To specify properties, follow this pattern: 
<br>
```
"properties": {
    property1: value1,
    property2: value2
}
```

<br>
Example 1: <br>
```
"properties": { "imageUrl": "file://c:/spinner-test4.gif" }
```


To use subtypes or scales, use the subtype: 

<br>

```javascript
"properties": {
    property1: {**subtype1**: value1},
    property2: {**subtype2**: value2}
}
```
<br> 

Example 2: <br>  

```javascript
"properties": { "backgroundColor": { "hex": "#00dddd" }, "tintColor": { "hex": "#ffffff" } }
```

You can also use the subtype pattern with property variables (keyword `ref`). <br>

Example 3: <br>

```
"properties": { "backgroundColor": { "ref": "primary_color" }}
```
