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



































