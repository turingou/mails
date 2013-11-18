## ![logo](http://ww2.sinaimg.cn/large/61ff0de3gw1eajmy0wdikj2014014wea.jpg) mails ![npm](https://badge.fury.io/js/mails.png)

使用 mails，让发送邮件变得更简单与优雅，mails 志在解决设计邮件模板时代码复用率低，终端兼容情况不佳等问题。

你既可以使用 mails 内建的标准模板来发送邮件，也可以快速发布自己的邮件主题。mails 内建的标准邮件模板由 [ink](http://zurb.com/ink) 改造而来，二次开发友好，并且对各个终端的兼容表现优秀，稍作修改，亦可以适配智能手机等小屏幕终端。

### 如何安装
````
$ npm install mails
````

### 快速指引

mails 包括三个部分：

- 一个邮件模板加载器  
- 一个支持实时编辑（live reload）的邮件模板设计工具（CLI）  
- 一个快速生成邮件主题项目文件的脚手架工具（CLI）  

如果你是邮件主题开发者，希望分享自己的主题，或者将他们发布到 NPM，你可能会想要使用到第二个与第三个工具；如果你只是使用 mails 发送邮件的程序员，并不需要了解后两者如何运作，只需了解API的使用方法即可：

### 范例代码
最快上手使用 mails，我们来看一段渲染邮件的代码：
````javascript
var mails = require('mails'); // 引用 mails

// 使用 basic 别名加载邮件模板，并填入对应的变量:
mail.render('basic', {
    name: 'mySite',
    banner: 'http://mysite.com/banner.jpg'
}, function(err,html){
    // 得到最终的邮件 html 代码
    if (!err) {
        console.log(html);
    } else {
        console.log(err);
    }
});
````
### 内建邮件主题
mails 内建邮件主题包括以下几种，各个邮件的变量列表请查阅 `templates/*.html` 各个模板文件：

- basic
- hero
- newsletter
- sidebar
- sidebar-hero

### 加载 NPM 模块作为主题
你可以将 mails 提供的标准邮件主题进行简单的二次开发，然后发布到 npm 作为您的邮件主题，使他人获益。

在这个例子中，我们使用 `mails-flat` 模块中的 `message` 主题进行邮件渲染：
````javascript
var mails = require('mails');

mails.render('mails-flat/message', { ...... }, function(err, html){
    console.log(html);
});
````
#### 如何进行主题的二次开发

1. 首先，将 mails 作为全局模块安装：

````
$ [sudo] npm install mails -g
````

2. 建立新项目文件夹，初始化邮件主题：

````
$ mkdir my-mails-theme && cd my-mails-theme
$ mails init
````

3. 编辑 `package.json`，这个文件定义了模板引擎的配置，也保存了调试所需要的变量，确保此文件中有正确的 `view engine` 字段：

````
$ vi ./package.json
$ { "view engine": "swig" }
````

4. 使用 live reload 设计工具进行开发

````
$ mails watch ./package.json 
````


#### 如何发布主题到 NPM
在使用 `npm publish` 发布到社区之前，确认以下几项：
- 确保你的项目中 `package.json` 符合 NPM 社区规范
- 确保 `package.json` 文件中有 `view engine` 字段并且符合邮件模板引擎

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