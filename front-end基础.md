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
| window.onload=function(){}             | 用于在网页加载完毕后立刻执行的操作，即当 HTML 文档加载完毕后，立刻执行某个方法, 因为 JavaScript 中的函数方法需要在 HTML 文档渲染完成后才可以使用，如果没有渲染完成，此时的 DOM 树是不完整的，这样在调用一些 JavaScript 代码时就可能报出"undefined"错误。 |                                               |
| document.write()                       | 在文档已加载后使用它（比如在函数中），会覆盖整个文档。       | document.write("<h1>This is a heading</h1>"); |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
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





#### 4. 知识点

- 浏览器的标签页显示 文字 和 图标

  ```html
  <title>天津公安经侦综合信息网</title>
  <link rel="icon" sizes="any" href="/ms-mcms/templets/1/company1804/images/JingHui.png">
  ```


#### 5. 引入公共部分

- 引入公共js  common.js

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

  

# jquery



| function     | description                                                  | example                                                      |
| ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| mouseenter() | 当鼠标指针穿过元素时，会发生 mouseenter 事件                 | $("p").mouseenter(function(){   $("p").css("background-color","yellow"); }); |
| mouseleave() | 鼠标离开                                                     |                                                              |
| find()       | 获得当前元素集合中每个元素的后代，通过选择器、jQuery 对象或元素来筛选。 | $("p").find("span").css('color','red');                      |
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
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |
|              |                                                              |                                                              |







# bootstrap

#### 1. 栅格

col-xs-* 超小屏幕 手机 (<768px)

.col-sm-* 小屏幕 平板 (≥768px)

.col-md-* 中等屏幕 桌面显示器 (≥992px)

.col-lg-* 大屏幕 大桌面显示器 (≥1200px)











