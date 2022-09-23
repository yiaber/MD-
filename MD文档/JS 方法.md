#### JS数组对象根据某个对象中的值删除该对象

##### filter() 函数方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。

```js
data=[
    { key: '999', name: 'zhangsan'},
    { key: '111', name: 'lisi'},
    { key: '222', name: 'wanger'},
    { key: '333', name: 'apple'},
    { key: '444', name: 'orange'},
]
this.data = this.data.filter(item => item.key !== "999")
```

#### **克隆对象**

```javascript
const _obj = { a: 0, b: 1, c: 2 };
const obj = { ..._obj };
const obj = JSON.parse(JSON.stringify(_obj));
// obj => { a: 0, b: 1, c: 2 }
```

#### **合并对象**

```js
const obj1 = { a: 0, b: 1, c: 2 };
const obj2 = { c: 3, d: 4, e: 5 };
const obj = { ...obj1, ...obj2 };
// obj => { a: 0, b: 1, c: 3, d: 4, e: 5 }
```



##### element input 只能输入数字

```vue
 <el-input v-model='width' oninput="value=value.replace(/[^\d]/g,'')" maxLength='3' />
```

##### element input 只能输入数字和字母

```vue
<el-input onkeyup="this.value=this.value.replace(/[^\w_]/g,'');"></el-input>
```



#### 过滤对象中的值为空

```js
let obj = Object.values(this.forms).filter((item) => item == "");

 if (!obj.length) {
	// 不为空 操作
 }else{
     // 为空 操作
 }

```

#### 数组at方法（ES2022新特性）

```javascript
let arr=[1,2,3];
arr.at(-1) //3
```

##### 常用正则

```
1.只能为数字 且不能为空    /^\d+$/
```

```
2.只能为数字和小数点 /^\d+(\.\d+)?$/
```

```
3.金额 /(?:^[1-9]([0-9]+)?(?:\.[0-9]{1,2})?$)|(?:^(?:0)$)|(?:^[0-9]\.[0-9](?:[0-9])?$)/
```

