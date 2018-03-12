# AlgorithmScripting
FreeCodeCamp 基础+中级 算法 
####翻转字符串
先把字符串转化成数组，再借助数组的reverse方法翻转数组顺序，最后把数组转化成字符串。
 ` function reverseString(str) {
         return str.split("").reverse().join("");
     }`
