# 正则表达式
## 正则表达式表示一种规则，一种模式，强大的字符串匹配工具
## var re = /a/

> i 不区分大小写
``` js
var re = /a/i;
    var str = 'abcdef';
    alert(str.search(re));
```

> \d 表示数字 查找第一个数字的位置  转义
```js
var str = 'adsf 38 25 vcdjhfkd0';
    var re = /\d/;
    alert(str.search(re));

```

> match 把所有匹配的东西，全部提取出来  查找所有的数字
```js
var str = 'asdf 34 658 cns330';
    var re = /\d/g;
    alert(str.match(re));

```

> +表示若干
```js
var str = 'asdf 34 658 cns330';
    var re = /\d+/g;
    alert(str.match(re));
```

> replace 替换字符串，只能替换第一个字符串
```js
var str = 'abc aa rew';
    var re = /a/;
    alert(str.replace('a', '0'));

```

> 把全部的a都变成0
```js
var str = 'abc aa rew';
    var re = /a/g;
    alert(str.replace(re, '0'));
```

> 元字符  方括号  abc任意一个都可以 [0-9]相当于\d
```js
[abc]pc
```
>  [^a-z]   除了a到z   [^a-z0-9]除了英文和数字

```js
// 转义字符
    // .(点)----任意字符
    // \d. \w. \s
    // \D. \W. \S
     //<.+>   任意个任意字符 

    // \d              数字                        [0-9]
    // \w              数字，英文，下划线           [a-z0-9]
    // \s              空白字符   
    // \D                                          [^0-9]
    // \W                                          [^a-z0-9]
    // \S              非空白字符


```

> 量词  ：个数
```js
// {n} 正好出现n 次
    // \d{8}   正好出现8次

    //电话号，前一位是1，后7位是数字 
    // [1-9]\d{7}
```

> {n,m} 最少n次，最多m次
```js
 // QQ号，第一位0-9 后面4到10个位数
    // [1-9]\d{4,10}
```

> {n,} 最少n次，最多不限  等于+
```js
 // ？相当于{0,1}  可有可无
    // *可以有，也可以没有，多少位都可以 但是不推荐使用

     // 固定电话  区号和分界号可有可无
    // 010-87596615
    // 87596615

    // (0\d{2,3}-)?[1-9]\d{7}(-\d{1,5})?

```
