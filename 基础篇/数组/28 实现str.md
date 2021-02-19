# 28 实现 str

## 题目描述

```
实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。

示例 1:

输入: haystack = "hello", needle = "ll"
输出: 2
示例 2:

输入: haystack = "aaaaa", needle = "bba"
输出: -1
说明:

当 needle 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。

对于本题而言，当 needle 是空字符串时我们应当返回 0 。这与C语言的 strstr() 以及 Java的 indexOf() 定义相符。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/implement-strstr
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。
```

## 方法一：内置函数处理

### 思路

（略）

### 复杂度分析

- 时间复杂度：
- 空间复杂度：

### 代码

JavaScript

```JS
// indexOf
var strStr = function (haystack, needle) {
  return haystack.indexOf(needle)
}

// search
var strStr = function(haystack, needle) {
    return haystack.search(needle);
};

// substr
var strStr = function (haystack, needle) {
  for(let i = 0; i < haystack.length - needle.length; i++) {
    if(haystack.substr(i, neddle.length) === neddle) 
      return i
  }
  return -1
}
```

Java

```Java
class Solution {
    public int strStr(String haystack, String needle) {
        if (haystack.toString() == needle.toString()) return 0
        for (int i = 0; i < haystack.length() - needle.length(); i++) {
            if (haystack.substring(i,i + needle.length()).equals(needle)) {
                return i;
            }
        }
        return -1;
    }
}
```

### **总结**

（略）



## 方法二：滑动窗口，双指针

### 思路

（略）

### 复杂度分析

- 时间复杂度：
- 空间复杂度：

### 代码

JavaScript

```JS
var strStr = function(haystack, needle) {
    let p = 0,j = 0;
    if (haystack.toString() == needle.toString()) return 0;
    while ( p < haystack.length && j < needle.length) {
        if (haystack[p+j] === needle[j]) {
            j++;
        } else {
            p++;
            j = 0;
        }
    }
    return j === needle.length ? p : -1
};
```

Java

```Java
class Solution {
    public int strStr(String haystack, String needle) {
    	int n = haystack.length(), m = needle.length();
      for (int i = 0; i < n - m; i++) {
        for (int j = 0; j < m; j++) {
          if (haystack.charAt(i) != needle.charAt(j)) break;
          if (j == m - 1) return i;
        } 
      }
      return -1;
    }
}
```

### **总结**

注意到 移动主串上的指针时，在未进行完完全的比较成功时不要移动主串指针，仅加上某个变量值来访问后面元素，否者容易忽略到意外情况

## **KMP 解法**

