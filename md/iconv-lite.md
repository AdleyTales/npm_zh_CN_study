
## iconv-lite

> - 解决乱码转码
> - 一般配合 `request` 使用

#### 使用
- 转成gbk编码

```js
var request = require('request');
var iconv = require('iconv-lite');

// 这是书包网的一个搜索 书包网返回的网页编码是gbk格式的 如果不转码就是乱码
var url = 'http://www.bookbaow.com/search.asp?m=0&s=0&word=%CD%EA%C3%C0%CA%C0%BD%E7&sf=index';

var options = {
    url:url
};

request(options)
.on('response',function(res){
    var chunks = [];
    res.on('data',function(chunk){
        chunks = chunks.concat(chunk);
    })

    res.on('end',function(){
        var buf = Buffer.concat(chunks);
        // 转码
        var text = iconv.decode(buf,'gbk');
        console.log(text);
    })
    
});

```


