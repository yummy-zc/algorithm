### 字符串

|         字符串         |               Java                |                     JS                      |
| :--------------------: | :-------------------------------: | :-----------------------------------------: |
|     获取字符串长度     |           str.length()            |                 str.length                  |
|       截取字符串       |     str.substring(start,end)      |  substring(s,t)，substr(s,length)，slice()  |
|   判断字符串是否相等   |            equals(str)            |               str.equals(str)               |
|  获取字符串中某个字符  |      charAt()，charCodeAt()       |   str[index]，str.charAt()，charCodeAt()    |
|    字符（串）的查找    | indexOf(String s)，lastIndexOf()  | indexOf()，lastIndexOf()，search()，match() |
|      字符串的修改      |        replace(oldS,newS)         |           replace()，replaceAll()           |
|    字符串大小写切换    |   toLowerCase()，toUpperCase()    |        toLowerCase()，toUpperCase()         |
|  字符串转换为字符数组  |           str.split('')           |                str.split('')                |
| 将字符数组转换为字符串 | new String(char[])，toCharArray() |                                             |
|      去掉首尾空格      |              trim()               |                   trim()                    |
|     判断字符串开头     |     startsWith(String prefix)     |               startsWith(str)               |
|     判断字符串结尾     |      endsWith(String suffix)      |                endsWith(str)                |
|    判断是否存在子串    |    contains(str)，indexOf(str)    |                includes(str)                |
|   判断字符串是否为空   |             isEmpty()             |                                             |
|      字符串的连接      |                                   |              str.concat(str2)               |
|                        |                                   |       JS 字符串方法拥有许多数组的方法       |
|    判断两个字符是否    |                ==                 |                     ===                     |