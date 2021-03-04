# JS 与 Java 哈希表区别

|         哈希表         |           Java           |                JS                 |
| :--------------------: | :----------------------: | :-------------------------------: |
|                        |                          |                                   |
|   **检测是否存在：**   |                          |                                   |
|  检测是否存在某个 key  |   map.containsKey(key)   |           map.has(key)            |
| 检测是否存在某个 value | map.containsValue(value) |              值做key              |
|                        |                          |                                   |
|      **基础操作**      |                          |                                   |
|       删除键值对       |     map.remove(key)      |          map.delete(key)          |
|        访问元素        |       map.get(key)       |        map[]，map.get(key)        |
|       添加键值对       |    map.put(key,value)    |        map.set(key, value)        |
|      修改某键值对      |  map.replace(key,value)  |        map.set(key, value)        |
|    计算哈希表的大小    |        map.size()        |             map.size              |
|       清除哈希表       |       map.clear()        |            map.clear()            |
|     返回可迭代对象     |                          |           map.entries()           |
|                        |                          |                                   |
|        **其他**        |                          |                                   |
|      检测是否为空      |      map.isEmpty()       |                                   |
|   将对象转换为哈希表   |                          |   new Map(Object.entries(obj))    |
|                        |                          |                                   |
|        **遍历**        |                          |                                   |
|        遍历键名        |       map.keySet()       | map.keys() (Iterator对象),key..in |
|        遍历键值        |       map.values()       |    map.values() (Iterator对象)    |
|      遍历 map 表       |         for-Each         |      map.forEach(callback())      |
|                        |                          |                                   |
|                        |                          |                                   |



## Java HashMap

**`基本操作:`**

```java
1.创建 HashMap 对象
  import java.util.HashMap; // 引入 HashMap 类
  HashMap<Integer, String> Sites = new HashMap<Integer, String>();
2.添加键值对
  Sites.put(1, "Google");
3.访问元素
  Sites.get(3);	// 参数为 index ，返回此位置的值
4.删除键值对
  Sites.remove(4); // 参数为 index ，删除此键对应的键值对
5.替换某键值对
  Site.replace(2, "newValue"); // 将 key为 2 的值 替换为 newValue
6.检测键 为 key 的键值对是否存在
  Site.containsKey(1);
7.检测值 为 value 的键值对是否存在
  Site.containsValue("Runoob");
5.清除所有键值对 
  Sites.clear();
6.计算大小
  Sites.size();
```

**`迭代 HashMap`**

可以使用 for-each 来迭代 HashMap 中的元素。如果你只想获取 key，可以使用 keySet() 方法，然后可以通过 get(key) 获取对应的 value，如果你只想获取 value，可以使用 values() 方法。

```java
HashMap<Integer, String> Sites = new HashMap<Integer, String>();

Sites.put(1,"we")
Sites.put(2,"ls")
  
// 迭代键
for (Integer key : map.keySet()) {
  System.out.println("Key = " + key + "Value = " + map.get(key));
}

// 迭代值
for (String value : map.values()) {
  System.out.println("Value = " + value);
}
```

**其他方法**

与 ArrayLists 对象类似

## JS HashMap

**`基础操作:`**

```JS
1.创建 HashMap 对象
  let map = new Map();
2.添加键值对
  map.set(1, "Google");
3.访问元素
  map.get(3);	// 参数为 index ，返回此位置的值
	map[index];
4.删除键值对
  Sites.delete(4); // 参数为 index ，删除此键对应的键值对
5.替换某键值对
  map.set(2, "newValue"); // 将 key为 2 的值 替换为 newValue
6.检测键 为 key 的键值对是否存在
  map.has(key);
7.检测值 为 value 的键值对是否存在
  值做哈希表键名，用 has 方法
5.清除所有键值对 
  map.clear();
6.计算大小
  map.size;
```

**`哈希表实际存储形式:`**

即为一个二维数组，以键名 键值的形式存储： `	[[key,value],[key,value],[key,value]]`

在 JS中可以 针对 

**`创建哈希表：`**

```JS
// 常规方法
let map = new Map();
map.set('foo',3)
map.set('bar',{})
map.set('foo',undefined)

// 简洁写法，写在语句中
new Map([['foo', 3], ['bar', {}], ['baz', undefined]])
```

**`forEach():`**

```JS
myMap.forEach(callback([value][,key][,map])[, thisArg]) 	// return undefined

let map = new Map();
map.set('foo',3)
map.set('bar',{})
map.set('foo',undefined)

map.forEach(function(value,key,map)) {
      console.log(`map.get('${key}') = ${value}`)
}
```

**`entires():`**

```JS 
// entries() 方法返回一个新的包含 [key, value] 对的 Iterator 对象，返回的迭代器的迭代顺序与 Map 对象的插入顺序相同。
myMap.entries()

let itmap = new Map([['foo', 3], ['bar', {}], ['baz', undefined]]).entires();

console.log(itmap.next().value);
// expected output: ["foo", "3"]

console.log(itmap.next().value);
// expected output: ["bar", "{}"]
```

注意输出以数组形式，数组元素都是字符串

### `以数组创建哈希表`

```JS
// 以数组元素值作为键，索引作为值
const NewValueMap = (nums) => {
    const valMap = new Map ()
    nums.forEach((item, index) => {
        valMap.set(item,index)
    })
    return valMap
}
```

数组 forEach 与 HashMap forEach 不同

```JS
array.forEach(function(currentValue, index, arr), thisValue)

myMap.forEach(callback([value][,key][,map])[, thisArg]) 	// return undefined
```

# 对象与哈希表的区别

对象与Map不同，对象可以像数组一样下标访问，Map不行

[关于对象与HashMap 的区别](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map)

![](https://cdn.jsdelivr.net/gh/yummy-zc/image-warehouse/images/algorithmimage-20210211005628608.png)

## 