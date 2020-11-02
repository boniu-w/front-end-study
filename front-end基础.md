# vue 部分

#### 1. 创建一个基于 webpack 模板的新项目

 vue init webpack my-project

 cd my-project
 cnpm install

 npm start (npm run dev)

---

document.write(vm.$el === document.getElementById('vue_det')) // true
 -----------------------------------------------------------------------
v-model不仅可以给input赋值还可以获取input中的数据，而且数据的获取是实时的，因为语法糖中是用@input对输入框进行监听的。
 -----------------------------------------------------------------------
 slice() 方法可从已有的数组中返回选定的元素。
 arrayObject.slice(start,end)
 返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。
 请注意，该方法并不会修改数组，而是返回一个子数组。如果想删除数组中的一段元素，应该使用方法 Array.splice()。

#### 2. vue中的单选框

```js
	<a-checkbox-group v-decorator="['personTypeId', {}]">
        <a-checkbox :value="1">主体</a-checkbox>
    </a-checkbox-group>
```





#### 3. vue computed

#### 4. this.$emit('ok')

子组件 向父组件 传值



-----------------------------------------------------------------------------------------------------------------------------------------------------------



# 								js 部分

-----------------------------------------------------------------------------------------------------------------------------------------------------------

| 方法                                         | 描述                 |
| -------------------------------------------- | -------------------- |
| String  join()                               | 把数组转成字符串     |
| 长度  push()                                 | 在数组的后面添加元素 |
| var formData = new FormData().append("",val) | 为formdata添加属性   |





#### 1. JavaScript  hasOwnProperty()  : obj 的方法

Object的`hasOwnProperty()`方法返回一个布尔值，判断对象是否包含特定的自身（非继承）属性

```java
obj.hasOwnProperty("id");  // obj 是否有这个 id 属性  
```



#### 2. JavaScript  .join()  : 数组的方法

join() 用于把数组中的所有元素放到一个字符串中, 

arrayobject.join(separator);



separator : 可选,指定使用的分隔符,如果省略,则使用逗号作为分隔符;



返回的是个 字符串



#### 3. push() :  数组的方法

push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。



```js
arrayObject.push(newelement1,newelement2,....,newelementX)
```



| 参数        | 描述                             |
| :---------- | :------------------------------- |
| newelement1 | 必需。要添加到数组的第一个元素。 |
| newelement2 | 可选。要添加到数组的第二个元素。 |
| newelementX | 可选。可添加多个元素。           |



返回的是个长度



例:

```js
<script type="text/javascript">

var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

document.write(arr + "<br />")
document.write(arr.push("James") + "<br />")
document.write(arr)

</script>
```



输出: 

```js
George,John,Thomas
4
George,John,Thomas,James
```





#### 4. sessionStorage.setItem

使用 sessionStorage 创建一个本地存储的 key/value 对

sessionStorage.getItem(key);



