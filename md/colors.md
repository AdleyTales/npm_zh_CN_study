
## colors

> - nodejs console 命令行颜色

#### 使用

```js
const colors = require('colors')

// 第2种方式
const colors2 = require('colors/safe');

// 第3种方式


console.log('hello'.green);
console.log('i like cake and pies'.underline.red) // outputs red underlined text
console.log('inverse the color'.inverse); // inverses the color
console.log('OMG Rainbows!'.rainbow); // rainbow

console.log("=========================")
console.log(colors2.red("这是第2种方式"))

var name = 'Marak';
console.log(colors.green('Hello %s'), name);
console.log(colors.blue('%s'), "hahahahha");

console.log("=========================")

colors.setTheme({
	silly: 'rainbow',
	input: 'grey',
	verbose: 'cyan',
	prompt: 'grey',
	info: 'green',
	data: 'grey',
	help: 'cyan',
	warn: 'yellow',
	debug: 'blue',
	error: 'red'
});

console.log(colors.error("this is an error"));
console.log(colors.warn("this is a warning"));
```
