
# 创建一个基于 webpack 模板的新项目
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

#### 1. vue中的单选框

```js
	<a-checkbox-group v-decorator="['personTypeId', {}]">
        <a-checkbox :value="1">主体</a-checkbox>
    </a-checkbox-group>
```





#### 2. vue computed

#### 3. this.$emit('ok')

子组件 向父组件 传值



-----------------------------------------------------------------------------------------------------------------------------------------------------------



# 								js 部分

-----------------------------------------------------------------------------------------------------------------------------------------------------------

#### 1. JavaScript  hasOwnProperty()  : obj 的方法

Object的`hasOwnProperty()`方法返回一个布尔值，判断对象是否包含特定的自身（非继承）属性

```java
obj.hasOwnProperty("id");  // obj 是否有这个 id 属性  
```



#### 2. JavaScript  .join()  : 数组的方法

join() 用于把数组中的所有元素放到一个字符串中

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