# vue 部分

## 1. 创建一个基于 webpack 模板的新项目

 vue init webpack my-project

 cd my-project
 cnpm install

 npm start (npm run dev)

---

document.write(vm.$el === document.getElementById('vue_det')) // true
 -----------------------------------------------------------------------
v-model不仅可以给input赋值还可以获取input中的数据，而且数据的获取是实时的，因为语法糖中是用@input对输入框进行监听的。
 -----------------------------------------------------------------------


## 2. vue中的单选框

```js
	<a-checkbox-group v-decorator="['personTypeId', {}]">
        <a-checkbox :value="1">主体</a-checkbox>
    </a-checkbox-group>
```





## 3. vue watch created computed



created: html加载完成之前，执行。执行顺序：父组件-子组件

mounted: html加载完成后执行。执行顺序：子组件-父组件

methods：事件方法执行

watch：watch是去监听一个值的变化，然后执行相对应的函数。

computed：computed是计算属性，也就是依赖其它的属性计算所得出最后的值





- computed用来监控自己定义的变量，该变量不在data里面声明，直接在computed里面定义，然后就可以在页面上进行双向数据绑定展示出结果或者用作其他处理；
- computed比较适合对多个变量或者对象进行处理后返回一个结果值，也就是数多个变量中的某一个值发生了变化则我们监控的这个值也就会发生变化，举例：购物车里面的商品列表和总金额之间的关系，只要商品列表里面的商品数量发生变化，或减少或增多或删除商品，总金额都应该发生变化。这里的这个总金额使用computed属性来进行计算是最好的选择



## 4. this.$emit('ok')

子组件 向父组件 传值



## 5. mounted

通常是为 metheds 函数提前定义（ 类似提前声明变量 进入页面内容全部渲染完成后自动引函数），即

```js
mounted() {
  this.submit()
},
methods: {
  submit() {
    this.select.List = [];
    for (var j = 0; j < this.select.label.length; j++) {
      var Name = this.ToLabel(this.select.label[j])
      this.select.List.push(Name);
    }
  }
```



## 6. watch

watch的作用可以监控一个值的变换，并调用因为变化需要执行的方法。可以通过watch动态改变关联的状态,

即监听, watch主要用于监控vue实例的变化，它监控的变量当然必须在data里面声明才可以，它可以监控一个变量，也可以是一个对象，

-----------------------------------------------------------------------------------------------------------------------------------------------------------



## 7. $t()

$t是挂到了Vue.prototype上的一个方法，接受一个字符串作为参数

```vue
  <el-form-item :label="$t('fm.config.widget.model')" v-if="data.type!='grid'">
        <el-input v-model="data.model"></el-input>
  </el-form-item>
```





## 8. 生命周期函数

created

mounted



<img src=".\img\lifecycle.png" style="zoom:50%;" />



## 9. 绑定

插值: {{}}

v-model: 双向绑定

v-bind: 绑定属性

v-on:  @



## 10. 路由

声明式: 	\<route-link :to="">

编程式:  route.push(...)



# 								js 部分

## I. function



| <span style="white-space: nowrap;">方法&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">描述&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">例子&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| String  join()                                               | 把数组转成字符串                                             |                                                              |
| 长度  push()                                                 | 在数组的后面添加元素                                         |                                                              |
| var formData = new FormData().append("",val)                 | 为formdata添加属性                                           |                                                              |
| object.assign()                                              | 用于将所有可枚举属性的值从一个或多个源对象复制到目标对象。它将返回目标对象。 |                                                              |
| obj.hasOwnProperty("id");                                    | obj 是否有这个 id 属性                                       |                                                              |
| test()                                                       | 用于检测一个字符串是否匹配某个模式. RegExpObject.test(*string*) | var regex = /^1[3\|4\|5\|7\|8]\d{9}$/;<br>var phone = 18929382734<br>var boo = regex.test(phone) |
| JSON.parse(xhr.responseText)                                 | 将json字符串 转换为对象                                      |                                                              |
| JSON.stringify(JSONObject)                                   | 把JSONObject 转化为 JSON 规则的字符串                        |                                                              |
| str.replace(/\s+/g, "")                                      | 去空格                                                       | var me='王  刚'<br />me=me.replace(/\s+/g, "")<br />console.log(me) // 王刚 |



json 字符串示例:

```json
"{"data":{"id":"d0af2e7687aa4fb9b1d108a0875f988f","dutyLeader":"18","onDutyMonitor":"18","onDutyMember":"雷米，吉米，可汗，美队","flexibleMonitor":"18","flexibleMember":"雷米，吉米，可汗，美队","group":null,"dutyDate":"2020-12-03 00:00:00","createTime":"2020-12-03T02:31:09.000+0000","updateTime":"2020-12-03T02:31:09.000+0000"}}"
```

JSONObject 示例:

```json
{
	"data": {
		"id": "d0af2e7687aa4fb9b1d108a0875f988f",
		"dutyLeader": "18",
		"onDutyMonitor": "18",
		"onDutyMember": "雷米，吉米，可汗，美队",
		"flexibleMonitor": "18",
		"flexibleMember": "雷米，吉米，可汗，美队",
		"group": null,
		"dutyDate": "2020-12-03 00:00:00",
		"createTime": "2020-12-03T02:31:09.000+0000",
		"updateTime": "2020-12-03T02:31:09.000+0000"
	}
}
```



## II. 标签



| label    | description                                  | example |
| -------- | -------------------------------------------- | ------- |
| noscript | 用来定义在脚本未被执行时的替代内容（文本）。 |         |
|          |                                              |         |
|          |                                              |         |





## 1. JavaScript  hasOwnProperty()  : obj 的方法

Object的`hasOwnProperty()`方法返回一个布尔值，判断对象是否包含特定的自身（非继承）属性

```java
obj.hasOwnProperty("id");  // obj 是否有这个 id 属性  
```



## 2. JavaScript  .join()  : 数组的方法

join() 用于把数组中的所有元素放到一个字符串中, 

arrayobject.join(separator);



separator : 可选,指定使用的分隔符,如果省略,则使用逗号作为分隔符;



返回的是个 字符串



## 3. push() :  数组的方法

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





## 4. sessionStorage.setItem

使用 sessionStorage 创建一个本地存储的 key/value 对

sessionStorage.getItem(key);



