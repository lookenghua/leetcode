实现 [strStr()](https://baike.baidu.com/item/strstr/811469) 函数。

给你两个字符串 `haystack` 和 `needle` ，请你在 `haystack` 字符串中找出 `needle` 字符串出现的第一个位置（下标从 0 开始）。如果不存在，则返回 `-1` 。

**说明：**

当 `needle` 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。

对于本题而言，当 `needle` 是空字符串时我们应当返回 0 。这与 C 语言的 [strstr()](https://baike.baidu.com/item/strstr/811469) 以及 Java 的 [indexOf()](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#indexOf(java.lang.String)) 定义相符。

**示例 1：**

```javascript
输入：haystack = "hello", needle = "ll"
输出：2
```

**示例 2：**

```javascript
输入：haystack = "aaaaa", needle = "bba"
输出：-1
```

**示例 3：**

```javascript
输入：haystack = "", needle = ""
输出：0
```

**提示：**

- `0 <= haystack.length, needle.length <= 5 * 104`
- `haystack` 和 `needle` 仅由小写英文字符组成

***

**解答:**

```javascript
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
    if(needle==="") return 0
    var arr = haystack.split(needle)
    return arr.length===1?-1:arr[0].length
};
```

**思路:**

先判断needle为空字符串的情况,直接返回0,然后用needle切分haystack字符串,如果存在的话,切分出来的数组,至少有两个元素,如果只有一个说明不存在这样的字符串,这时候返回-1,如果是存在的情况,数组第一个元素的长度,则是第一次出现的的下标。