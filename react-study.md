# 1. render

初始化渲染, state 改变后(状态更新后)



# 2. 数组操作

在 React 中，处理数组是非常常见的操作，尤其是在状态管理和渲染列表时。以下是 React 开发中常用的数组操作方法：

### 1. 渲染数组（列表）

使用 `map()` 方法遍历数组并渲染元素，需为每个元素添加唯一 `key`：

jsx

```jsx
const items = [1, 2, 3];
return (
  <ul>
    {items.map((item) => (
      <li key={item}>{item}</li>
    ))}
  </ul>
);
```



### 2. 添加元素

为保持状态不可变性，使用扩展运算符 `...` 创建新数组：

jsx

```jsx
// 向数组末尾添加
const [list, setList] = useState([1, 2, 3]);
setList([...list, 4]); // [1, 2, 3, 4]

// 向数组开头添加
setList([0, ...list]); // [0, 1, 2, 3]
```



### 3. 删除元素

使用 `filter()` 方法过滤掉不需要的元素：

jsx

```jsx
// 删除值为2的元素
setList(list.filter(item => item !== 2)); // [1, 3]

// 根据索引删除
const indexToRemove = 1;
setList(list.filter((_, index) => index !== indexToRemove)); // [1, 3]
```



### 4. 更新元素

使用 `map()` 方法更新特定元素：

jsx

```jsx
// 将值为2的元素更新为20
setList(list.map(item => item === 2 ? 20 : item)); // [1, 20, 3]

// 根据索引更新
const indexToUpdate = 1;
setList(list.map((item, index) => index === indexToUpdate ? 20 : item));
```



### 5. 查找元素

使用 `find()` 或 `findIndex()` 查找元素：

jsx

```jsx
// 查找值为2的元素
const found = list.find(item => item === 2);

// 查找值为2的元素索引
const foundIndex = list.findIndex(item => item === 2);
```



### 6. 数组排序

使用 `sort()` 方法（注意：会修改原数组，需先复制）：

jsx

```jsx
// 正序排序
setList([...list].sort((a, b) => a - b));

// 倒序排序
setList([...list].sort((a, b) => b - a));
```



### 7. 数组拼接

使用 `concat()` 或扩展运算符合并数组：

jsx

```jsx
const arr1 = [1, 2];
const arr2 = [3, 4];

// 方法1: concat
const combined = arr1.concat(arr2); // [1, 2, 3, 4]

// 方法2: 扩展运算符
const combined = [...arr1, ...arr2]; // [1, 2, 3, 4]
```



### 8. 检查元素是否存在

使用 `includes()` 或 `some()`：

jsx

```jsx
// 检查是否包含2
const hasTwo = list.includes(2);

// 检查是否有大于3的元素
const hasGreaterThanThree = list.some(item => item > 3);
```



### 9. 数组归约

使用 `reduce()` 进行累加等操作：

```jsx
// 计算数组总和
const sum = list.reduce((total, item) => total + item, 0);
```

### 注意事项：

- 始终保持状态不可变，避免直接修改原数组（如 `push()`、`pop()`、`splice()` 等方法会修改原数组）
- 处理对象数组时，操作方式类似，只是判断条件需要针对对象属性
- 对于大型数组，考虑使用 `React.memo` 和虚拟列表优化性能

这些操作在处理 React 状态中的数组时非常实用，尤其是结合 `useState` 或 `useReducer` 进行状态管理时。