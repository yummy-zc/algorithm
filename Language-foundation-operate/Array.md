# 基础操作

### 区别一览表

|                数组                 |             Java（ArrayList）              |                 JS                  |
| :---------------------------------: | :----------------------------------------: | :---------------------------------: |
|          修改指定位置的值           |             set(index，value)              |         arr[index] = value          |
|       在指定位置添加值(插入)        |              add(index,value)              |           splice(),fill()           |
|            访问指定元素             |                 get(index)                 |             arr[index]              |
|              删除元素               |               remove(index)                |              splice()               |
|              计算大小               |                   size()                   |             arr.length              |
|          特定位置添加元素           |                     无                     |          push()、unshift()          |
|          特定位置删除元素           |                     无                     |           pop()、shift()            |
|         检测是否存在这个数          | contains(),indexOf(),Arrays.binarySearch() | indexOf(),includes(),some(),find()  |
|              复制数组               |    Arrays.copyOf(),Arrays.copyOfRange()    |               slice()               |
|                排序                 |              Arrays.sort(arr)              |          reverse(),sort()           |
|           数组之间的组合            |             System.arraycopy()             |          concat(),splice()          |
|          数组转化为字符串           |                                            |              join("")               |
|                                     |                                            |                                     |
|              遍历数组               |                for-Each(:)                 |   forEach(),map(),for...of('of')    |
|           判断是否为数组            |                 isArray()                  |              isArray()              |
|          检测各个数组元素           |                                            |           every(),some()            |
|              过滤元素               |                                            |              filter()               |
|          查询元素值的索引           |                                            | indexOf(),lastIndexOf(),findIndex() |
|        将其他类型转化为数组         |                                            | from(arrayLike[, mapFn[, thisArg])  |
|      返回 Array Iterator 对象       |                                            |      keys(),entries(),values()      |
|                正常                 |                     .                      |                                     |
| ArrayList String 类型转换为str数组  |     arrList.toArray(new String[size])      |                                     |
| ArrayList Integer 类型转换为int数组 |              for循环遍历赋值               |                                     |
|       数组转换为集合ArrayList       |             Arrays.asList(arr)             |                                     |
|                                     |                                            |                                     |
|                                     |                                            |                                     |
|                                     |                                            |                                     |

将数组的值累加 ： arr.reduce((a,b) => a + b)

## Java Array

#### **创建数组**

```JS
1.声明
  int[] arr
  String[][] str = new String[3][4]

2.初始化
  int[] arr = new int[] {1,2,3,4,5}
  int[] arr = {1,2,3,4}
  int[][]	arr = new int[][] {{1},{2,3},{4},{4,5,6}}

  // 简洁写法，写在return 或者语句中
  new int[] { i, map.get(complement) }

3.多维数组
  int intArray[][] = new int[4][]; //先初始化高维数组为4
  // 逐一初始化低维数组
  intArray[0] = new int[2];
  intArray[1] = new int[1];
  intArray[2] = new int[3];
  intArray[3] = new int[3];

4.创建 ArrayList 对象
  // 一维 数组
  ArrayList<Integer> arr = new ArrayList()
  
  // 二维 数组
  List<List<Integer>> arr2 = new ArrayList()
 
  // 动态创建
  new ArrayList<Integer>(Arrays.asList(nums[k], nums[i], nums[j]))
```

#### 数组的排序

```JS
1.Arrays.sort()
  int[] array = new int[]{3,7,8,2,1,9};
  Arrays.sort(array);    //全排序
  Arrays.sort(array,2,5);    //2到5排序

2.Arrays.sort(arr, Collections.reverseOrder());  // 倒序排序
	Integer[] ew = { 9, 8, 7, 2, 3, 4, 1, 0, 6, 5 };  // 使用这种方法  数组必须是包装类型
	Arrays.sort(ew, Collections.reverseOrder());  // 倒序排序
```

#### 遍历

```JAVA
1.for 循环		// 确定执行次数时使用
  
2.for-Each		// 遍历数组和集合
 
  for(元素类型t 元素变量x : 遍历对象obj) {
        引用了x的java语句
  }

  // 遍历一维数组
  int[] arr = {1,2,4,5,6}
  for (int element : arr) {
    sout(element)
  }

  // 遍历二维数组
  int[][] arr = {{1,2},{2,2},{4,5,6,7}};
  for(int[] row : arr) {
    for(int element : row) {
      sout(element)
    }
  }

3.Arrays.toString(arr)
  // 将一维数组转化为字符串形式输出
  int[] arr = {1,2,4,5,6}		// [1,2,3,4,5]
```

#### 查找某个值

```JS
1.Arrays.binarySearch(arr,value)		// index 返回索引 		！数组必须是已经按顺序排序好的
  int[] arr = {1,3,4,5,6}
	int index = Arrays.binarySearch(arr,3)  // 1
```

#### 数组的复制

```Java
1.Arrays.copyOf() 和 Arrays.copyOfRange
  int[] array = new int[]{3,7,8,2,1,9};
  array2 = Arrays.copyOf(array,3); //新数组的长度为3
  array3 = Arrays.copyOfRange(array,3,5); //复制第三到五个元素

2. System.arrayCopy(Object src,int srcPos,Object dest,int destPos,int length)
    参数：
    src - 源数组。
    srcPos - 源数组中的起始位置。
    dest - 目标数组。
    destPos - 目的地数据中的起始位置。
    length - 要复制的源数组元素的数量。
```

#### 转换类

**`将数组转换为集合`**

```java
1.Array.asList()
  List<List<Integer>> res = new ArrayList<>();
  res.add(new ArrayList<Integer>(Arrays.asList(nums[k], nums[i], nums[j])));
```

#### 

## JS基础操作实例

#### **创建数组**

```JS
1.创建一个规定大小的数组
  let arr = new Array(30) 	// 值都为undefined

2.常规字面量建法
  let arr = [1,2,3,55]

3.Array.of()   // ES6 方法	数组创建，将参数中所有值作为元素形成数组，如果参数为空，则返回一个空数组。
  Array.of(1, 2, 3, 4); 		// [1, 2, 3, 4] 

4.Array(arr.length).fill(0)

5.创建一个二维数组
	Array.from({lenth:nums.length}, x => Array.from({length:nums.length}), y => 0))
  Array.from({lenth:nums.length}, x => Array(arr.length).fill(0))
  
6.Array.from({length: 5}, (value, index) => i); 	// [0, 1, 2, 3, 4]
```

JS 可以 通过 arr.length 来动态设定 数组长度， 多余的用 undefined 填充

```JS
arr.length = 5
```

#### **遍历数组**

```JS
1.forEach(callback(currentValue [, index [, array]])[, thisArg])	 // ES5		
	// forEach() 方法对数组的每个元素执行一次给定的函数。不会对原数组进行改变，方法返回的是undefined
  // 参数为 一个回调函数和 一个当执行回调函数 callback 时，用作 this 的值（）可省略。
  // 回调函数为必须，参数current为遍历的当前元素的值，index为当前数组元素的索引，array为遍历的这个数组对象本身

  // forEach 方法主要为遍历数组元素，读取数组元素的值做读取操作，方法返回的是undefined，原理上不会对原数组的值进行改变，所以重点在与遍历读取数组元素
  let NumberArr = [1,2,3,4,5]
  let sum = 0

  NumberArr.forEach(element => {
        sum += element
  }

2.map(callback(currentValue [, index [, array]])[, thisArg])   // ES5		
	//  参数与 forEach() 方法是一样的，与此方法的重要区别在于会返回新的数组，不会修改原数组，
  // 因为map生成一个新数组，当你不打算使用返回的新数组却使用map是违背设计初衷的，请用forEach或者for-of替代


3.for....of 语句  // ES6
  // for...of语句在可迭代对象（包括 Array，Map，Set，String，TypedArray，arguments 对象等等）上创建一个迭代循环
  // 与 forEach方法功能类型，主要也是做读取操作
  const array1 = ['a', 'b', 'c'];
	const array2 = [[1,2], [2,3], [3,3]];

  for (const element of array1) {
    console.log(element);
  }

	for (const [a, b] of array1) {
    console.log(a);
    console.log(b);
  }
```

**拓展：关于对象的遍历**

```JS
1.object.keys(obj) // 遍历键名

var obj = {'a':'123','b':'345'}
  console.log(Object.keys(obj))
// ["a", "b"]

2.for...in 遍历对象，它遍历的是属性名
//会遍历实例的属性，还会遍历整个原型链，这可能不是你所期望的结果，从性能角度上看Object.keys会更优。

 var obj = {'a':'123','b':'345'}
 for (let key in obj){
   console.log(key ,obj[key])
 }
// a 123
// b 345

关于 for...in 遍历：
1、for in遍历对象时，会遍历实例的属性+还遍历原型中可枚举的属性
2、for in不适合遍历数组，遍历数组遍历的是下标，下标类型是 字符串
3，for in遍历会以任意顺序遍历对象的属性名
```

#### **检测数组元素的值**

```Js 
1.every(callback(element[, index[, array]])[, thisArg])  // every() 方法测试一个数组内的所有元素是否都能通过某个指定函数的测试。它返回一个布尔值。
// 参数形式与forEach方法相似，都是回调函数和一个thisArg

// 检测数组中的所有元素是否都大于 10
function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough);   // false
[12, 54, 18, 130, 44].every(isBigEnough); // true


2.some(callback(element[, index[, array]])[, thisArg])		// some() 方法测试数组中是不是至少有1个元素通过了被提供的函数测试。它返回的是一个Boolean类型的值。
// 参数形式与forEach方法相似，都是回调函数和一个thisArg

function isBiggerThan10(element, index, array) {
  return element > 10;
}

[2, 5, 8, 1, 4].some(isBiggerThan10);  // false
[12, 5, 8, 1, 4].some(isBiggerThan10); // true
```

#### **判断数组是否存在某个值**

（查询首个满足某个条件的元素值）

```JS
1.includes(valueToFind[, fromIndex)		// 参数为要查询的元素 与 起始查询的位置，返回布尔值
[1, 2, 3].includes(2)					// true


2.some()		// some() 方法测试数组中是不是至少有1个元素通过了被提供的函数测试。它返回的是一个Boolean类型的值。

var fruits = ['apple', 'banana', 'mango', 'guava'];

function checkAvailability(arr, val) {
  return arr.some(arrVal => val === arrVal);
}

checkAvailability(fruits, 'kela');   // false
checkAvailability(fruits, 'banana'); // true

3.find(callback[, thisArg])		//  方法返回数组中满足提供的测试函数的第一个元素的值。否则返回 undefined。与forEach方法参数形式相同

// 用对象的属性查找数组里的对象
var inventory = [
    {name: 'apples', quantity: 2},
    {name: 'bananas', quantity: 0},
    {name: 'cherries', quantity: 5}
];

function findCherries(fruit) {
    return fruit.name === 'cherries';
}

console.log(inventory.find(findCherries)); // { name: 'cherries', quantity: 5 }
```

**根据 元素的值 （满足条件）查询到元素所在的索引**

```JS
1.indexOf(value，startIndex)			//	返回该元素第一次出现的索引，可以设定起始查询位 ，返回索引，未查找到返回 -1
arr.indexOf(2) 	 				// 从头开始查找，第一个出现 值为 2 的元素的索引

2.lastIndexOf(value，startIndex)			// 	返回该元素最后一次出现的索引，可以设定起始查询位，逆向查询
arr.indexOf(5)					// 从末位（起始位）开始逆向查找，第一个出现 值为 5 的元素的索引

3.findIndex(callback[, thisArg])			// 返回数组中满足提供的测试函数的第一个元素的索引。若没有找到对应元素则返回-1。参数形式与 forEach 一样，
// 与 indexOf不同在与可以先对要查询的数据进行处理后再查询，indexOf适用已知知道要查询的值，而此方法适合查询某个首先满足条件的元素 的 索引

// 查找首个素数的索引
function isPrime(element, index, array) {
  var start = 2;
  while (start <= Math.sqrt(element)) {
    if (element % start++ < 1) {
      return false;
    }
  }
  return element > 1;
}

console.log([4, 6, 8, 12].findIndex(isPrime)); // -1, not found
console.log([4, 6, 7, 12].findIndex(isPrime)); // 2
```

#### **数组值的删除、增加**

```JS
pop()
let lastValue = arr.pop()  // 删除的数组最后一位值，并且返回这个值

shift()
let fitstValue = arr.shift() 	// 删除数组的第一位值，并且返回这个值

push()
let addValue = arr.push(6)	// 	添加值到数组的最后一位，返回数组长度

unshfit()
let addFirst = arr.unshift(12) // 添加值到数组第一位，返回数组长度
```

#### **在 index 位置插入元素**

```JS 
fill(value[, start[, end]])			//	用一个固定值填充一个数组中从起始索引到终止索引内的全部元素。不包括终止索引。
// 只能用来填充一个固定值
// value 为要填充的值，start为起始要填充的位置（包括此位置），默认值为0。end为结束位置（不包含此位置），默认值为 arr.length

let arr = [1,3,5,7]
arr.fill(6)										//		[6,6,6,6],默认从起始到结尾都替换
arr.fill(6,1,2)								//		[1,6,5,7], 替换一个
```

#### **综合操作 splice**

可以实现 数组元素的删除 和 数组元素的添加，默认是以删除为目的

```JS
splice(start[, deleteCount[, item1[, item2[, ...]]]])
// 三个参数：数组的起始位，删除的数组元素的个数，要添加的元素 ，第一个为必须，其他两个可省略
// 返回值：有删除的元素，返回删除的值的组成的数组，没删除的元素，返回空数组

实现数组元素的添加 arr.splice(添加的起始位，0，要添加的数组元素)
arr.splice(0,0,1,2,3,4)			// 添加（插入）元素 1 2 3 4 到数组的第一位

实现数组元素的删除
arr.splice(2,5) 						// 从索引为 2 的起始位开始，删除后面的五个元素 ，返回删除元素组成的元素

实现数组元素的删除与添加 
arr.splice(2,5,9,9,9)			// 先删除五个元素后，添加9，9，9
```

#### **数组的排序**

```JS
1.reverse()			// 倒置数组，对原数组产生影响，返回一个颠倒后的数组
arr.reverse()


TODO？？？？？
2.sort()			//  按照想要的方式进行排序，改变原数组，由于它取决于具体实现，因此无法保证排序的时间和空间复杂性。
默认没有参数时 arr.sort()	// 按照ASCII码的大小进行排序
接受一个回调函数作为参数，如果返回值为正数的话，按照由小到大的排序，返回为负值，按照由大到小的排序
a.sort(function(a,b)=>{return a - b})			// 按照由小到大的排序
a.sort(function(a,b)=>{return b - a})			// 按照由大到小的排序 
```

**`二维数组排序`**

```JS
entries()			// 返回一个新的Array Iterator对象，该对象包含数组中每个索引的键/值对
// 将一个一维数组，转化为可迭代的二维数组，将数组的索引作为键名，数组元素作为键值，而每一个 iterator1.next().value 就是二维数组中的元素（即一维数组），iterator1.next().value[0] 为此数组元素的索引，iterator1.next().value[1] 为此数组元素的值，iterator1.next().done 为此数组元素是否遍历到底的标志，未到底 false ，到底为 true

const array1 = ['a', 'b', 'c'];
const iterator1 = array1.entries();

console.log(iterator1.next().value);
// expected output: Array [0, "a"]					// 打印的同时也执行了next()
console.log(iterator1.next().value);
// expected output: Array [1, "b"]
console.log(iterator1.next().value[1]);
// expected output: "c"
console.log(iterator1.next().done);						// false
console.log(iterator1.next().done);						// true

// 二维数组
let arr = [[1,2],[33,56,11],[13,34,9]];
let arrIter = arr.entries()

console.log(arrItem.next().value)					// [[0],[1,2]]
console.log(arrItem.next().value)					// [[1],[33,56,11]]
console.log(arrItem.next().value[1])			// [13,34,9]

// 二维数组的排序
let arr = [[1,34],[456,2,3,44,234],[4567,1,4,5,6],[34,78,23,1]];
SortArr(arr);

function entriesSortArr(arr) {
  let goNext = true;
  let entries = arr.entries();
  while (goNext) {
    let item = entries.next();
    if (item.done !== true) {
      item.value[1].sort((a,b) => a - b);
      goNext = true;
    } else {
      goNext = false;
    }
  }
  return arr
}

sort()
function SortArr2(arr) {
  for (let i = 0; i < arr.length; i++) {
    arr[i].sort((a - b) => a - b)
  }
}
```

#### **其他**

**`数组的元素截取`**

```JS
1.slice()					// 分割 指定起始位 与 终止位的数组元素 ，返回一个新的数组
arr.slice(stratIndex,endIndex)
```

**`数组之间的组合`**

```JS
1.concat()				// 	组合数组，将两个数组组合为一个数组，参数为需要组合的数组，返回一个新数组
arr1.concat(arr2)
```

**`判断一个数据是否为数组`**

```JS
1.isArray()
Array.isArray(arr)					// 返回布尔值
```

**`数组的复制`**

```JS
1.slice(start.end) 			// 复制数组，返回新数组，不改变原数组
arr.slice(1,3)				// 从索引值为 1 的元素开始复制（包含1对应的元素），到索引值为 3 的元素截止（不包含3对应的元素）
```

**`过滤数组，组成新的数组`**

```JS
filter(callback(element[, index[, array]])[, thisArg]) // 生产新的数组，不改变原数组，参数形式与forEach方法相同，主要对数组做过滤抽取操作

let arr = [1,'a',2,'b',3,'c',4,'d',5,'e']
let newArr = arr.filter(function(e,i,a){return typeof e === 'number'})	// [1,2,3,4,5]
```

#### **转换类**

**`将数组转化为字符串`**

```JS
1.join()				// 将数组元素组合为字符串 ,	有参转换和无参转换
let arr = [1,2,3,4,5]

let StringValue = arr.join() 				// "1,2,3,4,5"
let StringValue2 = arr.join("") 			//	"12345"
```

**`将可迭代对象或者类似数组转换为数组`**

```JS
Array.from(arrayLike[, mapFn[, thisArg])	// ES6 方法 返回新数组
// arrayLike 需要转换的原对象，mapFn存在每个元素都会执行此函数，thisArg指针

String => Array
Array.from('foo');
// [ "f", "o", "o" ]

Set => Array
const set = new Set(['foo', 'bar', 'baz', 'foo']);
Array.from(set);
// [ "foo", "bar", "baz" ]

Map => Array
const mapper = new Map([['1', 'a'], ['2', 'b']]);
Array.from(mapper.values());
// ['a', 'b'];
Array.from(mapper.keys());
// ['1', '2'];

使用箭头函数
Array.from([1, 2, 3], x => x + x);
// [2, 4, 6]
```

## Java [Arrays 工具类](http://c.biancheng.net/view/5885.html)

java.util.Arrays类能方便地操作数组，它提供的所有方法都是静态的。静态方法是属于类的，不是属于类的对象。所以可以直接使用类名加方法名进行调用。Arrays作为一个工具类，能很好的操作数组。

## [Java ArrayList](https://www.runoob.com/java/java-arraylist.html)

ArrayList 类是一个可以动态修改的数组，与普通数组的区别就是它是没有固定大小的限制，我们可以添加或删除元素。

基本操作

```Java
import java.util.ArrayList; // 引入 ArrayList 类

1.创建对象
    ArrayList<E> objectName = new ArrayList()
  	// E: 泛型数据类型，用于设置 objectName 的数据类型，只能为引用数据类型。
  	ArrayList<String> arr = new ArrayList();
2.添加元素
  arr.add([指定要插入的位置,]"google")	//	默认插入最后一位
3.访问元素
  arr.get(1)	// 访问索引为 1 的数组元素
4.修改元素
  arr.set(2,"google")		// 第一个参数为索引位置，第二个为要修改的值
5.删除元素
  arr.remove(3)		 // 删除第四个元素
6.计算大小
  arr.size()
```

遍历

```java
1.for循环
  
  
2.for-Each
  for (String element : arr) {sout(element)}

3.forEach方法
  arr.forEach((e) -> {
    e = e + 10;
  })
```

排序

```java
判断两个字符是否
```

此类型的其他方法

```java
===
```



