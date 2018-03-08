# Styling Monetary Hosted WebToken with CSS

### Customizing the style within the iframe!
If you wish to customize the look-and-feel of the content within the Hosted WebToken iframe, you can do so with simple CSS!

##### Styling is as simple as adding the optional 4th parameter, `css`, to the `init` call:
```javascript
var customCSS = ".card-data { background-color: #ADD8E6; color: white; }";
MonetaryHostedWebToken.init('[Public Key Goes Here]', 'monetary-token-iframe', tokenCallback, customCSS);
```

### Stylable objects in Hosted WebToken
#### HTML components CSS class hierarchy:
* `<div class="container">`
  * `<div class="row row-card-data-number">`
    * `<div class="left-col">`
      * `<label class="card-data-number-label">`
    * `<div class="right-col">`
      * `<input class="card-data card-data-number" placeholder="Card Number" />`
    * `<div class="row row-card-data-exp-month">`
      * `<div class="left-col">`
        * `<label class="card-data-exp-month-label">`
      * `<div class="right-col">`
        * `<select class="card-data card-data-exp-month">`
    * `<div class="row row-card-data-exp-year">`
      * `<div class="left-col">`
        * `<label class="card-data-exp-year-label">`
      * `<div class="right-col">`
        * `<select class="card-data card-data-exp-year">`
    * `<div class="row row-card-data-cvv">`
      * `<div class="left-col">`
        * `<label class="card-data-cvv-label">`
      * `<div class="right-col">`
        * `<input class="card-data card-data-cvv" />`

### Default styling and CSS errors
* If the `css` parameter is not provided, a simplistic default styling is applied to the page.
* If any error occurs parsing the provided CSS, all styling will be stripped.
* Invalid selectors, properties, or values in the provided CSS will be ignored.
* When any `css` parameter is provided, default styling is not applied.
* All remote resources referenced in provided CSS will be ignored.
