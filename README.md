# Rise Node.js SDK

## Public Api V2

This v2 version offers the same functionalities of V1 above except of a different and improved approach that will let you query the RISE apis easily using typescript.

### Coding differences from V1
- In V1 if the network request fails you wouldn't have been able to know it.
- Like [Promises](https://developers.google.com/web/fundamentals/getting-started/primers/promises)? In V2 you can use them!!

### Other Perks in V2

V2 was completely rewritten in [TypeScript](https://www.typescriptlang.org/). You **don't need** to know what TypeScript to leverage some of its benefits such as:
- Code completion: several IDEs such as IntelliJ/WebStorm, sublime and others provide code assist for typescript
- Faster development: thanks to the supporting IDEs, you do not need to remember if that variable is supposed to be a number, an array, or a string. The editor will tell you that. 
- Less errors in your code: thanks to TypeScript your editor will be able to catch errors before running your code!

## Documentation

All available methods are available [here]('https://vekexasia.github.io/rise-js-sdk/modules/_index_.html')

## Quick Start

### Include the library in your browser.

Either download `dist/browser/index.js` or use gitcdn as follows:

```html
<script type="text/javascript" src="https://gitcdn.xyz/repo/vekexasia/rise-js-sdk/master/dist/browser/index.js"></script>
<script>
  var apiWrapper = createWrapper('http://example.com:5566'); // Set your node url here. (no leading slash)
  // ...
</script>

```

### Include it with npm (Suitable also for webpack/browserify)

```bash
npm i rise-js-sdk -D
```

```javascript
var riseSDK = require('rise-js-sdk');
var apiWrapper = riseSDK.createWrapper('http://example.com:5566'); // Set your node url here. (no leading slash) 

```


## Compatibility

### Browser Support

![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Firefox](https://raw.github.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![Safari](https://raw.github.com/alrra/browser-logos/master/src/safari/safari_48x48.png) | ![Opera](https://raw.github.com/alrra/browser-logos/master/src/opera/opera_48x48.png) | ![Edge](https://raw.github.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![IE](https://raw.github.com/alrra/browser-logos/master/src/archive/internet-explorer_9-11/internet-explorer_9-11_48x48.png) |
--- | --- | --- | --- | --- | --- |
Latest ✔ | Latest ✔ | Latest ✔ | Latest ✔ | Latest ✔ | 8+ ✔ |

[![Browser Matrix](https://saucelabs.com/open_sauce/build_matrix/axios.svg)](https://saucelabs.com/u/axios)

### Node support

Node >= 4.x is fully supported :)


## Examples

All the APIs are designed to be easy to use. You can use both Callbacks or Promises; you decide.

For example you can open a new account by doing:

```javascript
// wrapper was previously created
wrapper.accounts.open('secret', function(error, account) {
  if (!error) {
    // yay!
    console.log(account);
  } else {
    console.log('error: ', error);
  }
  // ...
});
```

or

```javascript
wrapper.accounts.open('secret')
    .then(function (account) {
      console.log(account);
    })
    .catch(function (error) {
      console.log('error: ', error);
    });
```

which can be even shorter if you write your code in TypeScript or ES6

```javascript
wrapper.accounts.open('secret')
    .then(console.log)
    .catch(error => console.log('error: ', error));
```

