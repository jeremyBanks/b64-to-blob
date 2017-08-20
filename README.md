`b64toBlob(b64Data [, contentType])` converts a base64 string to a Blob object
[as described in this Stack Overflow post](https://stackoverflow.com/a/16245768).

Note that the `Blob` class only exists in browsers, not Node, so this package is
intended to be used with a bundler like Webpack or in a simulated browser environment.

## Example Usage

    var b64toBlob = require('b64-to-blob');

    var contentType = 'image/png';
    var b64Data = 'iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACN' +
                  'byblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHx' +
                  'gljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg==';
    
    var blob = b64toBlob(b64Data, contentType);

    var blobUrl = URL.createObjectURL(blob);
    window.location = blobUrl;
