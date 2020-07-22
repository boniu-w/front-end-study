
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





#### 3. js   hasOwnProperty()

Object的`hasOwnProperty()`方法返回一个布尔值，判断对象是否包含特定的自身（非继承）属性

```java
obj.hasOwnProperty("id");  // obj 是否有这个 id 属性  
```



#### 4. this.$emit('ok')

子组件 向父组件 传值