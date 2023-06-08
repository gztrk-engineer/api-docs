# Stylesheet Specification 

The stylesheet provides the following two top-level fields:

| KEY  |  DATA TYPE | DESCRIPTION | COMMENTS    
---|---|---|---
`styles` | Array of styleset objects | Provides the stylesets for all elements on all application screens. |  
`values` | Object | The object provides a key-value pair for each style variable. | Style variables work similarly to [CSS variables (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties). The object is not required, if the stylesheet uses no variables.   



# Style Matching Logic

1. If the 