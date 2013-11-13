## ![logo](http://ww2.sinaimg.cn/large/61ff0de3gw1eajmy0wdikj2014014wea.jpg) mails ![npm](https://badge.fury.io/js/mails.png)

mails 让你发送邮件变得更加简单，优雅。你可以使用 mails 内建的标准模板来发送邮件，也可以快速发布自己的邮件主题。mails 内建的标准邮件模板由 [ink](http://zurb.com/ink) 改造而来，二次开发简易，并且对各个终端的兼容表现优秀。

### 如何安装
````
$ npm install mails
````

### 范例代码
最快上手使用 mails，这里，我们选用名为 basic 的邮件模板渲染邮件：
````javascript
var mails = require('mails');

// use built in templates
mail.render('basic', {
    name: 'mySite',
    banner: 'http://mysite.com/banner.jpg'
}, function(err,html){
    if (!err) {
        console.log(html);
    } else {
        console.log(err);
    }
});
````
### 内建邮件主题
mails 内建邮件主题包括以下几种:

- ink 主题:
    - basic
    - hero
    - newsletter
    - sidebar
    - sidebar-hero
- mails 主题:
    - one

#### 内建邮件主题变量列表
take a look:
(screenshots coming soon...)

### 使用 NPM 模块作为邮件主题
你可以将 mails 提供的标准邮件主题进行简单的二次开发，然后发布到 npm 座位您的邮件主题，并且让他人受益。

在这个例子中，我们引入了一个叫做 `mails-mailmao` 的模块，并使用其中的 `single.jade` 主题。
````javascript
var mails = require('mails');

// using templates named `single` under module `mails-mailmao`
mails.render('mails-mailmao/single', {
    name: 'mySite',
    banner: 'http://mysite.com/banner.jpg'
}, function(err, html){
    // do sth.
});
````
#### 如何进行主题的二次开发
待续...

#### 如何发布主题到 NPM
待续...

### API
查看这个文件: `index.js`

### 贡献我的代码
- Fork this repo
- Clone your repo
- Install dependencies
- Checkout a feature branch
- Feel free to add your features
- Make sure your features are fully tested
- Open a pull request, and enjoy <3

### MIT license
Copyright (c) 2013 turing

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


---
![docor](https://cdn1.iconfinder.com/data/icons/windows8_icons_iconpharm/26/doctor.png)
generated using [docor](https://github.com/turingou/docor.git) @ 0.1.0. brought to you by [turingou](https://github.com/turingou)