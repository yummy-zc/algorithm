## 28 实现 str

![image-20210208163322152](/Users/yummy/web开发/文章笔记/typora-notes/Typora笔记/算法/LeetCode（Lucifer）/基础篇/数组.assets/image-20210208163322152.png)

内置函数处理

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

```java
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

滑动窗口，双指针

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

```java
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

注意到 移动主串上的指针时，在未进行完完全的比较成功时不要移动主串指针，仅加上某个变量值来访问后面元素，否者容易忽略到意外情况

**KMP 解法**