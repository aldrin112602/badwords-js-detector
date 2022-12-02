# badwords-js-detector
The badwords-js-detector library exported as Node.js modules.

## Installation
Using npm:
```bash
$ npm i badwords-js-detector
```

Using CDN:
```html
<script src="https://cdn.jsdelivr.net/gh/aldrin112602/badwords-js-detector/badwords-js-detector.js"></script>
```
### Importing:
```javascript
// CJS
const { Detector } = require('badwords-js-detector');
const badwords = new Detector();

// ESM
import { Detector } from 'badwords-js-detector';
const badwords = new Detector();

// CDN
const badwords = new Detector();
```

### Usage:
```javascript
const response = badwords.filter('Hello fuck you...');
console.log(response); 

/*
Expected output:

{
    bad-words-list: [
        'fuck'
    ],
    bad-words-total: 1,
    censor-character: '*',
    content: 'Hello fuck you...',
    content-filtered: 'Hello **** you...'
}

*/

// You can customized censor-character
const badwords = new Detector({ placeholder: '@' });
const response = badwords.filter('Hello fuck you...');
console.log(response); 

/*
Expected output:

{
    bad-words-list: [
        'fuck'
    ],
    bad-words-total: 1,
    censor-character: '@',
    content: 'Hello fuck you...',
    content-filtered: 'Hello @@@@ you...'
}

*/
```

Developed with ❤️ by Aldrin Caballero
