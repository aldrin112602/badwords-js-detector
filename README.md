# badwords-js-detector
The badwords-js-detector library exported as Node.js modules.

## Installation
Using npm:\
`$ npm i badwords-js-detector`

### Importing:
```javascript
// CJS
const { Detector } = require('badwords-js-detector');
const badwords = new Detector();

// ESM
import { Detector } from 'badwords-js-detector';
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