`sessionStorage` 属性允许你访问一个，对应当前源的 session [`Storage`](https://developer.mozilla.org/zh-CN/docs/Web/API/Storage) 对象。它与 [`localStorage`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/localStorage) 相似，不同之处在于 `localStorage` 里面存储的数据没有过期时间设置，而存储在 `sessionStorage` 里面的数据在页面会话结束时会被清除。



#### 5. el

获取{}中指定的对象（参数、对象等）的值, 其搜寻的范围依次是：page、request、session、application

request.getAttribute(name) === ${name} 



#### 6. js内置对象

Math

Date

Array

String



#### 7. 立即执行函数

(function(arg){})(arg)

前半部分: (function(arg){}) 匿名函数

后半部分: (arg)传入参数 并立即执行

#### 8. 新窗口打开 , 当前页面打开

```js
onclick="window.open('https://www.baidu.com')" // 新窗口打开
window.location.href='https://www.baidu.com'  // 当前页面打开
```



#### 9. 将两个字符串数组 合并为一个 对象

```js
						var values = new Array();
                        $("#mail-content input").each(function () {
                            values.push($(this).val())
                        })

                        console.log(values, typeof values);

                        var str = ["name", "company", "phone", "content"];

                        var obj= values.reduce(function (result, value, index) {
                            result[str[index]] = value;
                            return result;
                        },{})

                        console.log("*****  ",obj)
```



#### 10. 数组



| function | description | example |
| -------- | ----------- | ------- |
| push()   |             |         |
| join()   |             |         |
|          |             |         |
|          |             |         |





#### 11. bootstraptable

```js
  $('#table').bootstrapTable({
            url: '/ms-mcms/emailController/getEmailList',
            method:'get',
            pageNumber : 1,
            pagination: true,
            // sidePagination: "server",
            pageSize : 10,
            pageList : [ 5, 10, 20, 30 ,50],
            // search: true,
            responseHandler: function(res) {
                console.log(res.data)
                res.data.forEach((item,i)=>{
                    let date = new Date(item.time);
                datetime =formatDate(date);
                res.data[i].time = datetime
            })
                return res.data
            },
            columns: [{
                field: 'id',
                title: '序号'
            }, {
                field: 'sender',
                title: '发件人'
            }, {
                field: 'senderCompany',
                title: '发件人单位'
            },{
                field: 'senderPhone',
                title: '发件人手机号码'
            },{
                field: 'content',
                title: '邮件内容'
            },{
                field: 'sendTime',
                title: '发送时间'
            }]
        })
```



1. bootstraptable columns 隐藏 

> visible: false









#### 12. 日期 按一定的格式输出

```js
        function formatDate(date) {
            var year = date.getFullYear()
            var month = format(date.getMonth() + 1)
            var da = format(date.getDate())
            var h = format(date.getHours())
            var m =format(date.getMinutes())
            var s = format(date.getSeconds())
            return year + '-' + month + '-' + da + ' ' + h + ':' + m + ':' + s
        };
        function format(val) {
            return Number(val) < 10 ? '0' + val : '' + val
        };
```





# npm 部分

#### 1. 安装 依赖

```
cnpm install echarts --save
```





# html

#### 1. meta

<meta> 元素可提供有关页面的元信息（meta-information），比如针对搜索引擎和更新频度的描述和关键词。

- http-equiv 属性

http-equiv 属性为名称/值对提供了名称。并指示服务器在发送实际的文档之前先在要传送给浏览器的 MIME 文档头部包含名称/值对。

当服务器向浏览器发送文档时，会先发送许多名称/值对。虽然有些服务器会发送许多这种名称/值对，但是所有服务器都至少要发送一个：content-type:text/html。这将告诉浏览器准备接受一个 HTML 文档。

使用带有 http-equiv 属性的 <meta> 标签时，服务器将把名称/值对添加到发送给浏览器的内容头部。例如，添加：

```
<meta http-equiv="charset" content="iso-8859-1">
<meta http-equiv="expires" content="31 Dec 2008">
```

这样发送到浏览器的头部就应该包含：

```
content-type: text/html
charset:iso-8859-1
expires:31 Dec 2008
```

当然，只有浏览器可以接受这些附加的头部字段，并能以适当的方式使用它们时，这些字段才有意义。



#### 2. document.domain

跨域访问的

默认情况下，document.domain存放的是载入文档的服务器的主机名，可以手动设置这个属性，不过是有限制的，只能设置成当前域名或者上级的域名，并且必须要包含一个.号，也就是说不能直接设置成顶级域名。例如：id.qq.com，可以设置成qq.com，但是不能设置成com。

具有相同document.domain的页面，就相当于是处在同域名的服务器上，如果协议和端口号也是一致，那它们之间就可以跨域访问数据。





#### 3. function,attribute



| document                               | description                                                  | example                                       |
| -------------------------------------- | ------------------------------------------------------------ | --------------------------------------------- |
| window.open(URL,name,features,replace) |                                                              | window.open("http://www.w3school.com.cn")     |
| window.domain                          | 跨域 属性可以解决因同源安全策略带来的不同文档的属性共享问题  |                                               |
| window.onload=function(){}             | 用于在网页加载完毕后立刻执行的操作，即当 HTML 文档加载完毕后，立刻执行某个方法, 因为 JavaScript 中的函数方法需要在 HTML 文档渲染完成后才可以使用，如果没有渲染完成，此时的 DOM 树是不完整的，这样在调用一些 JavaScript 代码时就可能报出"undefined"错误。<br>一般用在body标签和 img标签 |                                               |
| document.write()                       | 在文档已加载后使用它（比如在函数中），会覆盖整个文档。       | document.write("<h1>This is a heading</h1>"); |
| document.body.clientHeight             | 可见部分的高度, 包括padding, 但不包括border、水平滚动条、margin的元素的高度 |                                               |
| document.body.offsetHeight             | 包括padding、border、水平滚动条，但不包括margin的元素的高度  |                                               |
| document.body.scrollHeight             | 滚动条高, scrollHeight:因为子元素比父元素高，父元素不想被子元素撑的一样高就显示出了滚动条 |                                               |
| window.screen.height                   | 获取屏幕分辨率                                               |                                               |
| window.localtion.reload()              | 刷新页面                                                     |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |




- window.onload 与 document.ready

  1. document.ready：document.ready可以写多个.ready，可以执行多次，第N次都不会被上一次覆盖。

  2. onload：onload只能执行一次，如果有多个，那么第一次的执行会被覆盖

  3. 执行速度不同 

     1. document.ready：onload除了要等待DOM被创建还要等到包括大型图片、音频、视频在内的所有外部资源都完全加载。如果加载图片和媒体内容花费了大量时间，用户就会感受到定义在onload事件上的代码在执行时有明显的延迟。
     2. onload：document.ready函数只需对 DOM 树的等待，而无需对图像或外部资源加载的等待，从而执行起来更快。

  4. 加载程度不同

     1. document.ready：在DOM加载完成后bai就可以可以对DOM进行操作。一du般情况一个页面响应加载的顺序是，域名解析-加载html-加载js和css-加载图片等其他信息。那么Dom Ready应该在“加载js和css”和“加载图片等其他信息”之间，就可以操作Dom了。

     2. onload：在document文档加载完成后就可以可以对DOM进行操作，document文档包括了加载图片等其他信息。那么Dom Load就是在页面响应加载的顺序中的“加载图片等其他信息”之后，就可以操作Dom了。



location.hash : 一般情况下为URL后 "#" 及其后面一部分组成，如http://www.test.com/#/something，其中http://www.test.com为真实的路径，而#/something则为网页中的位置，称之为**锚点**, 在访问锚点时会自动跳到锚点所在的网页位置，

在对hash写时有个需要注意的地方，如下所示

```javascript
//当前URL为http://www.test.com/location.hash = "#/test"	//http://www.test.com/#/testlocationl.hash = "/#/test"	//http://www.test.com/#/#/test
```

当写入第一个字符不为为 "#" 时会自动生成一个 "#" 在字符串之前，再把字符串追加到生成的#后面

这样会造成有两个#,此时location.hash输出 "#/#/test"

#### 4. 标签页显示 文字 和 图标

- 浏览器的标签页显示 文字 和 图标

  ```html
  <title>天津公安经侦综合信息网</title>
  <link rel="icon" sizes="any" href="/ms-mcms/templets/1/company1804/images/JingHui.png">
  ```


#### 5. 引入公共部分

- 写入公共js  common.js

  ```html
  document.write('<!-----------  公共js和css start----------->');
  document.write('' +
      '<link rel="stylesheet" href="http://localhost:33333/css/bootstrap.min.css">' +
      '<link rel="stylesheet" href="http://localhost:33333/css/bootstrap-theme.css">' +
      '<script src="http://localhost:33333/js/jquery-3.3.1.min.js"></script>' +
      '<script src="http://localhost:33333/js/bootstrap.min.js"></script>' +
      '');
  document.write('<!-----------  公共js和css end----------->');
  ```

  ```html
  <script src="http://localhost:33333/js/common.js"></script>
  ```

  

- 引入公共页面 header.html

  ```html
  
  <div class="container" style="background: #a6e1ec; ">
      <div class="row">
          <div class="col-md-4">
              <div class="row">
                  <div class="col-md-4">
                      <span class="riqi">2020年7月30日</span>
                  </div>
                  <div class="col-md-4">
                      <span class="xianxing">今日限行 0 5</span>
                  </div>
                  <div class="col-md-4">
                      <span class="kuaisubobao"> 快速播报</span>
                  </div>
              </div>
          </div>
  
          <div class="col-md-5">
  
              <marquee>文本从左向右滚动</marquee>
  
          </div>
          <div class="col-md-3" style="margin-top: 2px;margin-bottom: 4px; height: 80%">
              <div class="row">
                  <div class="col-md-12 input-group input-mini">
                      <input type="text" class="form-control" placeholder="Recipient's username"
                             aria-describedby="basic-addon2">
                      <span class="input-group-addon" id="basic-addon2">@example.com</span>
                  </div>
              </div>
          </div>
  
      </div>
  
  
  </div>
  
  ```

- body.html

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>test body include header.html</title>
      <script src="http://localhost:33333/js/common.js"></script>
  </head>
  <body>
  
  <div id="yy"></div>
  <script>
      $().ready(function () {
          $("#yy").load("http://localhost:33333/page/templet/header.html");
      })
  
  </script>
  </body>
  </html>
  ```




#### 6. 列表

```html
<html>

<body>

<h2>一个定义列表：</h2>

<dl>
   <dt>计算机</dt>
   <dd>用来计算的仪器 ... ...</dd>
   <dt>显示器</dt>
   <dd>以视觉方式显示信息的装置 ... ...</dd>
</dl>

</body>
</html>
```



#### 7. 属性



| attribute | description                                                  |                                                              |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| alt       | alt 属性是一个必需的属性，它规定在图像无法显示时的替代文本   | <img src="smiley-2.gif" alt="Smiley face" width="42" height="42"> |
| z-index   | 设置元素的堆叠顺序。拥有更高堆叠顺序的元素总是会处于堆叠顺序较低的元素的前面。 | \<div id="box" style="z-index: 999">                         |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |
|           |                                                              |                                                              |



#### 8. 选择器



| 选择器                                                       | 示例                  | 示例说明                                                  | CSS  |
| :----------------------------------------------------------- | :-------------------- | :-------------------------------------------------------- | :--- |
| [.*class*](https://www.runoob.com/cssref/sel-class.html)     | .intro                | 选择所有class="intro"的元素                               | 1    |
| [#*id*](https://www.runoob.com/cssref/sel-id.html)           | #firstname            | 选择所有id="firstname"的元素                              | 1    |
| [*](https://www.runoob.com/cssref/sel-all.html)              | *                     | 选择所有元素                                              | 2    |
| *[element](https://www.runoob.com/cssref/sel-element.html)*  | p                     | 选择所有<p>元素                                           | 1    |
| *[element,element](https://www.runoob.com/cssref/sel-element-comma.html)* | div,p                 | 选择所有<div>元素和<p>元素                                | 1    |
| [*element* *element*](https://www.runoob.com/cssref/sel-element-element.html) | div p                 | 选择<div>元素内的所有<p>元素                              | 1    |
| [*element*>*element*](https://www.runoob.com/cssref/sel-element-gt.html) | div>p                 | 选择所有父级是 <div> 元素的 <p> 元素                      | 2    |
| [*element*+*element*](https://www.runoob.com/cssref/sel-element-pluss.html) | div+p                 | 选择所有紧接着<div>元素之后的<p>元素                      | 2    |
| [[*attribute*\]](https://www.runoob.com/cssref/sel-attribute.html) | [target]              | 选择所有带有target属性元素                                | 2    |
| [[*attribute*=*value*\]](https://www.runoob.com/cssref/sel-attribute-value.html) | [target=-blank]       | 选择所有使用target="-blank"的元素                         | 2    |
| [[*attribute*~=*value*\]](https://www.runoob.com/cssref/sel-attribute-value-contains.html) | [title~=flower]       | 选择标题属性包含单词"flower"的所有元素                    | 2    |
| [[*attribute*\|=*language*\]](https://www.runoob.com/cssref/sel-attribute-value-lang.html) | [lang\|=en]           | 选择 lang 属性以 en 为开头的所有元素                      | 2    |
| [:link](https://www.runoob.com/cssref/sel-link.html)         | a:link                | 选择所有未访问链接                                        | 1    |
| [:visited](https://www.runoob.com/cssref/sel-visited.html)   | a:visited             | 选择所有访问过的链接                                      | 1    |
| [:active](https://www.runoob.com/cssref/sel-active.html)     | a:active              | 选择活动链接                                              | 1    |
| [:hover](https://www.runoob.com/cssref/sel-hover.html)       | a:hover               | 选择鼠标在链接上面时                                      | 1    |
| [:focus](https://www.runoob.com/cssref/sel-focus.html)       | input:focus           | 选择具有焦点的输入元素                                    | 2    |
| [:first-letter](https://www.runoob.com/cssref/sel-firstletter.html) | p:first-letter        | 选择每一个<p>元素的第一个字母                             | 1    |
| [:first-line](https://www.runoob.com/cssref/sel-firstline.html) | p:first-line          | 选择每一个<p>元素的第一行                                 | 1    |
| [:first-child](https://www.runoob.com/cssref/sel-firstchild.html) | p:first-child         | 指定只有当<p>元素是其父级的第一个子级的样式。             | 2    |
| [:before](https://www.runoob.com/cssref/sel-before.html)     | p:before              | 在每个<p>元素之前插入内容                                 | 2    |
| [:after](https://www.runoob.com/cssref/sel-after.html)       | p:after               | 在每个<p>元素之后插入内容                                 | 2    |
| [:lang(*language*)](https://www.runoob.com/cssref/sel-lang.html) | p:lang(it)            | 选择一个lang属性的起始值="it"的所有<p>元素                | 2    |
| [*element1*~*element2*](https://www.runoob.com/cssref/sel-gen-sibling.html) | p~ul                  | 选择p元素之后的每一个ul元素                               | 3    |
| [[*attribute*^=*value*\]](https://www.runoob.com/cssref/sel-attr-begin.html) | a[src^="https"]       | 选择每一个src属性的值以"https"开头的元素                  | 3    |
| [[*attribute*$=*value*\]](https://www.runoob.com/cssref/sel-attr-end.html) | a[src$=".pdf"]        | 选择每一个src属性的值以".pdf"结尾的元素                   | 3    |
| [[*attribute**=*value*\]](https://www.runoob.com/cssref/sel-attr-contain.html) | a[src*="runoob"]      | 选择每一个src属性的值包含子字符串"runoob"的元素           | 3    |
| [:first-of-type](https://www.runoob.com/cssref/sel-first-of-type.html) | p:first-of-type       | 选择每个p元素是其父级的第一个p元素                        | 3    |
| [:last-of-type](https://www.runoob.com/cssref/sel-last-of-type.html) | p:last-of-type        | 选择每个p元素是其父级的最后一个p元素                      | 3    |
| [:only-of-type](https://www.runoob.com/cssref/sel-only-of-type.html) | p:only-of-type        | 选择每个p元素是其父级的唯一p元素                          | 3    |
| [:only-child](https://www.runoob.com/cssref/sel-only-child.html) | p:only-child          | 选择每个p元素是其父级的唯一子元素                         | 3    |
| [:nth-child(*n*)](https://www.runoob.com/cssref/sel-nth-child.html) | p:nth-child(2)        | 选择每个p元素是其父级的第二个子元素                       | 3    |
| [:nth-last-child(*n*)](https://www.runoob.com/cssref/sel-nth-last-child.html) | p:nth-last-child(2)   | 选择每个p元素的是其父级的第二个子元素，从最后一个子项计数 | 3    |
| [:nth-of-type(*n*)](https://www.runoob.com/cssref/sel-nth-of-type.html) | p:nth-of-type(2)      | 选择每个p元素是其父级的第二个p元素                        | 3    |
| [:nth-last-of-type(*n*)](https://www.runoob.com/cssref/sel-nth-last-of-type.html) | p:nth-last-of-type(2) | 选择每个p元素的是其父级的第二个p元素，从最后一个子项计数  | 3    |
| [:last-child](https://www.runoob.com/cssref/sel-last-child.html) | p:last-child          | 选择每个p元素是其父级的最后一个子级。                     | 3    |
| [:root](https://www.runoob.com/cssref/sel-root.html)         | :root                 | 选择文档的根元素                                          | 3    |
| [:empty](https://www.runoob.com/cssref/sel-empty.html)       | p:empty               | 选择每个没有任何子级的p元素（包括文本节点）               | 3    |
| [:target](https://www.runoob.com/cssref/sel-target.html)     | #news:target          | 选择当前活动的#news元素（包含该锚名称的点击的URL）        | 3    |
| [:enabled](https://www.runoob.com/cssref/sel-enabled.html)   | input:enabled         | 选择每一个已启用的输入元素                                | 3    |
| [:disabled](https://www.runoob.com/cssref/sel-disabled.html) | input:disabled        | 选择每一个禁用的输入元素                                  | 3    |
| [:checked](https://www.runoob.com/cssref/sel-checked.html)   | input:checked         | 选择每个选中的输入元素                                    | 3    |
| [:not(*selector*)](https://www.runoob.com/cssref/sel-not.html) | :not(p)               | 选择每个并非p元素的元素                                   | 3    |
| [::selection](https://www.runoob.com/cssref/sel-selection.html) | ::selection           | 匹配元素中被用户选中或处于高亮状态的部分                  | 3    |
| [:out-of-range](https://www.runoob.com/cssref/sel-out-of-range.html) | :out-of-range         | 匹配值在指定区间之外的input元素                           | 3    |
| [:in-range](https://www.runoob.com/cssref/sel-in-range.html) | :in-range             | 匹配值在指定区间之内的input元素                           | 3    |
| [:read-write](https://www.runoob.com/cssref/sel-read-write.html) | :read-write           | 用于匹配可读及可写的元素                                  | 3    |
| [:read-only](https://www.runoob.com/cssref/sel-read-only.html) | :read-only            | 用于匹配设置 "readonly"（只读） 属性的元素                | 3    |
| [:optional](https://www.runoob.com/cssref/sel-optional.html) | :optional             | 用于匹配可选的输入元素                                    | 3    |
| [:required](https://www.runoob.com/cssref/sel-required.html) | :required             | 用于匹配设置了 "required" 属性的元素                      | 3    |
| [:valid](https://www.runoob.com/cssref/sel-valid.html)       | :valid                | 用于匹配输入值为合法的元素                                | 3    |
| [:invalid](https://www.runoob.com/cssref/sel-invalid.html)   | :invalid              | 用于匹配输入值为非法的元素                                | 3    |



在table中动态添加tr td

```js
                                var table = document.getElementById("onDutyMember");
                                for (let j = 0; j < trLength; j++) {
                                    var tr = table.insertRow(j);
                                    for (let i = 0; i < a.length; i++) {
                                        var td = tr.insertCell(i)
                                        td.innerText = a[i];
                                    }
                                }
```



#### 9. 符号 HTML 中有用的字符实体

**注释：**实体名称对大小写敏感！

| 显示结果 | 描述              | 实体名称           | 实体编号 |
| :------- | :---------------- | :----------------- | :------- |
|          | 空格              | \&nbsp;            | \&#160;  |
|          | 也是空格, 大空格  | \&emsp;            |          |
| <        | 小于号            | \&lt;              | \&#60;   |
| >        | 大于号            | \&gt;              | \&#62;   |
| &        | 和号              | \&amp;             | \&#38;   |
| "        | 引号              | \&quot;            | \&#34;   |
| '        | 撇号              | \&apos; (IE不支持) | \&#39;   |
| ￠       | 分（cent）        | \&cent;            | \&#162;  |
| £        | 镑（pound）       | \&pound;           | \&#163;  |
| ¥        | 元（yen）         | \&yen;             | \&#165;  |
| €        | 欧元（euro）      | \&euro;            | \&#8364; |
| §        | 小节              | \&sect;            | \&#167;  |
| ©        | 版权（copyright） | \&copy;            | \&#169;  |
| ®        | 注册商标          | \&reg;             | \&#174;  |
| ™        | 商标              | \&trade;           | \&#8482; |
| ×        | 乘号              | \&times;           | \&#215;  |
| ÷        | 除号              | \&divide;          | \&#247;  |
| /        | 斜线              | \&#47;             |          |



#### 10. 问题

1. 找不到favicon.ico

   favicon.ico文件是浏览器收藏网址时显示的图标，当客户端使用浏览器页面时，浏览器会自己主动发起请求获取页面的favicion.ico文件，但是当浏览器请求的favicion.ico文件不存在时，服务器会记录404日志，而且浏览器也会显示404错误,

    用localhost请求会报这个错, 但是用 127.0.0.1 请求 就没有这个报错

   解决办法: 

   1. 办法一: 让服务器不记录访问日志
   
      ```js
      server {
          server_name www.mylinuxops.com;
          access_log /var/log/nginx/access.log access_json;
          location / {
              root /data/www;
              index index.html;
        }
          location = /favicon.ico {       #精确定位ifavicon.ico文件
              log_not_found off;          #找不到文件时日志不记录
              access_log off;             #关闭日志记录
       }
   }
      ```

      

   2. 办法二: 将图标文件保存到指定的目录访问
   
      ```js
      server {
          server_name www.mylinuxops.com;
          access_log /var/log/nginx/access.log access_json;
          location / {
              root /data/www;
              index index.html;
        }
          location = /favicon.ico {
              root /data/www/image;
       }
      }
       
      [root@www ~]# ls /data/www/image/favicon.ico
   /data/www/image/favicon.ico
      ```

   3. 办法三: \<link rel="shortcut icon" href="#"/> 将代码 放到 \<head>里, 网上说不推荐使用, 当点一个链接后 会产生2次请求,但是自己实验中并没有发现问题
   
   4. 办法四: 将请求的localhost 改为 127.0.0.1 
   
   

#### 11. 垂直居中

div的垂直居中问题 vertical-align:middle; 将行距增加到和整个DIV一样高 line-height:200px; 然后插入文字，就垂直居中了。缺点是要控制内容不要换行



#### 12. target="_blank"



| <span style="white-space: nowrap;">attribute &emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">description &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">example &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| alt                                                          | 图的一个属性, alt 属性是一个必需的属性，它规定在图像无法显示时的替代文本 | `<img src="smiley-2.gif" alt="Smiley face" width="42" height="42">` |
| target                                                       | 如果在一个 <a> 标签内包含一个 target 属性，浏览器将会载入和显示用这个标签的 href 属性命名的、名称与这个目标吻合的框架或者窗口中的文档。如果这个指定名称或 id 的框架或者窗口不存在，浏览器将打开一个新的窗口，给这个窗口一个指定的标记，然后将新的文档载入那个窗口。从此以后，超链接文档就可以指向这个新的窗口 | <ul><br/>  `<li><a href="pref.html" target="view_window">Preface</a></li>`  `<li><a href="chap1.html" target="view_window">Chapter 1</a></li><li><a href="chap2.html" target="view_window">Chapter 2</a></li><li><a href="chap3.html" target="view_window">Chapter 3</a></li>`</ul> |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |


| attr            | description                | example                                         |
| --------------- | -------------------------- | ----------------------------------------------- |
| target="_blank" | 在新标签页打开链接         | \<a href="test.html" target="_blank">test</a>   |
| target="_self"  | 默认的, 当前标签页打开链接 | \<a href="video.html" target="_self">123123</a> |
|                 |                            |                                                 |



# jquery



#### 1. 函数



| function     | description                                                  | example                                                      |
| ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| mouseenter() | 当鼠标指针穿过元素时，会发生 mouseenter 事件                 | $("p").mouseenter(function(){   $("p").css("background-color","yellow"); }); |
| mouseleave() | 鼠标离开                                                     |                                                              |
| find()       | 获得当前元素集合中每个元素的后代，通过选择器、jQuery 对象或元素来筛选。 | $("p").find("span").css('color','red');                      |
| attr()       | 为属性赋值                                                   | $("#test-weekday").attr("placeholder",weekday);              |
| height()     | 设置高度                                                     | $('#table-div').height($('#testScreen').css('height'));      |
| css()        | 设置样式                                                     | $('#table-div').css({'background-color': 'red'})             |
| html(string) |                                                              | document.getElementById(divId).innerHTML = txt;<br>等效 ->  $("#div").html(txt); |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |





#### 2. jquery form 文件 上传

```js
                        function uploadDutyExcel() {
                            var formData=new FormData($("#uploadDutyExcel")[0]);

                            $.ajax({
                                url:"/ms-mcms/dutyDetail/importDutyData",
                                data:formData,
                                type: "post",
                                async:false,
                                cache: false,
                                contentType: false,
                                processData: false,
                                success:function (res) {
                                    console.log("上传成功")
                                    console.log(res)
                                },
                                error: function (res) {
                                    console.log("上传失败")
                                }
                            })

                        }
```





#### 3. ajax

1. processData : 默认情况下会将发送的数据序列化以适应默认的内容类型application/x-www-form-urlencoded ,如果想发送不想转换的的信息的时候需要手动将其设置为false,在我遇到的是传输的是blob对象的时候就是不需要将传输的数据序列化,一般的还有类似DOM树等

2. contentType: 

   在网络请求中，常用的Content-Type有如下：

> text/html, text/plain, text/css, text/javascript, image/jpeg, image/png, image/gif,
> application/x-www-form-urlencoded, multipart/form-data, application/json, application/xml 等。



其中: 

> text/html, text/plain, text/css, text/javascript, image/jpeg, image/png, image/gif, 都是常见的页面资源类型。



> application/x-www-form-urlencoded, multipart/form-data, application/json, application/xml 这四个是ajax的请求，表单提交或上传文件的常用的资源类型



form表单中可以定义enctype属性，该属性的含义是在发送到服务器之前应该如何对表单数据进行编码。默认的情况下，表单数据会编码为

> application/x-www-form-unlencoded



在使用文件上传时候，使用 

> multipart/form-data, 不对字符编码













# bootstrap

#### 1. 栅格

col-xs-* 超小屏幕 手机 (<768px)

.col-sm-* 小屏幕 平板 (≥768px)

.col-md-* 中等屏幕 桌面显示器 (≥992px)

.col-lg-* 大屏幕 大桌面显示器 (≥1200px)