`sessionStorage` 属性允许你访问一个，对应当前源的 session [`Storage`](https://developer.mozilla.org/zh-CN/docs/Web/API/Storage) 对象。它与 [`localStorage`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/localStorage) 相似，不同之处在于 `localStorage` 里面存储的数据没有过期时间设置，而存储在 `sessionStorage` 里面的数据在页面会话结束时会被清除。



## 5. el

获取{}中指定的对象（参数、对象等）的值, 其搜寻的范围依次是：page、request、session、application

request.getAttribute(name) === ${name} 



## 6. js内置对象

Math

Date

Array

String



## 7. 立即执行函数

(function(arg){})(arg)

前半部分: (function(形参){}) 匿名函数

后半部分: (实参)传入实参, 并立即执行



**js中(function(){}()),(function(){})(),$(function(){});之间的区别**

1. (function(){}())与(function(){})()

   这两种写法，都是一种`立即执行函数`的写法，即[IIFE (Immediately Invoked Function Expression)](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression)。这种函数在函数定义的地方就直接执行了

   IIFE函数的调用方式通常是将函数表达式、它的调用操作符、[分组操作符](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Grouping)放到一个括号内，来告诉解释器这里有一个需要立即执行的函数。

2. $(function(){/*...*/});是$(document).ready(function(){/*...*/})的简写形式，是在DOM加载完成后执行的回调函数，并且只会执行一次









## 8. 新窗口打开 , 当前页面打开

```js
onclick="window.open('https://www.baidu.com')" // 新窗口打开
window.location.href='https://www.baidu.com'  // 当前页面打开
```



## 9. 将两个字符串数组 合并为一个 对象

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



## 10. 数组



| function                                                     | description                                                  | example                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| push()                                                       | 在数组的后面添加元素                                         |                                                              |
| unshift()                                                    | 将数据添加到数组起始位,                                      | var fruits = ["Banana", "Orange", "Apple", "Mango"];<br/>	fruits.unshift("Lemon","Pineapple");<br />Lemon,Pineapple,Banana,Orange,Apple,Mango |
| join()<br />arrayobject.join(separator);                     | 把数组中的所有元素放到一个字符串中,返回的是个 字符串,separator : 可选,指定使用的分隔符,如果省略,则使用逗号作为分隔符; |                                                              |
| slice()<br />arrayObject.slice(start,end)                    | 截取数组, 返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素,slice() 方法可从已有的数组中返回选定的元素。<br/> 请注意，该方法并不会修改数组，而是返回一个子数组。如果想删除数组中的一段元素，应该使用方法 Array.splice()。 | car = car.slice(1, car.length);                              |
| map(function(currentValue,index,arr), thisValue)             | 返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值, 数组中的每个元素都会执行这个函数, map() 方法按照原始数组元素顺序依次处理元素。map() 不会改变原始数组, map() 不会对空数组进行检测。 | {this.props.data.map((data, index) => <li key={index}>{data}</li>)} |
| reduce()<br />array.reduce(function(total, currentValue, currentIndex, arr), initialValue) | 接收一个函数作为累加器，数组中的每个值（从左到右）开始缩减，最终计算为一个值。 |                                                              |
| pop()                                                        | 删除(弹出)数组最后一个元素, 有返回值                         |                                                              |
| shift()                                                      | 删除数组第一个元素                                           |                                                              |



- array.reduce(function(total, currentValue, currentIndex, arr), initialValue)

| 参数                                      | 描述                                                         |
| :---------------------------------------- | :----------------------------------------------------------- |
| *function(total,currentValue, index,arr)* | 必需。用于执行每个数组元素的函数。 函数参数:参数描述*total*必需。*初始值*, 或者计算结束后的返回值。*currentValue*必需。当前元素*currentIndex*可选。当前元素的索引*arr*可选。当前元素所属的数组对象。 |
| *initialValue*                            | 可选。传递给函数的初始值                                     |

示例:

```js
// 合并数组
function testReduce() {
    var a1=[1,2,3,4,5]
    var a2=['sdf','sdf','qwe','rty','zxc']

    var obj= a1.reduce(function(res,value,index){
        res[a2[index]]=value;
        return res;
    },{})

    console.log(obj,typeof obj)

     obj= a2.reduce(function(res,value,index){
        res[a1[index]]=value;
        return res;
    },{})

    console.log(obj,typeof obj)

}
```







## 11. bootstraptable

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









## 12. 日期 按一定的格式输出

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



## 13. formdata

FormData 对象 数据  , 后台用 request.getparameter 接收 也可以用 实体类接收或 map

但是 , 用ajax 会报一个错误, 用xmlhttprequest 不报错



```js
function submit3() {
            var name = $("#name").val();
            let age = $("#age").val();

            let obj = {};
            obj = Object.assign({
                name: name,
                age: age
            }, obj)

            console.log(obj)

            let request = new XMLHttpRequest();

            request.open("post", "http://127.0.0.1:33333/validateTestController/validatePost", false);
            request.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
            request.send(obj)         // 后台接收不到 数据

            console.log("request  ", request)
            if ((request.status >= 200 && request.status < 300) || request.status == 304) {

                console.log("200", request.status)
            } else {
                console.log("xmlHttpRequest 的状态为: ", request.status)
            }

            /////////////////////////////////////////////////////////////////////////////
            var formData = new FormData();

            formData.append('name', name);
            formData.append('age', age);
            formData.append('birthDate', 1940);

            var xhr = new XMLHttpRequest();
            xhr.open('POST', 'http://127.0.0.1:33333/validateTestController/validatePost',false);
            xhr.send(formData);    // 后台可以接收到 数据 实体类接收

            console.log(formData)
            if ((request.status >= 200 && request.status < 300) || request.status == 304) {

                console.log("formData 200", request.status)
            } else {
                console.log("formData xmlHttpRequest 的状态为: ", request.status)
            }

        }
```



```js
        function submit4() {
            var name = $("#name").val();
            let age = $("#age").val();

            let formData = new FormData();
            formData.append('name', name)
            formData.append('age', age)

            console.log(formData)
            $.ajax({
                url: "http://127.0.0.1:33333/validateTestController/validate",
                data: formData,  // 后台接收不到数据, 而且前台就报错: Uncaught TypeError: Illegal invocation
                type: "get",

                // cache: false,
                // processData: false,  // 告诉jQuery不要去处理发送的数据 processData 可不得了,
                // contentType: false,  // 告诉jQuery不要去设置Content-Type请求头
                success: function (res) {
                    console.log(res)
                },
                error: function () {
                    console.log("error")
                }
            })

        }
```



```js
function submit1() {
    var name = $("#name").val();
    let age = $("#age").val();

    let obj = {};
    obj["name"] = name;
    obj["age"] = age;

    console.log(obj)
    $.ajax({
        url: "http://127.0.0.1:33333/validateTestController/validate",
        data: obj,  // 后台可以接收数据 用实体类
        type: "get",

        cache: false,
        // processData: false,  // 告诉jQuery不要去处理发送的数据 processData 可不得了,
        // contentType: false,  // 告诉jQuery不要去设置Content-Type请求头
        success: function (res) {
            console.log(res)
        },
        error: function () {
            console.log("error")
        }
    })

}
```



~~由此可见, 用ajax 就不要使用 formdata 对象提交数据,  要提交formdata 对象数据 使用xmlhttprequest, ajax 提交数据用object~~

~~总结: ajax -> object~~

~~xmlhttprequest -> formdata~~



**注意: 只有false request.status 才 >=200**

使用formdata 封装表单数据

```js
<div id="div3">

    <form id="form3">
        <input type="text" name="name" value="">
        <input type="number" name="age">
        <input type="button" value="sendForm" onclick="sendForm()">
    </form>

    <script>

        var selectors = "#form3";
        var form = document.querySelector(selectors)

        function sendForm() {
           var formData = new FormData(form);

            formData.append("sex","1")

            var request = new XMLHttpRequest();
            request.open('POST', 'http://127.0.0.1:33333/validateTestController/getFormData',false);
            request.send(formData);    // 后台可以接收到 数据

            console.log(formData)
            if ((request.status >= 200 && request.status < 300) || request.status == 304) {
                console.log("formData 200", request.status)
            } else {
                console.log("formData xmlHttpRequest 的状态为: ", request.status)
            }

        }
    </script>

</div>
```



formData 的错误用法

```js
formData["birthday"] = "2020-10-2";
formData["name"] = "wg"
formData["age"] = 12;
```



正确用法

```js
formData.append("sex",1);
formData.append("sex",0);
```

并且 sex 并不会被0取代, 后台接收的sex=1;



## 14. const, let, var 

1. const定义的变量不可以修改，而且必须初始化
2. var定义的变量可以修改，如果不初始化会输出undefined，不会报错。
3. let是块级作用域，函数内部使用let定义后，对函数外部无影响。





## 15. a标签的点击事件

> \<a href="javascript:void(0);" onclick="js_method()"</a>



## 16. date





## 17. this

1. 箭头函数

   首先箭头函数其实是没有 this 的，箭头函数中的 this 只取决包裹箭头函数的第一个普通函数的 this

```js
function a() {
  return () => {
    return () => {
      console.log(this)
    }
  }
}
console.log(a()()()) // window
```

2. 普通函数

   ```js
   function foo() {
     console.log(this.a, this)
   }
   var a = 1
   foo() // 对于直接调用 foo 来说，不管 foo 函数被放在了什么地方，this 一定是 window
   
   const obj = {
     a: 2,
     foo: foo
   }
   obj.foo() // 谁调用了函数，谁就是 this，所以在这个场景下 foo 函数中的 this 就是 obj 对象
   
   const c = new foo()  // 对于 new 的方式来说，this 被永远绑定在了 c 上面，不会被任何方式改变 this
   
   ```

   接下来我们一个个分析上面几个场景

   - 对于直接调用 foo 来说，不管 foo 函数被放在了什么地方，this 一定是 window
   - 对于 obj.foo() 来说，我们只需要记住，谁调用了函数，谁就是 this，所以在这个场景下 foo 函数中的 this 就是 obj 对象
   - 对于 new 的方式来说，this 被永远绑定在了 c 上面，不会被任何方式改变 this

3. 多个规则同时出现

   不同的规则之间会根据优先级最高的来决定 this 最终指向哪里

   new 的方式优先级最高，接下来是 bind 这些函数，然后是 obj.foo() 这种调用方式，最后是 foo 这种调用方式，同时，箭头函数的 this 一旦被绑定，就不会再被任何方式所改变





## 18. void(0)

> `void`运算符对给定的表达式进行求值，然后返回 `undefined`。

先前看[underscore](https://underscorejs.bootcss.com/docs/underscore.html)的源码，里面有个判断是这样写的:

```
if(context === void 0) return func;
```

当时第一次看到有点懵，竟然还有这种操作，恕我孤陋寡闻。后来查阅了[文档](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/void)才发现，原来`void 0`写法等价于`undefined`，即上面的代码等价于：

```
if(context === undefined) return func;
```

文档描述中指出：void 运算符通常只能用于获取 `undefined`的原始值，一般使用 `void(0)`（等同于`void 0`）。在上述情况中，也可以使用全局变量 `undefined` 来代替（假定其仍是默认值）。为什么说假设仍是默认值呢？我们下面分析一下

- void(0) vs undefined

我们先看下undefined的文档说明

> undefined是js原始类型值之一，也是全局对象window的属性，在部分低级别的浏览器（IE7,IE8）中可以被修改，在局部作用域中也可以被修改。

```
var undefined = '111'
console.log(undefined) //111

在旧版的IE中直接改写了undefined。
```

也就是说当你想知道一个变量是不是等于undefined的时候，直接判断就不安全了。

接下来我们在看一段js

```js
var testUndefined = function(){
  var obj = {}
  var undefined = 'underscore'
  var window = {
    'undefined': 'bb'
  }
  console.log(window) //{'undefined': 'bb'}
  console.log(undefined) //underscore
  console.log(window.undefined) //bb
  console.log(obj.name === undefined) // false
  console.log(obj.name === window.undefined) // false
  console.log(obj.name === (void 0)) // true
}
testUndefined()
```

从上面的代码中可以看出，window,undefined本身在局部作用域中是可以被修改的。这样将导致判断undefined是有风险的。

为什么要用void 0 来代替undefined

> 通过上述栗子可以看出。在某些情况下用全局的undefined判断是有风险的。因为他可能会被修改过。而`void 0`在任何情况下返回的都是`undefined`，同时兼容性上所有浏览器都是支持的。





## 19. a标签中href="javacript:;" href="javacript:void(0);" href="#"区别

在使用<a>标签时，经常会绑定其他事件比如onclick，这候我们会给<a>标签的href属性赋值为“#”，“javacript:;” ，“javacript:void(0);”等

一、href="javacript:;" 用这个的话会出现浏览器访问“javascript:;”这个地址的现象，所以任何情况下都不建议使用；

二、href="javacript:void(0);" 表示点击这个链接后执行一条javascript语句：void(0); 这条语句表示什么也不做，是个空语句。当绑定了onclick()事件并且点击后，页面会停留在原地；

三、href="#" 这个是HTML的链接用法，意思是跳转到页面顶部，如果想快速地返回到顶部，那么就用这个链接，这种用法叫做锚。

四、如果想使用a标签来对一个函数进行调用，有两种方式：

```js
   <a href="javascript:void(0);  onclick=hello();">点我</a> 
   <a href="javascript:hello();">点我</a>
```



## 20. js表达式,  js代码

1. 表达式: 会产生一个值, 可以放在任何需要值的地方

   下面都是表达式

   (1). a

   (2). a+b

   (3). demo(1)

   (4). arr.map()

   (5). function test(){}

2. 语句, 代码

   下面都是语句: 

   (1). if(){}

   (2). for(){}

# npm 部分

## 1. 安装 依赖

```
cnpm install echarts --save
```



## 2. cnpm

```js
npm set registry https://registry.npm.taobao.org
npm set sass_binary_site https://npm.taobao.org/mirrors/node-sass
```





# html

## 1. meta

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



| meta |      |      |
| ---- | ---- | ---- |
|      |      |      |
|      |      |      |
|      |      |      |



设置屏幕密度为高频，中频，低频自己主动缩放，禁止用户手动调整缩放

```html
<meta name="viewport" content="width=device-width, target-densitydpi=high-dpi, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
```





## 2. document.domain

跨域访问的

默认情况下，document.domain存放的是载入文档的服务器的主机名，可以手动设置这个属性，不过是有限制的，只能设置成当前域名或者上级的域名，并且必须要包含一个.号，也就是说不能直接设置成顶级域名。例如：id.qq.com，可以设置成qq.com，但是不能设置成com。

具有相同document.domain的页面，就相当于是处在同域名的服务器上，如果协议和端口号也是一致，那它们之间就可以跨域访问数据。





## 3. function,attribute



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
| e.which                                | `which`属性用于**返回触发当前事件时按下的键盘按键或鼠标按钮**。该属性属于jQuery的`Event`对象(实例) |                                               |
| document.querySelector()               | 返回文档中匹配指定 CSS 选择器的一个元素。仅仅返回匹配指定选择器的第一个元素。如果你需要返回所有的元素，请使用 querySelectorAll() 方法替代。 | document.querySelector("#enterEvent");        |
| onerror                                | 目前 见于图片的 属性                                         | onerror=`javascript:this.src=''图片" '        |
| location                               | location 对象描述了与一个给定的 Window对象关联的完整 URL。location对象的每个属性都描述了URL的不同特性。 |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |
|                                        |                                                              |                                               |




- window.onload 与 document.ready

  1. document.ready：document.ready可以写多个.ready，可以执行多次，第N次都不会被上一次覆盖。

  2. onload：onload只能执行一次，如果有多个，那么第一次的执行会被覆盖

  3. 执行速度不同 

     1. onload：onload除了要等待DOM被创建还要等到包括大型图片、音频、视频在内的所有外部资源都完全加载。如果加载图片和媒体内容花费了大量时间，用户就会感受到定义在onload事件上的代码在执行时有明显的延迟。
     2. document.ready：document.ready函数只需对 DOM 树的等待，而无需对图像或外部资源加载的等待，从而执行起来更快。

  4. 加载程度不同

     1. document.ready：在DOM加载完成后bai就可以可以对DOM进行操作。一du般情况一个页面响应加载的顺序是，域名解析-加载html-加载js和css-加载图片等其他信息。那么Dom Ready应该在“加载js和css”和“加载图片等其他信息”之间，就可以操作Dom了。

     2. onload：在document文档加载完成后就可以可以对DOM进行操作，document文档包括了加载图片等其他信息。那么Dom Load就是在页面响应加载的顺序中的“加载图片等其他信息”之后，就可以操作Dom了。



### location

location.hash : 一般情况下为URL后 "#" 及其后面一部分组成，如http://www.test.com/#/something，其中http://www.test.com为真实的路径，而#/something则为网页中的位置，称之为**锚点**, 在访问锚点时会自动跳到锚点所在的网页位置，

在对hash写时有个需要注意的地方，如下所示

```javascript
//当前URL为http://www.test.com/
location.hash = "#/test"	
//http://www.test.com/#/test
locationl.hash = "/#/test"	
//http://www.test.com/#/#/test
```

当写入第一个字符不为为 "#" 时会自动生成一个 "#" 在字符串之前，再把字符串追加到生成的#后面

这样会造成有两个#,此时location.hash输出 "#/#/test"



location: 该属性获取页面的url 地址

| 属性     | 描述                              |
| :------- | :-------------------------------- |
| hash     | 从井号 (#) 开始的 URL（锚）       |
| host     | 主机名和当前 URL 的端口号         |
| hostname | 当前 URL 的主机名                 |
| href     | 完整的 URL                        |
| pathname | 当前 URL 的路径部分               |
| port     | 当前 URL 的端口号                 |
| protocol | 当前 URL 的协议                   |
| search   | 从问号 (?) 开始的 URL（查询部分） |







## 4. 标签页显示 文字 和 图标

- 浏览器的标签页显示 文字 和 图标

  ```html
  <title>天津公安经侦综合信息网</title>
  <link rel="icon" sizes="any" href="/ms-mcms/templets/1/company1804/images/JingHui.png">
  ```


## 5. 引入公共部分

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




## 6. 列表

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



## 7. 属性



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



## 8. 选择器



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



| [*](https://www.runoob.com/jquery/jq-sel-all.html)           | $("*")                        | 所有元素                                                     |
| ------------------------------------------------------------ | ----------------------------- | ------------------------------------------------------------ |
| [#*id*](https://www.runoob.com/jquery/jq-sel-id.html)        | $("#lastname")                | id="lastname" 的元素                                         |
| [.*class*](https://www.runoob.com/jquery/jq-sel-class.html)  | $(".intro")                   | class="intro" 的所有元素                                     |
| [.*class,*.*class*](https://www.runoob.com/jquery/sel-multiple-classes.html) | $(".intro,.demo")             | class 为 "intro" 或 "demo" 的所有元素                        |
| [*element*](https://www.runoob.com/jquery/jq-sel-element.html) | $("p")                        | 所有 <p> 元素                                                |
| [*el1*,*el2*,*el3*](https://www.runoob.com/jquery/sel-multiple-elements.html) | $("h1,div,p")                 | 所有 <h1>、<div> 和 <p> 元素                                 |
|                                                              |                               |                                                              |
| [:first](https://www.runoob.com/jquery/sel-first.html)       | $("p:first")                  | 第一个 <p> 元素                                              |
| [:last](https://www.runoob.com/jquery/sel-last.html)         | $("p:last")                   | 最后一个 <p> 元素                                            |
| [:even](https://www.runoob.com/jquery/sel-even.html)         | $("tr:even")                  | 所有偶数 <tr> 元素，索引值从 0 开始，第一个元素是偶数 (0)，第二个元素是奇数 (1)，以此类推。 |
| [:odd](https://www.runoob.com/jquery/sel-odd.html)           | $("tr:odd")                   | 所有奇数 <tr> 元素，索引值从 0 开始，第一个元素是偶数 (0)，第二个元素是奇数 (1)，以此类推。 |
|                                                              |                               |                                                              |
| [:first-child](https://www.runoob.com/jquery/jq-sel-firstchild.html) | $("p:first-child")            | 属于其父元素的第一个子元素的所有 <p> 元素                    |
| [:first-of-type](https://www.runoob.com/jquery/sel-firstoftype.html) | $("p:first-of-type")          | 属于其父元素的第一个 <p> 元素的所有 <p> 元素                 |
| [:last-child](https://www.runoob.com/jquery/sel-lastchild.html) | $("p:last-child")             | 属于其父元素的最后一个子元素的所有 <p> 元素                  |
| [:last-of-type](https://www.runoob.com/jquery/sel-lastoftype.html) | $("p:last-of-type")           | 属于其父元素的最后一个 <p> 元素的所有 <p> 元素               |
| [:nth-child(*n*)](https://www.runoob.com/jquery/sel-nthchild.html) | $("p:nth-child(2)")           | 属于其父元素的第二个子元素的所有 <p> 元素                    |
| [:nth-last-child(*n*)](https://www.runoob.com/jquery/sel-nthlastchild.html) | $("p:nth-last-child(2)")      | 属于其父元素的第二个子元素的所有 <p> 元素，从最后一个子元素开始计数 |
| [:nth-of-type(*n*)](https://www.runoob.com/jquery/sel-nthoftype.html) | $("p:nth-of-type(2)")         | 属于其父元素的第二个 <p> 元素的所有 <p> 元素                 |
| [:nth-last-of-type(*n*)](https://www.runoob.com/jquery/sel-nthlastoftype.html) | $("p:nth-last-of-type(2)")    | 属于其父元素的第二个 <p> 元素的所有 <p> 元素，从最后一个子元素开始计数 |
| [:only-child](https://www.runoob.com/jquery/sel-onlychild.html) | $("p:only-child")             | 属于其父元素的唯一子元素的所有 <p> 元素                      |
| [:only-of-type](https://www.runoob.com/jquery/sel-onlyoftype.html) | $("p:only-of-type")           | 属于其父元素的特定类型的唯一子元素的所有 <p> 元素            |
|                                                              |                               |                                                              |
| [parent > child](https://www.runoob.com/jquery/sel-parent-child.html) | $("div > p")                  | <div> 元素的直接子元素的所有 <p> 元素                        |
| [parent descendant](https://www.runoob.com/jquery/sel-parent-descendant.html) | $("div p")                    | <div> 元素的后代的所有 <p> 元素                              |
| [element + next](https://www.runoob.com/jquery/sel-previous-next.html) | $("div + p")                  | 每个 <div> 元素相邻的下一个 <p> 元素                         |
| [element ~ siblings](https://www.runoob.com/jquery/sel-previous-siblings.html) | $("div ~ p")                  | <div> 元素同级的所有 <p> 元素                                |
|                                                              |                               |                                                              |
| [:eq(*index*)](https://www.runoob.com/jquery/sel-eq.html)    | $("ul li:eq(3)")              | 列表中的第四个元素（index 值从 0 开始）                      |
| [:gt(*no*)](https://www.runoob.com/jquery/sel-gt.html)       | $("ul li:gt(3)")              | 列举 index 大于 3 的元素                                     |
| [:lt(*no*)](https://www.runoob.com/jquery/sel-lt.html)       | $("ul li:lt(3)")              | 列举 index 小于 3 的元素                                     |
| [:not(*selector*)](https://www.runoob.com/jquery/jq-sel-not.html) | $("input:not(:empty)")        | 所有不为空的输入元素                                         |
|                                                              |                               |                                                              |
| [:header](https://www.runoob.com/jquery/sel-header.html)     | $(":header")                  | 所有标题元素 <h1>, <h2> ...                                  |
| [:animated](https://www.runoob.com/jquery/sel-animated.html) | $(":animated")                | 所有动画元素                                                 |
| [:focus](https://www.runoob.com/jquery/jq-sel-focus.html)    | $(":focus")                   | 当前具有焦点的元素                                           |
| [:contains(*text*)](https://www.runoob.com/jquery/sel-contains.html) | $(":contains('Hello')")       | 所有包含文本 "Hello" 的元素                                  |
| [:has(*selector*)](https://www.runoob.com/jquery/sel-has.html) | $("div:has(p)")               | 所有包含有 <p> 元素在其内的 <div> 元素                       |
| [:empty](https://www.runoob.com/jquery/jq-sel-empty.html)    | $(":empty")                   | 所有空元素                                                   |
| [:parent](https://www.runoob.com/jquery/sel-parent.html)     | $(":parent")                  | 匹配所有含有子元素或者文本的父元素。                         |
| [:hidden](https://www.runoob.com/jquery/sel-hidden.html)     | $("p:hidden")                 | 所有隐藏的 <p> 元素                                          |
| [:visible](https://www.runoob.com/jquery/sel-visible.html)   | $("table:visible")            | 所有可见的表格                                               |
| [:root](https://www.runoob.com/jquery/jq-sel-root.html)      | $(":root")                    | 文档的根元素                                                 |
| [:lang(*language*)](https://www.runoob.com/jquery/jq-sel-lang.html) | $("p:lang(de)")               | 所有 lang 属性值为 "de" 的 <p> 元素                          |
|                                                              |                               |                                                              |
| [[*attribute*\]](https://www.runoob.com/jquery/jq-sel-attribute.html) | $("[href]")                   | 所有带有 href 属性的元素                                     |
| [[*attribute*=*value*\]](https://www.runoob.com/jquery/sel-attribute-equal-value.html) | $("[href='default.htm']")     | 所有带有 href 属性且值等于 "default.htm" 的元素              |
| [[*attribute*!=*value*\]](https://www.runoob.com/jquery/sel-attribute-notequal-value.html) | $("[href!='default.htm']")    | 所有带有 href 属性且值不等于 "default.htm" 的元素            |
| [[*attribute*$=*value*\]](https://www.runoob.com/jquery/sel-attribute-end-value.html) | $("[href$='.jpg']")           | 所有带有 href 属性且值以 ".jpg" 结尾的元素                   |
| [[*attribute*\|=*value*\]](https://www.runoob.com/jquery/sel-attribute-prefix-value.html) | $("[title\|='Tomorrow']")     | 所有带有 title 属性且值等于 'Tomorrow' 或者以 'Tomorrow' 后跟连接符作为开头的字符串 |
| [[*attribute*^=*value*\]](https://www.runoob.com/jquery/sel-attribute-beginning-value.html) | $("[title^='Tom']")           | 所有带有 title 属性且值以 "Tom" 开头的元素                   |
| [[*attribute*~=*value*\]](https://www.runoob.com/jquery/sel-attribute-contains-value.html) | $("[title~='hello']")         | 所有带有 title 属性且值包含单词 "hello" 的元素               |
| [[*attribute**=*value*\]](https://www.runoob.com/jquery/sel-attribute-contains-string-value.html) | $("[title*='hello']")         | 所有带有 title 属性且值包含字符串 "hello" 的元素             |
| [[*name*=*value*\][*name2*=*value2*]](https://www.runoob.com/jquery/sel-multipleattribute-equal-value.html) | $( "input[id][name$='man']" ) | 带有 id 属性，并且 name 属性以 man 结尾的输入框              |
|                                                              |                               |                                                              |
| [:input](https://www.runoob.com/jquery/sel-input.html)       | $(":input")                   | 所有 input 元素                                              |
| [:text](https://www.runoob.com/jquery/sel-input-text.html)   | $(":text")                    | 所有带有 type="text" 的 input 元素                           |
| [:password](https://www.runoob.com/jquery/sel-input-password.html) | $(":password")                | 所有带有 type="password" 的 input 元素                       |
| [:radio](https://www.runoob.com/jquery/sel-input-radio.html) | $(":radio")                   | 所有带有 type="radio" 的 input 元素                          |
| [:checkbox](https://www.runoob.com/jquery/sel-input-checkbox.html) | $(":checkbox")                | 所有带有 type="checkbox" 的 input 元素                       |
| [:submit](https://www.runoob.com/jquery/sel-input-submit.html) | $(":submit")                  | 所有带有 type="submit" 的 input 元素                         |
| [:reset](https://www.runoob.com/jquery/sel-input-reset.html) | $(":reset")                   | 所有带有 type="reset" 的 input 元素                          |
| [:button](https://www.runoob.com/jquery/sel-input-button.html) | $(":button")                  | 所有带有 type="button" 的 input 元素                         |
| [:image](https://www.runoob.com/jquery/sel-input-image.html) | $(":image")                   | 所有带有 type="image" 的 input 元素                          |
| [:file](https://www.runoob.com/jquery/sel-input-file.html)   | $(":file")                    | 所有带有 type="file" 的 input 元素                           |
| [:enabled](https://www.runoob.com/jquery/sel-input-enabled.html) | $(":enabled")                 | 所有启用的元素                                               |
| [:disabled](https://www.runoob.com/jquery/sel-input-disabled.html) | $(":disabled")                | 所有禁用的元素                                               |
| [:selected](https://www.runoob.com/jquery/sel-input-selected.html) | $(":selected")                | 所有选定的下拉列表元素                                       |
| [:checked](https://www.runoob.com/jquery/sel-input-checked.html) | $(":checked")                 | 所有选中的复选框选项                                         |
| .selector                                                    | $(selector).selector          | 在jQuery 1.7中已经不被赞成使用。返回传给jQuery()的原始选择器 |
| [:target](https://www.runoob.com/jquery/jq-sel-target.html)  | $( "p:target" )               | 选择器将选中ID和URI中一个格式化的标识符相匹配的<p>元素       |





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



## 9. 符号 HTML 中有用的字符实体

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



## 10. 问题

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
   
   

## 11. 垂直居中

div的垂直居中问题 vertical-align:middle; 将行距增加到和整个DIV一样高 line-height:200px; 然后插入文字，就垂直居中了。缺点是要控制内容不要换行



## 12. target="_blank"



| <span style="white-space: nowrap;">attribute &emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">description &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">example &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| alt                                                          | 图的一个属性, alt 属性是一个必需的属性，它规定在图像无法显示时的替代文本 | `<img src="smiley-2.gif" alt="Smiley face" width="42" height="42">` |
| target                                                       | 如果在一个 <a> 标签内包含一个 target 属性，浏览器将会载入和显示用这个标签的 href 属性命名的、名称与这个目标吻合的框架或者窗口中的文档。如果这个指定名称或 id 的框架或者窗口不存在，浏览器将打开一个新的窗口，给这个窗口一个指定的标记，然后将新的文档载入那个窗口。从此以后，超链接文档就可以指向这个新的窗口 | <ul><br/>  `<li><a href="pref.html" target="view_window">Preface</a></li>`  `<li><a href="chap1.html" target="view_window">Chapter 1</a></li><li><a href="chap2.html" target="view_window">Chapter 2</a></li><li><a href="chap3.html" target="view_window">Chapter 3</a></li>`</ul> |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |


| attr            | description                | example                                         |
| --------------- | -------------------------- | ----------------------------------------------- |
| target="_blank" | 在新标签页打开链接         | \<a href="test.html" target="_blank">test</a>   |
| target="_self"  | 默认的, 当前标签页打开链接 | \<a href="video.html" target="_self">123123</a> |
|                 |                            |                                                 |





## 13. XMLHttpRequest



```js
function submit3() {
    var name = $("#name").val();
    let age = $("#age").val();

    let obj = {};
    obj["name"] = name;
    obj["age"] = age;

    console.log(obj)

    let request = new XMLHttpRequest();


    request.open("get", "http://127.0.0.1:33333/validateTestController/validate", false);  // false 时, request.status才>=200
    request.send(obj)

    console.log("request  ", request)
    if ((request.status >= 200 && request.status < 300) || request.status == 304) {

        console.log("200",request.status)
    }else {
        console.log("xmlHttpRequest 的状态为: ", request.status)
    }

}
```



## 14.  页面失去焦点

```js
<script>
    document.addEventListener('visibilitychange', function () {
        var isHidden = document.hidden;
        if (isHidden) {
            //失去焦点
            document.title = '小主，快回来';
        }
        else {
            //未失去焦点
            document.title = 'xxx后台管理';
        }
    });
</script>
```






## 15. 基础知识

### 1. 配置window 属性时, 要写在页面的前面

例:

```js
// 行内按钮，点击事件
    window.operateEvents = {
        'click .edit': function (e, value, row, index) {
            alert("edit");
        },
        'click .remove': function (e, value, row, index) {
            alert("remove");
        },
    };

  $('#table').bootstrapTable({
       columns: [
            {
                field: 'edit',
                title: '操作',
                events: operateEvents,
                formatter: operateFormatter,
            }]
  })

// 单元格，自定义设置
    // 操作按钮
    function operateFormatter(value, row, index) {
        return [
            '<a class="edit ml10" href="javascript:void(0)" data-toggle="tooltip" title="Edit">编辑</a>　',
            '<a class="remove ml10" href="javascript:void(0)" data-toggle="tooltip" title="Remove">删除</a>'
        ].join('');
    }

```



### 2. console.log 怎么换行显示

```js
console.log('e ->', e, '\n', ' value -> ', value, ' \n', ' row -> ', row, '\n', ' index -> ', index)
```



## 16. 拖放元素

在拖放的过程中会触发以下事件：

- - 在拖动目标上触发事件

     

    (源元素)

    :

    - ondragstart - 用户开始拖动元素时触发
    - ondrag - 元素正在拖动时触发
    - ondragend - 用户完成元素拖动后触发

- - 释放目标时触发的事件:
    - ondragenter - 当被鼠标拖动的对象进入其容器范围内时触发此事件
    - ondragover - 当某被拖动的对象在另一对象容器范围内拖动时触发此事件
    - ondragleave - 当被鼠标拖动的对象离开其容器范围内时触发此事件
    - ondrop - 在一个拖动过程中，释放鼠标键时触发此事件



## 17. event 对象

|                         |                                                              |      |
| ----------------------- | ------------------------------------------------------------ | ---- |
| event.stopPropagation() | 不再派发事件。阻止捕获和冒泡阶段中当前事件的进一步传播,终止事件在传播过程的捕获、目标处理或起泡阶段进一步传播。调用该方法后，该节点上处理该事件的处理程序将被调用，事件不再被分派到其他节点 |      |
| event.preventDefault(); | 告诉[user agent](https://developer.mozilla.org/zh-CN/docs/Glossary/User_agent)：如果此事件没有被显式处理，它默认的动作也不应该照常执行。此事件还是继续传播，除非碰到事件侦听器调用[`stopPropagation()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Event/stopPropagation) 或[`stopImmediatePropagation()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Event/stopImmediatePropagation)，才停止传播。 |      |
|                         |                                                              |      |









# jquery



## 1. 函数



| function     | description                                                  | example                                                      |
| ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| mouseenter() | 当鼠标指针穿过元素时，会发生 mouseenter 事件                 | $("p").mouseenter(function(){   $("p").css("background-color","yellow"); }); |
| mouseleave() | 鼠标离开                                                     |                                                              |
| find()       | 获得当前元素集合中每个元素的后代，通过选择器、jQuery 对象或元素来筛选。 | $("p").find("span").css('color','red');                      |
| attr()       | 为属性赋值                                                   | $("#test-weekday").attr("placeholder",weekday);              |
| height()     | 设置高度                                                     | $('#table-div').height($('#testScreen').css('height'));      |
| css()        | 设置样式                                                     | $('#table-div').css({'background-color': 'red'})             |
| html(string) |                                                              | document.getElementById(divId).innerHTML = txt;<br>等效 ->  $("#div").html(txt); |
| on()         | 被选元素及子元素上添加一个或多个事件处理程序, on() 方法是 bind()、live() 和 delegate() 方法的新的替代品。该方法给 API 带来很多便利，我们推荐使用该方法，它简化了 jQuery 代码库。如需移除事件处理程序，请使用 [off()](https://www.runoob.com/jquery/event-off.html) 方法。如需添加只运行一次的事件然后移除，请使用 [one()](https://www.runoob.com/jquery/event-one.html) 方法。 | $(document).ready(function(){  $("p").on("click",function(){    alert("段落被点击了。");  }); }); |
| eq()         | 返回带有被选元素的指定索引号的元素。索引号从 0 开头，        | $("td[name='uuid']").eq().text();// name=uuid 的所有td的值   |
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





## 2. jquery form 文件 上传

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





1个例子, 关于不使用\<form>标签, 提交formdata 数据

前台 

```js
    function submit1() {
        var name = $("#name").val();
        let age =  $("#age").val();

        let formData = new FormData();
        formData["name"] = name;
        formData["age"] = age;

        console.log(formData)
        $.ajax({
            url: "http://127.0.0.1:33333/validateTestController/validate",
            data: formData,
            processData: false,
            contentType: false,
            success: function (res) {
                console.log(res.data)
            },
            error: function () {
                console.log("error")
            }
        })

    }

```

在ajax里不加 processData 这个属性, 会报一个错误 : 'append' called on an object that does not implement interface FormData.

那么processData 的具体是什么意思呢?





## 3. ajax

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



### ajax 与 Object 数据类型 

后台接收数据 不能加 @RequestBody

```js
    function ajaxObjectTest() {
        $.ajax({
            url: "http://127.0.0.1:33333/validateTestController/validatePost",
            method: "post",
            data: {name: "wg", age: 12},
            success: function (res) {
                console.log("ajax -> ", res)
            },
            error: function (error) {
                console.log("ajax error -> ", error)
            }
        })
    }
```



### ajax 与 FormData 数据类型

 不能用 

get 的话 会 跨域错误

post 的话 后台得不到数据





# bootstrap

## 1. 栅格

col-xs-* 超小屏幕 手机 (<768px)

.col-sm-* 小屏幕 平板 (≥768px)

.col-md-* 中等屏幕 桌面显示器 (≥992px)

.col-lg-* 大屏幕 大桌面显示器 (≥1200px)

## 2. 调整列之间的宽度

> \<div class="col-md-6 column div-plate-jijianjiancha" style="background-color: white;width: 49.5%; margin-left: 1%;">

## 3.  栅格的间距

间隙宽度为30px（一个列的每边分别是15px）



## 4. 覆盖事件

data-toggle：触发事件的类型

data-target ：事件的作用对象 。

```html
   <button
      type="button"
      class="update-button"
      style="width:70px; height:40px;"
      data-toggle="modal"
      data-target=".update-Dialog"
    > 编辑
   </button>


 <div class="modal fade update-Dialog">
  ...
 </div>
```

点击编辑按钮，弹出一个静态框。

如上例子中的 button，Bootstrap 为这个元素都绑定了特定事件，覆盖了这些元素原本的行为，

以上代码意思：把 class 为 “ update-Dialog ” 的 div  作用为一个 modal（静态框）





# axios



## axios 与 Object 数据类型

 后台接收 要加 @RequestBody 

```js
function axiosTest() {
    axios({
        url: "http://127.0.0.1:33333/validateTestController/validatePost",
        method: "post",
        data: {name: "wg", age: 12}
    })
        .then(function (res) {
            console.log(res)
        })
        .catch(function (error) {
            console.log(error)
        })

}

axiosTest()
```



## axios 与 FormData 数据类型



```js
"Content-Type": "application/x-www-form-urlencoded"  // 对应 formData 类型数据, 如果是json 形式数据 会报如下错误
```

>  Content type 'application/x-www-form-urlencoded;charset=UTF-8' not supported









# 状态码



| 状态码 | 含义                               |
| ------ | ---------------------------------- |
| 415    | 服务器无法处理请求附带的媒体格式！ |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |
|        |                                    |





# css

## 1. 各式各样

| <span style="white-space: nowrap;">css &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;"> 解释 &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> | <span style="white-space: nowrap;">例子&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span> |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| position: relative;                                          | 相对定位,如果对一个元素进行相对定位，它将出现在它所在的位置上。然后，可以通过设置垂直或水平位置，让这个元素“相对于”它的起点进行移动 | #box_relative {   position: relative;   left: 30px;   top: 20px; } |
| :after                                                       | 伪元素在元素之后添加内容,默认地，这个伪元素是行内元素，不过可以使用属性 display 改变这一点。 |                                                              |
| cursor: pointer;                                             | 鼠标经过 变手型                                              | .section4-0 div{     cursor: pointer; }                      |
| content:                                                     |                                                              | :after{<br>content: "hello world"}                           |
| :nth-child(n)                                                | 选择器匹配父元素中的第 n 个子元素，元素类型没有限制。*n* 可以是一个数字，一个关键字，或者一个公式  ,例子: 指定每个 p 元素匹配的父元素中第 2 个子元素的背景色： | p:nth-child(2) {    background:#ff0000; }                    |
| :hover                                                       | 选择器用于选择鼠标指针浮动在上面的元素                       | a:hover {  background-color:yellow; }                        |
| letter-spacing                                               | 字母间距                                                     |                                                              |
| line-height                                                  | 设置行高(行间的距离), 该属性会影响行框的布局。在应用到一个块级元素时，它定义了该元素中基线之间的最小距离而不是最大距离, line-height 与 font-size 的计算值之差（在 CSS 中成为“行间距”）分为两半，分别加到一个文本行内容的顶部和底部。可以包含这些内容的最小框就是行框。 |                                                              |
| white-space                                                  | 能让p 标签内 容 换行, 见下方具体描述                         |                                                              |
| \&nbsp;                                                      | 两个\&nbsp;相当于*一个汉字的宽度* 一个\&nbsp;相当于一个英文字符的宽度 |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |
|                                                              |                                                              |                                                              |





### 省略号 显示 超出的文本

```css
div {  
  white-space:nowrap;/* 规定文本是否折行 */  
  overflow: hidden;/* 规定超出内容宽度的元素隐藏 */
  text-overflow: ellipsis;
  /* 规定超出的内容文本省略号显示，通常跟上面的属性连用，因为没有上面的属性不会触发超出规定的内容 */
}

div {      
  overflow: hidden;      
  text-overflow: ellipsis;      
  display: -webkit-box; /* 将对象作为弹性伸缩盒子模型显示 */      
  -webkit-line-clamp: 4; /* 控制最多显示几行 */      
  -webkit-box-orient: vertical; /* 设置或检索伸缩盒对象的子元素的排列方式 */    
}
```



### CSS的inline、block与inline-block

**块级元素(block)：**

1. 独霸一行，总是在新行上开始+

2. 宽度缺省是它父级元素的100%，除非设定一个宽度
3. 高度、行高、外边距、内边距都可以设置
4. 可以容纳其他内联元素或者其他块元素

**行内元素(inline)：**

1. 和其他元素都在一行上，遇到父级元素边界会自动换行
2. 高、行高以及内外边距都不可以改变
3. 宽度与内容一样宽，且不可改变
4. 对于行内元素，需要注意的是：设置宽度width无效，设置高度无效，可以通过设置line-height来设置，设置margin只有左右有效，上下无效，设置padding只有左右有效，上下无效
5. 

**行内块元素(inline-block)：***

1. 元素排列在一行
2. 宽度默认由内容决定
3. 元素间默认有间距
4. 支持宽高、外边距、内边距的所有样式的设置

|          |                                                              |
| -------- | ------------------------------------------------------------ |
| 块级元素 | header,form,ul,ol, table, div, article, hr, aside, figure, canvas, video, audio, footer |
| 行内元素 | a,b,strong,span,img,label,button,input,select,textarea       |
|          |                                                              |



### inherit, unset, initial, normal

initial：`initial` 关键字用于设置 CSS 属性为它的默认值，可作用于任何 CSS 样式。

inherit：每一个 CSS 属性都有一个特性就是，这个属性必然是默认继承的 (`inherited: Yes`) 或者是默认不继承的 (`inherited: no`)其中之一，我们可以在 [MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Reference) 上通过这个索引查找，判断一个属性的是否继承特性。

unset：它是关键字 `initial` 和 `inherit` 的组合。什么意思呢？也就是当我们给一个 CSS 属性设置了 `unset` 的话：

1. 如果该属性是默认继承属性，该值等同于 `inherit`
2. 如果该属性是非继承属性，该值等同于 `initial`



##  2. white-space

| 值       | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| normal   | 默认。空白会被浏览器忽略。                                   |
| pre      | 空白会被浏览器保留。其行为方式类似 HTML 中的 <pre> 标签。    |
| nowrap   | 文本不会换行，文本会在在同一行上继续，直到遇到 <br> 标签为止。 |
| pre-wrap | 保留空白符序列，但是正常地进行换行。                         |
| pre-line | 合并空白符序列，但是保留换行符。                             |
| inherit  | 规定应该从父元素继承 white-space 属性的值。                  |



## 3. px, em, rem

1. px

   pixel 相对长度单位。像素px是相对于显示器屏幕分辨率而言的

   PX特点: 

    	1. IE无法调整那些使用px作为单位的字体大小；
    	2. 国外的大部分网站能够调整的原因在于其使用了em或rem作为字体单位；
    	3. Firefox能够调整px和em，rem，但是96%以上的中国网民使用IE浏览器(或内核)。

2. em

   em是相对长度单位。相对于当前对象内文本的字体尺寸。如当前对行内文本的字体尺寸未被人为设置，则相对于浏览器的默认字体尺寸

   em的特点:

    1. em的值不是固定的

    2. em会继承父级元素的字体大小

       > **注意：**任意浏览器的默认字体高都是16px。所有未经调整的浏览器都符合: 1em=16px。那么12px=0.75em,10px=0.625em。为了简化font-size的换算，需要在css中的body选择器中声明Font-size=62.5%，这就使em值变为 16px*62.5%=10px, 这样12px=1.2em, 10px=1em, 也就是说只需要将你的原来的px数值除以10，然后换上em作为单位就行了。
       >
       > 所以我们在写CSS的时候，需要注意两点：
       >
       > - \1. body选择器中声明Font-size=62.5%；
       > - \2. 将你的原来的px数值除以10，然后换上em作为单位；
       > - \3. 重新计算那些被放大的字体的em数值。避免字体大小的重复声明。
       >
       > 也就是避免1.2 * 1.2= 1.44的现象。比如说你在#content中声明了字体大小为1.2em，那么在声明p的字体大小时就只能是1em，而不是1.2em, 因为此em非彼em，它因继承#content的字体高而变为了1em=12px。

3. rem

   em是CSS3新增的一个相对单位（root em，根em），这个单位引起了广泛关注。这个单位与em有什么区别呢？区别在于使用rem为元素设定字体大小时，仍然是相对大小，但相对的只是HTML根元素

   

# ts





### 特殊符号的含义



|      |                                                              |                                                              |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ?:   | 属性或参数为可选项                                           |                                                              |
| !    | 类型推断排除null, undefined                                  |                                                              |
| ??   | 当左侧操作数为null 或 undefined 时, 其返回右侧的操作数, 否则返回左侧的操作数 |                                                              |
| ?:   | 可选属性                                                     | Person{name:String;age?:String}<br>age属性如果存在,就设定为String类型 |
|      |                                                              |                                                              |
|      |                                                              |                                                              |
|      |                                                              |                                                              |
|      |                                                              |                                                              |
|      |                                                              |                                                              |





# npm

## 1. --save-dev 与  --save

- --save ： dependencies 键下，发布后还需要依赖的模块，譬如像jQuery库或者Angular框架类似的，我们在开发完后后肯定还要依赖它们，否则就运行不了。

- --save-dev ： devDependencies 键下，开发时的依赖比如安装 js的压缩包gulp-uglify 因为我们在发布后用不到它，而只是在我们开发才用到它。 



```json
{
 "dependencies": {
    "vue": "^2.2.1"
  },
  "devDependencies": {
    "babel-core": "^6.0.0",
    "webpack": "^2.2.0",
  }
}

```





# bootstrap-table



## 1. function



| function                                  | describe    |      |
| ----------------------------------------- | ----------- | ---- |
| $("#table").bootstrapTable('refresh')     | 刷新        |      |
| $("#table").bootstrapTable("load", data); | 装载数据    |      |
| $('#table').bootstrapTable({})            | 初始化table |      |





# ASC II 码

| Bin(二进制) | Oct(八进制) | Dec(十进制) | Hex(十六进制) | 缩写/字符                   | 解释         |
| ----------- | ----------- | ----------- | ------------- | --------------------------- | ------------ |
| 0000 0000   | 00          | 0           | 0x00          | NUL(null)                   | 空字符       |
| 0000 0001   | 01          | 1           | 0x01          | SOH(start of headline)      | 标题开始     |
| 0000 0010   | 02          | 2           | 0x02          | STX (start of text)         | 正文开始     |
| 0000 0011   | 03          | 3           | 0x03          | ETX (end of text)           | 正文结束     |
| 0000 0100   | 04          | 4           | 0x04          | EOT (end of transmission)   | 传输结束     |
| 0000 0101   | 05          | 5           | 0x05          | ENQ (enquiry)               | 请求         |
| 0000 0110   | 06          | 6           | 0x06          | ACK (acknowledge)           | 收到通知     |
| 0000 0111   | 07          | 7           | 0x07          | BEL (bell)                  | 响铃         |
| 0000 1000   | 010         | 8           | 0x08          | BS (backspace)              | 退格         |
| 0000 1001   | 011         | 9           | 0x09          | HT (horizontal tab)         | 水平制表符   |
| 0000 1010   | 012         | 10          | 0x0A          | LF (NL line feed, new line) | 换行键       |
| 0000 1011   | 013         | 11          | 0x0B          | VT (vertical tab)           | 垂直制表符   |
| 0000 1100   | 014         | 12          | 0x0C          | FF (NP form feed, new page) | 换页键       |
| 0000 1101   | 015         | 13          | 0x0D          | CR (carriage return)        | 回车键       |
| 0000 1110   | 016         | 14          | 0x0E          | SO (shift out)              | 不用切换     |
| 0000 1111   | 017         | 15          | 0x0F          | SI (shift in)               | 启用切换     |
| 0001 0000   | 020         | 16          | 0x10          | DLE (data link escape)      | 数据链路转义 |
| 0001 0001   | 021         | 17          | 0x11          | DC1 (device control 1)      | 设备控制1    |
| 0001 0010   | 022         | 18          | 0x12          | DC2 (device control 2)      | 设备控制2    |
| 0001 0011   | 023         | 19          | 0x13          | DC3 (device control 3)      | 设备控制3    |
| 0001 0100   | 024         | 20          | 0x14          | DC4 (device control 4)      | 设备控制4    |
| 0001 0101   | 025         | 21          | 0x15          | NAK (negative acknowledge)  | 拒绝接收     |
| 0001 0110   | 026         | 22          | 0x16          | SYN (synchronous idle)      | 同步空闲     |
| 0001 0111   | 027         | 23          | 0x17          | ETB (end of trans. block)   | 结束传输块   |
| 0001 1000   | 030         | 24          | 0x18          | CAN (cancel)                | 取消         |
| 0001 1001   | 031         | 25          | 0x19          | EM (end of medium)          | 媒介结束     |
| 0001 1010   | 032         | 26          | 0x1A          | SUB (substitute)            | 代替         |
| 0001 1011   | 033         | 27          | 0x1B          | ESC (escape)                | 换码(溢出)   |
| 0001 1100   | 034         | 28          | 0x1C          | FS (file separator)         | 文件分隔符   |
| 0001 1101   | 035         | 29          | 0x1D          | GS (group separator)        | 分组符       |
| 0001 1110   | 036         | 30          | 0x1E          | RS (record separator)       | 记录分隔符   |
| 0001 1111   | 037         | 31          | 0x1F          | US (unit separator)         | 单元分隔符   |
| 0010 0000   | 040         | 32          | 0x20          | (space)                     | 空格         |
| 0010 0001   | 041         | 33          | 0x21          | !                           | 叹号         |
| 0010 0010   | 042         | 34          | 0x22          | "                           | 双引号       |
| 0010 0011   | 043         | 35          | 0x23          | #                           | 井号         |
| 0010 0100   | 044         | 36          | 0x24          | $                           | 美元符       |
| 0010 0101   | 045         | 37          | 0x25          | %                           | 百分号       |
| 0010 0110   | 046         | 38          | 0x26          | &                           | 和号         |
| 0010 0111   | 047         | 39          | 0x27          | '                           | 闭单引号     |
| 0010 1000   | 050         | 40          | 0x28          | (                           | 开括号       |
| 0010 1001   | 051         | 41          | 0x29          | )                           | 闭括号       |
| 0010 1010   | 052         | 42          | 0x2A          | *                           | 星号         |
| 0010 1011   | 053         | 43          | 0x2B          | +                           | 加号         |
| 0010 1100   | 054         | 44          | 0x2C          | ,                           | 逗号         |
| 0010 1101   | 055         | 45          | 0x2D          | -                           | 减号/破折号  |
| 0010 1110   | 056         | 46          | 0x2E          | .                           | 句号         |
| 0010 1111   | 057         | 47          | 0x2F          | /                           | 斜杠         |
| 0011 0000   | 060         | 48          | 0x30          | 0                           | 字符0        |
| 0011 0001   | 061         | 49          | 0x31          | 1                           | 字符1        |
| 0011 0010   | 062         | 50          | 0x32          | 2                           | 字符2        |
| 0011 0011   | 063         | 51          | 0x33          | 3                           | 字符3        |
| 0011 0100   | 064         | 52          | 0x34          | 4                           | 字符4        |
| 0011 0101   | 065         | 53          | 0x35          | 5                           | 字符5        |
| 0011 0110   | 066         | 54          | 0x36          | 6                           | 字符6        |
| 0011 0111   | 067         | 55          | 0x37          | 7                           | 字符7        |
| 0011 1000   | 070         | 56          | 0x38          | 8                           | 字符8        |
| 0011 1001   | 071         | 57          | 0x39          | 9                           | 字符9        |
| 0011 1010   | 072         | 58          | 0x3A          | :                           | 冒号         |
| 0011 1011   | 073         | 59          | 0x3B          | ;                           | 分号         |
| 0011 1100   | 074         | 60          | 0x3C          | <                           | 小于         |
| 0011 1101   | 075         | 61          | 0x3D          | =                           | 等号         |
| 0011 1110   | 076         | 62          | 0x3E          | >                           | 大于         |
| 0011 1111   | 077         | 63          | 0x3F          | ?                           | 问号         |
| 0100 0000   | 0100        | 64          | 0x40          | @                           | 电子邮件符号 |
| 0100 0001   | 0101        | 65          | 0x41          | A                           | 大写字母A    |
| 0100 0010   | 0102        | 66          | 0x42          | B                           | 大写字母B    |
| 0100 0011   | 0103        | 67          | 0x43          | C                           | 大写字母C    |
| 0100 0100   | 0104        | 68          | 0x44          | D                           | 大写字母D    |
| 0100 0101   | 0105        | 69          | 0x45          | E                           | 大写字母E    |
| 0100 0110   | 0106        | 70          | 0x46          | F                           | 大写字母F    |
| 0100 0111   | 0107        | 71          | 0x47          | G                           | 大写字母G    |
| 0100 1000   | 0110        | 72          | 0x48          | H                           | 大写字母H    |
| 0100 1001   | 0111        | 73          | 0x49          | I                           | 大写字母I    |
| 01001010    | 0112        | 74          | 0x4A          | J                           | 大写字母J    |
| 0100 1011   | 0113        | 75          | 0x4B          | K                           | 大写字母K    |
| 0100 1100   | 0114        | 76          | 0x4C          | L                           | 大写字母L    |
| 0100 1101   | 0115        | 77          | 0x4D          | M                           | 大写字母M    |
| 0100 1110   | 0116        | 78          | 0x4E          | N                           | 大写字母N    |
| 0100 1111   | 0117        | 79          | 0x4F          | O                           | 大写字母O    |
| 0101 0000   | 0120        | 80          | 0x50          | P                           | 大写字母P    |
| 0101 0001   | 0121        | 81          | 0x51          | Q                           | 大写字母Q    |
| 0101 0010   | 0122        | 82          | 0x52          | R                           | 大写字母R    |
| 0101 0011   | 0123        | 83          | 0x53          | S                           | 大写字母S    |
| 0101 0100   | 0124        | 84          | 0x54          | T                           | 大写字母T    |
| 0101 0101   | 0125        | 85          | 0x55          | U                           | 大写字母U    |
| 0101 0110   | 0126        | 86          | 0x56          | V                           | 大写字母V    |
| 0101 0111   | 0127        | 87          | 0x57          | W                           | 大写字母W    |
| 0101 1000   | 0130        | 88          | 0x58          | X                           | 大写字母X    |
| 0101 1001   | 0131        | 89          | 0x59          | Y                           | 大写字母Y    |
| 0101 1010   | 0132        | 90          | 0x5A          | Z                           | 大写字母Z    |
| 0101 1011   | 0133        | 91          | 0x5B          | [                           | 开方括号     |
| 0101 1100   | 0134        | 92          | 0x5C          | \                           | 反斜杠       |
| 0101 1101   | 0135        | 93          | 0x5D          | ]                           | 闭方括号     |
| 0101 1110   | 0136        | 94          | 0x5E          | ^                           | 脱字符       |
| 0101 1111   | 0137        | 95          | 0x5F          | _                           | 下划线       |
| 0110 0000   | 0140        | 96          | 0x60          | `                           | 开单引号     |
| 0110 0001   | 0141        | 97          | 0x61          | a                           | 小写字母a    |
| 0110 0010   | 0142        | 98          | 0x62          | b                           | 小写字母b    |
| 0110 0011   | 0143        | 99          | 0x63          | c                           | 小写字母c    |
| 0110 0100   | 0144        | 100         | 0x64          | d                           | 小写字母d    |
| 0110 0101   | 0145        | 101         | 0x65          | e                           | 小写字母e    |
| 0110 0110   | 0146        | 102         | 0x66          | f                           | 小写字母f    |
| 0110 0111   | 0147        | 103         | 0x67          | g                           | 小写字母g    |
| 0110 1000   | 0150        | 104         | 0x68          | h                           | 小写字母h    |
| 0110 1001   | 0151        | 105         | 0x69          | i                           | 小写字母i    |
| 0110 1010   | 0152        | 106         | 0x6A          | j                           | 小写字母j    |
| 0110 1011   | 0153        | 107         | 0x6B          | k                           | 小写字母k    |
| 0110 1100   | 0154        | 108         | 0x6C          | l                           | 小写字母l    |
| 0110 1101   | 0155        | 109         | 0x6D          | m                           | 小写字母m    |
| 0110 1110   | 0156        | 110         | 0x6E          | n                           | 小写字母n    |
| 0110 1111   | 0157        | 111         | 0x6F          | o                           | 小写字母o    |
| 0111 0000   | 0160        | 112         | 0x70          | p                           | 小写字母p    |
| 0111 0001   | 0161        | 113         | 0x71          | q                           | 小写字母q    |
| 0111 0010   | 0162        | 114         | 0x72          | r                           | 小写字母r    |
| 0111 0011   | 0163        | 115         | 0x73          | s                           | 小写字母s    |
| 0111 0100   | 0164        | 116         | 0x74          | t                           | 小写字母t    |
| 0111 0101   | 0165        | 117         | 0x75          | u                           | 小写字母u    |
| 0111 0110   | 0166        | 118         | 0x76          | v                           | 小写字母v    |
| 0111 0111   | 0167        | 119         | 0x77          | w                           | 小写字母w    |
| 0111 1000   | 0170        | 120         | 0x78          | x                           | 小写字母x    |
| 0111 1001   | 0171        | 121         | 0x79          | y                           | 小写字母y    |
| 0111 1010   | 0172        | 122         | 0x7A          | z                           | 小写字母z    |
| 0111 1011   | 0173        | 123         | 0x7B          | {                           | 开花括号     |
| 0111 1100   | 0174        | 124         | 0x7C          | \|                          | 垂线         |
| 0111 1101   | 0175        | 125         | 0x7D          | }                           | 闭花括号     |
| 0111 1110   | 0176        | 126         | 0x7E          | ~                           | 波浪号       |
| 0111 1111   | 0177        | 127         | 0x7F          | DEL (delete)                | 删除         |



# react



## 1. public 文件夹

如果你希望你的文件不被编译，比如jquery.min.js，或者压缩好的js插件等，你就可以把文件放在public文件夹中，这样还可以减少文件构建时间，可以减少构建文件的大小。换过来想，如果你把所有静态资源全部放在assets文件夹中，你会发现最后打包出来的文件很大，导致首页白屏时间过长，所以，你可以把一些不会改动的静态文件放到public中

只有前缀public可以访问文件夹中的文件`%PUBLIC_URL%`

如果需要使用src或中的文件node_modules，则必须将其复制到那里以明确指定将此文件作为构建的一部分的意图。
 当运行npm run build，Create React App将替换`%PUBLIC_URL%`为正确的绝对路径，因此即使使用客户端路由或将其托管在非根URL上，项目也会正常工作。
 在JavaScript代码中，可以process.env.PUBLIC_URL出于类似目的使用：

```jsx
render() {
    return <img src={process.env.PUBLIC_URL + '/img/logo.png'} />;
}
```



## 2. life 生命周期

```
componentDidMount
componentWillUnmount
```



# nginx 



## 1. location



| 模式                  | 含义                                                         |
| --------------------- | ------------------------------------------------------------ |
| `location = /uri`     | = 表示精确匹配                                               |
| `location ^~ /uri`    | ^ 进行前缀匹配，~ 表示区分大小写                             |
| `location ~ pattern`  | ~ 区分大小写的匹配                                           |
| `location ~* pattern` | ~* 不区分大小写的匹配                                        |
| `location /uri`       | 不带任何修饰符，也表示前缀匹配，但是在正则匹配之后           |
| `location /`          | 通用匹配，任何未匹配到其它 location 的请求都会匹配到，相当于 switch 中的 default |
| `location !~`         | 区分大小写不匹配                                             |
| `location !~*`        | 不区分大小写不匹配                                           |



## 2. 配置示例

```javascript

#user  nobody;
worker_processes  1;

#error_log  logs/error.log;
#error_log  logs/error.log  notice;
#error_log  logs/error.log  info;

#pid        logs/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       mime.types;
    default_type  application/octet-stream;
    
    #log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
    #                  '$status $body_bytes_sent "$http_referer" '
    #                  '"$http_user_agent" "$http_x_forwarded_for"';

    #access_log  logs/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    #keepalive_timeout  0;
    keepalive_timeout  65;

    #gzip  on;
	gzip on;
	gzip_comp_level 9;
	gzip_min_length 10k;
	gzip_proxied any;
	gzip_vary on;
	gzip_types
    	application/atom+xml
    	application/javascript
    	application/json
    	application/ld+json
    	application/manifest+json
    	application/rss+xml
    	application/vnd.geo+json
    	application/vnd.ms-fontobject
    	application/x-font-ttf
    	application/x-web-app-manifest+json
    	application/xhtml+xml
    	application/xml
    	font/opentype
    	image/bmp
    	image/svg+xml
    	image/x-icon
    	text/cache-manifest
    	text/css
    	text/plain
    	text/vcard
    	text/vnd.rim.location.xloc
    	text/vtt
    	text/x-component
    	text/x-cross-domain-policy;	


	client_max_body_size 1000M;
	server_tokens off;
	
    server {
        listen       80;
        server_name  localhost;

        #charset koi8-r;

        #access_log  logs/host.access.log  main;

        location / {
            root   html;
            index  index.html index.htm;
        }

        #error_page  404              /404.html;

        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }

        # proxy the PHP scripts to Apache listening on 127.0.0.1:80
        #
        #location ~ \.php$ {
        #    proxy_pass   http://127.0.0.1;
        #}

        # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
        #
        #location ~ \.php$ {
        #    root           html;
        #    fastcgi_pass   127.0.0.1:9000;
        #    fastcgi_index  index.php;
        #    fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
        #    include        fastcgi_params;
        #}

        # deny access to .htaccess files, if Apache's document root
        # concurs with nginx's one
        #
        #location ~ /\.ht {
        #    deny  all;
        #}
    }


    # another virtual host using mix of IP-, name-, and port-based configuration
    #
    #server {
    #    listen       8000;
    #    listen       somename:8080;
    #    server_name  somename  alias  another.alias;

    #    location / {
    #        root   html;
    #        index  index.html index.htm;
    #    }
    #}


    # HTTPS server
    #
    #server {
    #    listen       443 ssl;
    #    server_name  localhost;

    #    ssl_certificate      cert.pem;
    #    ssl_certificate_key  cert.key;

    #    ssl_session_cache    shared:SSL:1m;
    #    ssl_session_timeout  5m;

    #    ssl_ciphers  HIGH:!aNULL:!MD5;
    #    ssl_prefer_server_ciphers  on;

    #    location / {
    #        root   html;
    #        index  index.html index.htm;
    #    }
    #}

    server {
        listen       8090 ssl;
        server_name  xianmoer-frontend;
		
		ssl_certificate D:/ProgramData/nginx/nginx-1.24.0/conf/xianmoer.crt;
        ssl_certificate_key D:/ProgramData/nginx/nginx-1.24.0/conf/xianmoer.key;
		ssl_session_timeout 5m;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2; 
        ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:HIGH:!aNULL:!MD5:!RC4:!DHE; 
        ssl_prefer_server_ciphers on;
	
		server_tokens off;
		proxy_hide_header Server;
		add_header Content-Security-Policy "default-src 'self';
                                 object-src 'self' ;
                                 style-src 'self' 'unsafe-inline';
                                 frame-src 'self' ;
                                 base-uri 'self'; 
                                 form-action 'self';
                                 script-src 'self'  'unsafe-eval' 'sha256-s9RoBFqqRTKEz03aMkaEGLy7X3nJuyOZ8mzkjwCekYA=' ;
								 connect-src 'self' https://api.iconify.design https://api.unisvg.com https://api.simplesvg.com;
                                 img-src 'self' data:";
		add_header X-Content-Type-Options "nosniff";
		add_header Set-Cookie "SameSite=Lax; Secure; HttpOnly; Path=/";
		add_header Referrer-Policy same-origin;
        
		root D:\xianmoer-assessment\front-end\20231121\dist;

        location /basic-api {
            proxy_pass http://127.0.0.1:9950/api;			
        }

        location /file/xianmoer {
            proxy_set_header Host 127.0.0.1:9000;
            proxy_pass http://127.0.0.1:9000/xianmoer;
        }

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
		
		location ~ /\. {
			deny all;
		}
		
		location / {
            try_files $uri $uri/ =404;
        }
    }
}

```





# eslint

## 1. eslint 为何推荐单引号,

ESLint 是一个可配置的 JavaScript 代码检查工具，它可以帮助开发者保持代码一致性和质量。关于引号风格，ESLint 的默认推荐配置通常会推荐使用单引号。以下是几个原因和背景解释：

### 1. 一致性和可读性

使用单引号或双引号是代码风格的一部分。保持一致的引号风格可以提高代码的可读性和可维护性。

### 2. 减少转义字符的使用

在 JavaScript 中，当字符串中包含 HTML 属性或其他带双引号的字符串时，使用单引号可以减少转义字符的使用。例如：

```
javascript
复制代码
// 使用单引号，不需要转义双引号
const htmlString = '<div class="container">Hello</div>';

// 使用双引号，需要转义双引号
const htmlString = "<div class=\"container\">Hello</div>";
```

### 3. 社区标准

许多 JavaScript 社区和框架（如 AirBnB JavaScript Style Guide、StandardJS）都推荐使用单引号。采用社区标准可以让团队中的每个开发者更容易理解和遵循代码风格。

### 4. JSON 和 JavaScript 区分

JSON 格式要求使用双引号，而在 JavaScript 代码中使用单引号可以更容易地区分 JSON 数据和 JavaScript 代码。例如：

```
javascript
复制代码
// JSON
const jsonString = '{"name": "John", "age": 30}';

// JavaScript
const jsString = '{"name": "John", "age": 30}';
const message = 'This is a JavaScript string';
```

### 配置 ESLint 使用单引号

在 ESLint 配置文件中，你可以通过 `quotes` 规则来指定引号风格。以下是一个示例配置：

```
json
复制代码
{
  "rules": {
    "quotes": ["error", "single"]
  }
}
```

这条规则表示：所有字符串应该使用单引号，如果不符合，将会产生一个错误。

### 例外情况

尽管 ESLint 推荐使用单引号，有时候仍然需要使用双引号。例如，当字符串中包含单引号时，使用双引号可以避免转义：

```
javascript
复制代码
const message = "It's a beautiful day"; // 使用双引号避免转义
```

在这种情况下，你可以根据实际需要覆盖默认规则。

### 总结

ESLint 推荐使用单引号的主要原因是为了代码的一致性、减少转义字符的使用、遵循社区标准以及区分 JSON 和 JavaScript 代码。这些推荐规则可以帮助开发团队保持统一的代码风格，提高代码的可读性和维护性。







