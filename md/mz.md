### mz

> Modernize node.js to current ECMAScript specifications! node.js will not update their API to ES6+ for a while. This library is a wrapper for various aspects of node.js' API.

```js
const fs = require('mz/fs');

(async () => {
    let data = await fs.readFile('1.txt', 'utf-8');
    console.log(data);
})();
```



