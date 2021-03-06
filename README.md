# Getting started with Monetary Hosted WebToken

### Include the client on your page
##### Add the secure, hosted JavaScript client in the `<head>` of your page:
```html
<script src="https://token.monetary.co/v1/client/hosted"></script>
```

### Define the required iframe control

##### Create an iframe and give it an ID:
```html
<iframe id="monetary-token-iframe" frameborder="0"></iframe>
```

##### Define an input control to insert the token resulting into:
```html
<input type="hidden" id="token" />
```

### Define required JavaScript
##### Define a JavaScript callback method for token events:
```javascript
var tokenCallback = function(response) {
  if (response.Error)
  {
    alert("Token error: " + response.Error);
  }
  else
  {
    var token = response.Token;
    document.getElementById("token").value = token;
  }
}
```

### Initialize the hosted iframe
##### Call `init` with your public authenticator, iframe control ID, and token callback method:

```javascript
MonetaryHostedWebToken.init('[Public Key Goes Here]', 'monetary-token-iframe', tokenCallback);
```

##### Optional: Provide `init` with a string of your custom CSS to style the iframe contents:

```javascript
var customCSS = ".card-data { background-color: #ADD8E6; color: white; }";
MonetaryHostedWebToken.init('[Public Key Goes Here]', 'monetary-token-iframe', tokenCallback, customCSS);
```

The layout of the iframe contents and their classes can be found here: https://token.monetary.co/v1/view/i

_Note_: When custom CSS is provided, Monetary's default styling is entirely cleared.

### Request a token!
##### Call `requestToken` from your page to trigger tokenization:

```html
<input type="button" onclick="MonetaryHostedWebToken.requestToken()" value="Submit" />
```

##### The response object received by your callback method looks like this:
###### On Success
```javascript
{
  Token: "otuABCDEFGHIJ",
  Brand: "Visa",
  ExpirationMonth: "12",
  ExpirationYear: "2020",
  Last4: "1111"
}
```

###### On Field Validation Failure
```javascript
{
  Error: "Invalid Card Number"
}
```

###### On Failure
```javascript
{
  Error: "Failed to create token"
}
```

### Use your tokens!
Now that you've got a fresh token in your payment form, you can submit the form and process token payments on Monetary's payment platform!

### Report bugs
If you encounter any bugs or issues with the latest version of WebToken, please report them to us by opening a [GitHub Issue](https://github.com/Mntry/HostedWebToken/issues)!
