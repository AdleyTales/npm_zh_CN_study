
### debug

> - Works in Node.js and web browsers.
> - 随着项目规模增加，console 控制台输出的日志就会堆积很多而不可读。另一方面，我们需要在开发调试环境才打开日志，而线上生产环境就不需要输出过多的日志。使用 console 对象控制日志输出，我们会自然而然地以“加注释”、“去注释”的方式来控制日志的输出。这样很笨。
> - debug库就是一款专门控制日志输出的库，能够完美解决我们的上述需求。
> - 首先，debug库会判断DEBUG环境变量，所以我们不需要修改代码，只调整一下程序运行环境就可以控制日志是否输出。另外，debug库不是简单地布尔判断DEBUG环境变量，而是会对DEBUG环境变量进行解析，允许我们选择性地控制输出哪些模块的日志，有效地解决了调试程序时候控制台日志堆积问题，因为我们可以控制debug，让其只输出我们关心的程序模块的日志。



#### 安装

```
npm install debug
```

#### 使用

```js
const Debugger = require('debug');

const a = Debugger('worker:a');
const b = Debugger('worker:b');

function work() {
  a('doing lots of uninteresting work');
  setTimeout(work, Math.random() * 1000);
}

work();

function workb() {
  b('doing some work');
  setTimeout(workb, Math.random() * 2000);
}

workb();
```


```
DEBUG=worker:* node 3_debug.js // 输出全部
DEBUG=worker:a node 3_debug.js // 只输出a
```

#### 环境设置
- 服务端 `process.env.DEBUG`
- 浏览器 `localStorage.debug = 'worker:*'`
