# AlgorithmScripting
FreeCodeCamp 基础+中级 算法

#### 翻转字符串

```function reverseString(str) {
  return str.split("").reverse().join("");
}```

#### 计算一个整数的阶乘

```function factorialize(num) {
  if(num < 1){
    return 1;
  }
  else{
    return factorialize(num - 1) * num;
  }
}```

### 检查回文字符串
```function palindrome(str) {

  var reg=/[^0-9a-z]/gi;
  var prestr=str.replace(reg,"").toLowerCase();
  var currstr=prestr.split("").reverse().join("");
  return currstr==prestr?true:false;
}```


