# Styling Monetary Hosted WebToken with CSS

### Customizing the style within the iframe!
If you wish to customize the look-and-feel of the content within the Hosted WebToken iframe, you can do so with simple CSS!

##### Styling is as simple as adding the optional 4th parameter, `css`, to the `init` call:
```javascript
var customCSS = ".card-data { background-color: #ADD8E6; color: white; }";
MonetaryHostedWebToken.init('[Public Key Goes Here]', 'monetary-token-iframe', tokenCallback, customCSS);
```

### Stylable objects in Hosted WebToken
#### Div class hierarchy:
* `container`
  * `row` `row-card-data-number`
    * `left-col`
    * `right-col`
  * `row` `row-card-data-exp-month`
    * `left-col`
    * `right-col`
  * `row` `row-card-data-exp-year`
    * `left-col`
    * `right-col`
  * `row` `row-card-data-cvv`
    * `left-col`
    * `right-col`

### Default styling and CSS errors
* If the `css` parameter is not provided a simplistic default styling is applied to the page.
* If any error occurs parsing the provided CSS, all styling will be stripped.
* Invalid selectors, properties, or values in the provided CSS will be ignored.
* When a `css` parameter is provided, default styling is not applied.
* All remote resources referenced in provided CSS will be ignored.
