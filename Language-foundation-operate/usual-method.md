# 转换类

## 对象转数组

#### object.entires(obj) 

`参数：obj ,可以返回其可枚举属性的键值对的对象。`

`返回值：Array ,给定对象自身可枚举属性的键值对数组。`

```Js
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}
```

# 