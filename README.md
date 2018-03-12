# AlgorithmScripting
FreeCodeCamp 基础+中级 算法

#### 翻转字符串

```
function reverseString(str) {
  return str.split("").reverse().join("");
}
```
#### 计算一个整数的阶乘

```
function factorialize(num) {
  if(num < 1){
    return 1;
  }
  else{
    return factorialize(num - 1) * num;
  }
}
```
#### 检查回文字符串
```
function palindrome(str) {

  var reg=/[^0-9a-z]/gi;
  var prestr=str.replace(reg,"").toLowerCase();
  var currstr=prestr.split("").reverse().join("");
  return currstr==prestr?true:false;
}
```
#### 找出最长单词，并返回它的长度。
```
function findLongestWord(str) {
 
  var strArr=str.split(" ").map(function(val){return val.length;}).sort(function(a,b){return b-a;});
  var strNum=strArr[0];
  return strNum;
 
  
  

 
}
```
#### 单词首字母大写
```
function titleCase(str) {
  // 请把你的代码写在这里
  var upStr=str.split(" ").map(function(val){
    var a=val.toLowerCase().split("");
    a[0]=a[0].toUpperCase();
    return a.join("");
  }).join(" ");
  return upStr;
  
}

```
#### 找出多个数组中的最大数,然后把它们串联起来，形成一个新数组。
```
function largestOfFour(arr) {
  // 请把你的代码写在这里
  var Arr=[];
  for(var i=0;i<arr.length;i++){
  Arr[i]=arr[i].sort(function(a,b){
     return a-b;
   }).pop();
    
    
  }
  return Arr;
}
 
```
#### 检查字符串结尾，判断一个字符串(str)是否以指定的字符串(target)结尾。
```
function confirmEnding(str, target) {
  // 请把你的代码写在这里
  return str.substr(-target.length) == target;
}

```
#### 重复输出字符串，重复一个指定的字符串 num次，如果num是一个负数则返回一个空字符串。
```
function repeat(str, num) {
  // 请把你的代码写在这里
  var str1=str;
 if(num>0){
   for(var i=1; i<num; i++){
     str+=str1;
   }
   return str;
 }
 else{
   return "";
 } 
}

```
#### 截断字符串

（用瑞兹来截断对面的退路）

如果字符串的长度比指定的参数num长，则把多余的部分用...来表示。

切记，插入到字符串尾部的三个点号也会计入字符串的长度。

但是，如果指定的参数num小于或等于3，则添加的三个点号不会计入字符串的长度。
```
function truncate(str, num) {
  // 请把你的代码写在这里

if(num>=str.length){
  return str;
}
  if(num>3){
    return str.slice(0,num-3)+'...';
  }
  else{
    return str.slice(0,num)+'...';
  }
}

```
#### 猴子吃香蕉, 分割数组

（猴子吃香蕉可是掰成好几段来吃哦）

把一个数组arr按照指定的数组大小size分割成若干个数组块。
```
function chunk(arr, size) {
  // 请把你的代码写在这里
var len=0;
  var arr1=[];
  while(len<arr.length){
    arr1.push(arr.slice(len,len+=size));
  }

return arr1;
}

```
#### 截断数组

返回一个数组被截断n个元素后还剩余的元素，截断从索引0开始。
```
function slasher(arr, howMany) {
  // 请把你的代码写在这里
return arr.splice(howMany);
}
```
#### 比较字符串

（蛤蟆可以吃队友，也可以吃对手）

如果数组第一个字符串元素包含了第二个字符串元素的所有字符，函数返回true。
```
function mutation(arr) {
  // 请把你的代码写在这里

var lowerStr1 = arr[0].toLowerCase();
  var lowerStr2 = arr[1].toLowerCase();
  var str2Arr = lowerStr2.split("");
  for(var i=0; i < lowerStr2.length; i++){
    if(lowerStr1.indexOf(str2Arr[i])==-1){
      return false;
    }
  }
return true;
}

```
#### 过滤数组假值

（真假美猴王）

删除数组中的所有假值。

在JavaScript中，假值有false、null、0、""、undefined 和 NaN。
```
function bouncer(arr) {
  // 请把你的代码写在这里

  
  return arr.filter(function(val){
    return val;
  });
}
```
#### 摧毁数组

金克斯的迫击炮！

实现一个摧毁(destroyer)函数，第一个参数是待摧毁的数组，其余的参数是待摧毁的值。
```
function destroyer(arr) {
  // 请把你的代码写在这里
var args=[];
  for(var i=1;i<arguments.length;i++){
    args.push(arguments[i]);
  }
 var arr1=arr.filter(function(val){
   return args.indexOf(val)==-1;
 });
  return arr1;

}
```
#### 数组排序并找出元素索引

我身在何处？

先给数组排序，然后找到指定的值在数组的位置，最后返回位置对应的索引。
```
function where(arr, num) {
  // 请把你的代码写在这里
arr.push(num);
  var arr1=arr.sort(function(a,b){
    return a-b;
  });
 for(var i=0;i<arr1.length;i++){
   if(arr1[i]==num){
     return i;
   }
 }
}
```
####凯撒密码

（让上帝的归上帝，凯撒的归凯撒）

下面我们来介绍风靡全球的凯撒密码Caesar cipher，又叫移位密码。

移位密码也就是密码中的字母会按照指定的数量来做移位。 
```
function rot13(str) { // LBH QVQ VG!
  // 请把你的代码写在这里
 var arr=str.split("");
  var str1=[];
  for(var i=0;i<arr.length;i++){
    var num=arr[i].charCodeAt();
    if(num>=65&&num<=77){
      num+=13;
    }
    else if(num>77&&num<=90){
      num-=13;
    }
    str1.push(String.fromCharCode(num));
  }
  return str1.join("");
}
 
```
#### 我们会传递给你一个包含两个数字的数组。返回这两个数字和它们之间所有数字的和。

最小的数字并非总在最前面。
```
function sumAll(arr) {
 var min=Math.min(arr[0],arr[1]) ;
  var max=Math.max(arr[0],arr[1]);
  var arr1=[];
  for(var i=0;i<=(max-min);i++){
    arr1[i]=min+i;
  }
  return arr1.reduce(function(a,b){
    return a+b;
  });
}

```
#### 比较两个数组，然后返回一个新数组，该数组的元素为两个给定数组中所有独有的数组元素。换言之，返回两个数组的差异。
```
function diff(arr1, arr2) {
var newArr1=arr1.filter(function(val){
  return arr2.indexOf(val) === -1;
});
  var newArr2=arr2.filter(function(val){
    return arr1.indexOf(val) === -1;
  });
  return newArr1.concat(newArr2);

}
```
#### 将给定的数字转换成罗马数字。
```
function convert(num) {
 var nums=[1000,900,500,400,100,90,50,40,10,9,5,4,1] ;
 var romans=["m","cm","d","cd","c","xc","l","xl","x","ix","v","iv","i"] ;
  var str='';
  nums.forEach(function(item,index,array){
    while(num>=item){
      str+=romans[index];
      num-=item;
      
    }
  });
  return str.toUpperCase();
}
```
#### 写一个 function，它遍历一个对象数组（第一个参数）并返回一个包含相匹配的属性-值对（第二个参数）的所有对象的数组。如果返回的数组中包含 source 对象的属性-值对，那么此对象的每一个属性-值对都必须存在于 collection 的对象中。
```
function where(collection, source) {
var arr = [];
            
  for (var i=0; i< collection.length; i++) {
     for (var key in collection[i]) {
     var count = 0;
        for (var key2 in source) {
             if (collection[i].hasOwnProperty(key2)) {
                    if (source[key2] == collection[i][key2]) {
                        count++;
                    }   
 if (count == Object.getOwnPropertyNames(source).length && key == key2) {
   arr.push(collection[i]);
      }
    }
  }
 }
     }
  return arr;



  
}
```
#### 使用给定的参数对句子执行一次查找和替换，然后返回新句子。

第一个参数是将要对其执行查找和替换的句子。

第二个参数是将被替换掉的单词（替换前的单词）。

第三个参数用于替换第二个参数（替换后的单词）。

注意：替换时保持原单词的大小写。例如，如果你想用单词 "dog" 替换单词 "Book" ，你应该替换成 "Dog"。
```
function myReplace(str, before, after) {
 


  if(before[0] === before[0].toUpperCase()){
    after = after[0].toUpperCase() + after.slice(1);
    
  }
  str = str.replace(before,after);
  return str;
}

```
#### 把指定的字符串翻译成 pig latin。

Pig Latin 把一个英文单词的第一个辅音或辅音丛（consonant cluster）移到词尾，然后加上后缀 "ay"。

如果单词以元音开始，你只需要在词尾添加 "way" 就可以了。
```
function translate(str) {

var a = str.search(/[aeiou]/);
            var str2 = str;
            if (a === 0) {
                str2 += "way";
            } else {
                str2 = str.substr(a);
                str2 += str.substr(0, a);
                str2 += "ay";
            }
            return str2;
       



}
```
#### DNA 链缺少配对的碱基。依据每一个碱基，为其找到配对的碱基，然后将结果作为第二个数组返回。

Base pairs（碱基对） 是一对 AT 和 CG，为给定的字母匹配缺失的碱基。

在每一个数组中将给定的字母作为第一个碱基返回。

例如，对于输入的 GCG，相应地返回 [["G", "C"], ["C","G"],["G", "C"]]

字母和与之配对的字母在一个数组内，然后所有数组再被组织起来封装进一个数组。
```
function pair(str) {
 var arr = str.split("");
  var pair='';
  var result = arr.map(function(val){
    switch(val){
      case 'A':
        pair = 'T';
        break;
      case 'T':
        pair = 'A';
        break;
      case "C":
        pair = 'G';
        break;
      case 'G':
        pair = 'C';
           
    }
    return [val,pair];
  });
  return result;
  
  
    


}
```
#### 从传递进来的字母序列中找到缺失的字母并返回它。

如果所有字母都在序列中，返回 undefined。
```
function fearNotLetter(str) {
var sub;
  for (var i=0;i<str.length - 1;i++){
    sub = str.charCodeAt(i+1)-str.charCodeAt(i);
    if(sub==1){
      if(i==str.length){
        return undefined;
      }
    }
    else{
      return String.fromCharCode(str.charCodeAt(i)+1);
    }
  }
}

```
#### 检查一个值是否是基本布尔类型，并返回 true 或 false。

基本布尔类型即 true 和 false。
```
function boo(bool) {
  if(bool===true||bool===false){
    return true;
  }
  return false;

}

```
#### 写一个 function，传入两个或两个以上的数组，返回一个以给定的原始数组排序的不包含重复值的新数组。

换句话说，所有数组中的所有值都应该以原始顺序被包含在内，但是在最终的数组中不包含重复值。

非重复的数字应该以它们原始的顺序排序，但最终的数组不应该以数字顺序排序。
```
function unite(arr1, arr2, arr3) {

var newArr=[];
  for(var i=1;i<arguments.length;i++){
    for(var j=0;j<arguments[i].length;j++){
      if(arguments[0].indexOf(arguments[i][j])==-1){
         newArr.push(arguments[i][j]);
         }
    }
  }
newArr=arguments[0].concat(newArr);
return newArr;
}

```
#### 将字符串中的字符 &、<、>、" （双引号）, 以及 ' （单引号）转换为它们对应的 HTML 实体。
```
function convert(str) {
  var arr=str.split("");
  for( var i=0;i<arr.length;i++){
    switch(arr[i]){
      case '&':
        arr.splice(i,1,'&amp;');
        break;
      case '>':
        arr.splice(i,1,'&gt;');
        break;
      case '<':
        arr.splice(i,1,'&lt;');
        break;
      case "'":
        arr.splice(i,1,'&apos;');
        break;
      case '"':
        arr.splice(i,1,'&quot;');
      
    }
  }
  str=arr.join("");
  return str;




}
```
#### 将字符串转换为 spinal case。Spinal case 是 all-lowercase-words-joined-by-dashes 这种形式的，也就是以连字符连接所有小写单词。
```
function spinalCase(str) {
  
str=str.replace(/([A-Z]+)/g,' $1');
  str=str.replace(/\s+|_+/g,'-'); 
  if(str[0]=='-'){
    str=str.substring(1);
  }
  str=str.replace(/--/g,'-');
  str=str.toLowerCase();
 return str;
}
```
#### 给一个正整数num，返回小于或等于num的斐波纳契奇数之和。

斐波纳契数列中的前几个数字是 1、1、2、3、5 和 8，随后的每一个数字都是前两个数字之和。

例如，sumFibs(4)应该返回 5，因为斐波纳契数列中所有小于4的奇数是 1、1、3。
```
function sumFibs(num) {
 var fibo = [1, 1];  
  var oddSum = 2;  
  while(true){
    var item = fibo[0] + fibo[1];   
    if(num < item){  
      return oddSum;
    }
    if(item % 2){   
      oddSum += item;    
    }
    fibo[0] = fibo[1];
    fibo[1] = item;
  }


}
```
#### 求小于等于给定数值的质数之和。

只有 1 和它本身两个约数的数叫质数。例如，2 是质数，因为它只能被 1 和 2 整除。1 不是质数，因为它只能被自身整除。

给定的数不一定是质数。
```
function sumPrimes(num) {
 var arr=[2];
  var sum=0;
  for(var i=2;i<=num;i++){
    var bCheck=true;
    for(var j=0;j<arr.length;j++){
      if(i%arr[j]===0){
        bCheck=false;
        break;
      }
    }
    if(bCheck){
      arr.push(i);
    }
  }
  for(var k=0;k<arr.length;k++){
    sum+=arr[k];
  }
  return sum;
}

```
#### 找出能被两个给定参数和它们之间的连续数字整除的最小公倍数。

范围是两个数字构成的数组，两个数字不一定按数字顺序排序。

例如对 1 和 3 —— 找出能被 1 和 3 和它们之间所有数字整除的最小公倍数。
```
function smallestCommons(arr) {
 arr=arr.sort(function(a,b){
    return a-b;
  });
  function fun(m,n){
    if(m%n===0) return n;
    return fun(n,m%n);
  }
  var num=arr[0];
  for(var i=arr[0]+1;i<=arr[1];i++){
    num*=i/fun(num,i);
  }
  return num;


}
```
#### 写一个 function，它遍历数组 arr，并返回数组中第一个满足 func 返回值的元素。举个例子，如果 arr 为 [1, 2, 3]，func 为 function(num) {return num === 2; }，那么 find 的返回值应为 2。

如果你被卡住了，记得开大招 Read-Search-Ask。尝试与他人结伴编程、编写你自己的代码。
```
function find(arr, func) {
 var num = 0;
  for(var i=0;i<arr.length;i++){
    if(func(arr[i])===true){
      num=arr[i];
      break;
    }
  }
  if(num===0){
    return undefined;  
  }
  return num;

}

```
#### 队友该卖就卖，千万别舍不得。

当你的队伍被敌人包围时，你选择拯救谁、抛弃谁非常重要，如果选择错误就会造成团灭。

如果是AD或AP，优先拯救。

因为AD和AP是队伍输出的核心。

其次应该拯救打野。

因为打野死了对面就可以无所顾虑地打龙。

最后才是辅助或上单。

因为辅助和上单都是肉，死了也不会对团队造成毁灭性影响，该卖就卖。

但真实中的团战远比这要复杂，你的队伍很可能会被敌人分割成2个或3个部分。

当你救了一个重要的人时，很可能其他队友也会因此获救。

举个例子：

辅助和AD经常是在一起的，打野和中单在一起，上单经常一个人。

你救了AD，辅助也经常因此获救。

让我们来丢弃数组(arr)的元素，从左边开始，直到回调函数return true就停止。

第二个参数，func，是一个函数。用来测试数组的第一个元素，如果返回fasle，就从数组中抛出该元素(注意：此时数组已被改变)，继续测试数组的第一个元素，如果返回fasle，继续抛出，直到返回true。

最后返回数组的剩余部分，如果没有剩余，就返回一个空数组。

如果你被卡住了，记得开大招 Read-Search-Ask。尝试与他人结伴编程。编写你自己的代码。
```
function drop(arr, func) {
for(var i=0;i<arr.length;i++){
    if(func(arr[i])===false){
      arr.splice(i,1,'false');
    }else{
      break;
    }
  }
  arr=arr.filter(function(a){
    return a!='false';
  });

  return arr;
}

```
#### 
对嵌套的数组进行扁平化处理。你必须考虑到不同层级的嵌套。
```
function steamroller(arr) {
var newArr=[];
  function fun(a){
    for(var j=0;j<a.length;j++){
      if(Array.isArray(a[j])===true){
        fun(a[j]);    
      }else{
        newArr.push(a[j]);      
      }
    }
    return newArr;
  }
  fun(arr); 

  return newArr;


}

```
#### 传入二进制字符串，翻译成英语句子并返回。

二进制字符串是以空格分隔的。
```
function binaryAgent(str) {
 var arr=str.split(' ');
  var arr10=[];
  var newStr='';
  for(var i=0;i<arr.length;i++){
    arr10.push(parseInt(arr[i],2));
  }
  for(var j=0;j<arr10.length;j++){
    newStr+=String.fromCharCode(arr10[j]);
  }
  return newStr;


}

```
#### 所有的东西都是真的！

完善编辑器中的every函数，如果集合(collection)中的所有对象都存在对应的属性(pre)，并且属性(pre)对应的值为真。函数返回ture。反之，返回false。
```
function every(collection, pre) {
function check(element, index, array) {
                return element[pre];
            }
            if (collection.every(check)) {
                return true;
            } else {
              return false;}

  
  
}
```
创建一个计算两个参数之和的 function。如果只有一个参数，则返回一个 function，该 function 请求一个参数然后返回求和的结果。

例如，add(2, 3) 应该返回 5，而 add(2) 应该返回一个 function。

调用这个有一个参数的返回的 function，返回求和的结果：

var sumTwoAnd = add(2);

sumTwoAnd(3) 返回 5。

如果两个参数都不是有效的数字，则返回 undefined。
function add(x) {
 if (arguments.length === 1 && typeof x === "number") {
   return function (y) { 
     if (typeof y === "number"){
       return x + y;
     }  
   }; 
 }else {
    if (typeof x !== "number"|| typeof arguments[1] !== "number") {
      return undefined;
    }
    return arguments[0] + arguments[1];
  } 
} 
如果传入字符串是一个有效的美国电话号码，则返回 true.

用户可以在表单中填入一个任意有效美国电话号码. 下面是一些有效号码的例子(还有下面测试时用到的一些变体写法):

555-555-5555
(555)555-5555
(555) 555-5555
555 555 5555
5555555555
1 555 555 5555
在本节中你会看见如 800-692-7753 or 8oo-six427676;laskdjf这样的字符串. 你的任务就是验证前面给出的字符串是否是有效的美国电话号码. 区号是必须有的. 如果字符串中给出了国家代码, 你必须验证其是 1. 如果号码有效就返回 true ; 否则返回 false.
function telephoneCheck(str) {
 var newStr = str.replace(/\D/g, '');
  
  if( (newStr.length !== 10 && newStr.length !== 11) || (newStr.length === 11 && newStr[0] !== '1') ) {
    return false;
  }
  var reg = /^1? ?\d{3}[- ]?\d{3}[- ]?\d{4}$|^1? ?\(\d{3}\) ?\d{3}-\d{4}$/;
  return reg.test(str);



} 

创建一个函数，接受两个或多个数组，返回所给数组的 对等差分(symmetric difference) (△ or ⊕)数组.

给出两个集合 (如集合 A = {1, 2, 3} 和集合 B = {2, 3, 4}), 而数学术语 "对等差分" 的集合就是指由所有只在两个集合其中之一的元素组成的集合(A △ B = C = {1, 4}). 对于传入的额外集合 (如 D = {2, 3}), 你应该安装前面原则求前两个集合的结果与新集合的对等差分集合 (C △ D = {1, 4} △ {2, 3} = {1, 2, 3, 4}).

function sym(args) {
 var arr = [];
  for(var i = 0; i < arguments.length; i++) {
    arr.push(arguments[i]);
  }
  for(var j = 0; j < arr.length; j++) {
    for(var k = 0; k < arr[j].length; k++) {
      for(var m = k + 1; m < arr[j].length; m++) {
        if(arr[j][k] === arr[j][m]) {
          arr[j].splice(m, 1);
          m -= 1;
          k -= 1;
        }
      }
    }
  }
  return arr.reduce(function(x, y) {
    return diff(x, y);
  });
  function diff(arr1, arr2) {
    for(var i = 0; i < arr1.length; i++) {
      for(var j = 0; j < arr2.length; j++) {
        if(arr1[i] === arr2[j]) {
          arr1.splice(i, 1); 
          arr2.splice(j, 1);
          i -= 1;
          break;
        }
      }
    }
    return arr1.concat(arr2);
  } 
}
设计一个收银程序 checkCashRegister() ，其把购买价格(price)作为第一个参数 , 付款金额 (cash)作为第二个参数, 和收银机中零钱 (cid) 作为第三个参数.

cid 是一个二维数组，存着当前可用的找零.

当收银机中的钱不够找零时返回字符串 "Insufficient Funds". 如果正好则返回字符串 "Closed".

否则, 返回应找回的零钱列表,且由大到小存在二维数组中.
function checkCashRegister(price, cash, cid) {
 var change = [];
  var diff = cash - price;
  var cidObj = {
    "ONE HUNDRED": {val: 100},
    "TWENTY": {val: 20},
    "TEN": {val: 10},
    "FIVE": {val: 5},
    "ONE": {val: 1},
    "QUARTER": {val: 0.25},
    "DIME": {val: 0.1},
    "NICKEL": {val: 0.05},
    "PENNY": {val: 0.01}
  };
  

  for(var k of cid) {
    cidObj[k[0]].num = Math.ceil( k[1] / (cidObj[k[0]].val) );
  }

 
  for( var i of Object.keys(cidObj) ) {
    var n = 0;
    
    while(diff >= cidObj[i].val && cidObj[i].num !== 0) {
      cidObj[i].num--; 
      n++;
      diff = (diff - cidObj[i].val).toFixed(2); 
      if(cidObj[i].num === 0 || diff < cidObj[i].val) {
        change.push( [i, n * (cidObj[i].val)] );
        break;
      }
    }
  }
  
  diff = Math.ceil(diff);
  if(diff === 0 ) {
    for( var j of Object.keys(cidObj) ) {
      if(cidObj[j].num !== 0) {
        return change;
      }
    }
    return "Closed";
  }
  else{
    return "Insufficient Funds";
  }
}


依照一个存着新进货物的二维数组，更新存着现有库存(在 arr1 中)的二维数组. 如果货物已存在则更新数量 . 如果没有对应货物则把其加入到数组中，更新最新的数量. 返回当前的库存数组，且按货物名称的字母顺序排列.

function updateInventory(arr1, arr2) {
     for(var i = 0; i < arr1.length; i++) {
    for(var j = 0; j < arr2.length; j++) {
      if(arr2[j][1] === arr1[i][1]) {
        arr1[i][0] += arr2[j][0];
        arr2.splice(j, 1);
        j--;
      }
    }
  }
  var arr = arr1.concat(arr2);
  
  arr.sort(sortFun);
  
  function sortFun(x, y) {
    var a = x[1].charCodeAt(0);
    var b = y[1].charCodeAt(0);
    
    return a - b;
  }
  
  return arr;
}

// 仓库库存示例
var curInv = [
    [21, "Bowling Ball"],
    [2, "Dirty Sock"],
    [1, "Hair Pin"],
    [5, "Microphone"]
];

var newInv = [
    [2, "Hair Pin"],
    [3, "Half-Eaten Apple"],
    [67, "Bowling Ball"],
    [7, "Toothpaste"]
];

把一个字符串中的字符重新排列生成新的字符串，返回新生成的字符串里没有连续重复字符的字符串个数.连续重复只以单个字符为准

例如, aab 应该返回 2 因为它总共有6中排列 (aab, aab, aba, aba, baa, baa), 但是只有两个 (aba and aba)没有连续重复的字符 (在本例中是 a).
function permAlone(str) {
 var count;
  function getCount() {
    var arr = str.split('');
    count = 0;
    permutations(0, arr);
    return count;
  }
  var res = getCount();
  
  function permutations(n, arr) {
    for(var i = n; i < arr.length; i++) {
     
      swap(i, n, arr);
      
     
      if(arr[n] === arr[n-1]) {
        swap(i, n, arr); 
        continue;
      }
      
      
      if(n < arr.length-1) {
        permutations(n+1, arr);
      }
      else {
       
        if(arr[n] !== arr[n-1]) {
          count++;
        }
      }
     
      swap(i, n, arr);
    }
  }
  
  
  function swap(i, n, arr) {
    var t;
    t = arr[i];
    arr[i] = arr[n];
    arr[n] = t;
  }
  return res;

}

让日期区间更友好！

把常见的日期格式如：YYYY-MM-DD 转换成一种更易读的格式。

易读格式应该是用月份名称代替月份数字，用序数词代替数字来表示天 (1st 代替 1).

记住不要显示那些可以被推测出来的信息: 如果一个日期区间里结束日期与开始日期相差小于一年，则结束日期就不用写年份了；在这种情况下，如果月份开始和结束日期如果在同一个月，则结束日期月份也不用写了。

另外, 如果开始日期年份是当前年份，且结束日期与开始日期小于一年，则开始日期的年份也不用写。
function makeFriendlyDates(arr) {
   var months = [" ","January ", "February ", "March ", "April ", "May ", "June ", "July ", "August ", "September ", "October ", "November ", "December ",];
  var arrs = [];
  var stmon,stdate,styear,ovmon,ovdate,ovyear,start,over;

  function day(val){
    if(val%10 == 1 && val != 11)return val+"st";
    else if(val%10 == 2 && val != 12)return val+"nd";
    else if(val%10 == 3 && val != 13)return val+"rd";
    else return val+"th";
  }
     arr = arr.map(function(item){
       return item.split("-");
     });
     arr.forEach(function(item , index){
               item.forEach(function(item1 ,index1){
                  switch(index1+index*3){
                      case 0: styear= parseInt(item1);break;
                      case 1: stmon= parseInt(item1);break;
                      case 2: stdate= parseInt(item1);break;
                      case 3: ovyear= parseInt(item1);break;
                      case 4: ovmon= parseInt(item1);break;
                      case 5: ovdate= parseInt(item1);break;
                  }
          });
       if(index === 0){
           start = parseInt(item.reduce(function(a, b) {   
               return a.concat(b);
           }));
       }
       else {
               over = parseInt(item.reduce(function(a, b) {
               return a.concat(b);
           }));
       }
     });
  var nowyear = 2017; 
  if(start > over) return;  
  var bool = (over - start) <= 10000;
  if(start === over){
      return [months[stmon]+day(stdate)+ ", "+styear];
  }
  arrs[0] = months[stmon]+day(stdate);  
  if(bool){
          if(nowyear != styear)arrs[0] = arrs[0] + ", "+ styear;
          if(ovmon == stmon && styear == ovyear)arrs[1] = day(ovdate);
            else arrs[1] = months[ovmon] + day(ovdate);
            if(ovmon == stmon && ovdate == stdate)arrs[1] = arrs[1] + ", "+ ovyear;
  }
    else {
          arrs[0] = arrs[0] + ", "+ styear;
          arrs[1] = months[ovmon] + day(ovdate);
          arrs[1] = arrs[1] + ", "+ ovyear;
 }
  return arrs;
}
用下面给定的方法构造一个对象.

方法有 getFirstName(), getLastName(), getFullName(), setFirstName(first), setLastName(last), and setFullName(firstAndLast).

所有有参数的方法只接受一个字符串参数.

所有的方法只与实体对象交互.
var Person = (function(firstAndLast) {
  var name;
  return function(firstAndLast) {
    name = firstAndLast;
    this.getFullName = function() {
      return name;
    };
    
    this.getFirstName = function() {
      var arrName = name.split(' ');
      return arrName[0];
    };
    
    this.getLastName = function() {
      var arrName = name.split(' ');
      return arrName[1];
    };
    
    this.setFirstName = function(first) {
      var arrName = name.split(' ');
      arrName[0] = first;
      name = arrName.join(' ');
      return name;
    };
    
    this.setLastName = function(last) {
      var arrName = name.split(' ');
      arrName[1] = last;
      name = arrName.join(' ');
      return name;
    };
    
    this.setFullName = function(firstAndLast) {
      var arrName = name.split(' ');
      name = firstAndLast;
      return name;
    };
    
  };
})();

返回一个数组，其内容是把原数组中对应元素的平均海拔转换成其对应的轨道周期.

原数组中会包含格式化的对象内容，像这样 {name: 'name', avgAlt: avgAlt}.

至于轨道周期怎么求，戳这里 on wikipedia (不想看英文的话可以自行搜索以轨道高度计算轨道周期的公式).

求得的值应该是一个与其最接近的整数，轨道是以地球为基准的.

地球半径是 6367.4447 kilometers, 地球的GM值是 398600.4418, 圆周率为Math.PI

function orbitalPeriod(arr) {
var GM = 398600.4418;
  var earthRadius = 6367.4447;
  
  function cal(h) {
    var t = Math.round(Math.pow(((4*(Math.pow(Math.PI, 2)) * Math.pow((h+earthRadius), 3))/GM), 0.5));
    return t;
  }
  
  var res = func(arr);
  return res;
  
  function func(arr) {
    var res = [];
    for(var i of arr) {
      var obj = {};
      obj.name = i.name;
      obj.orbitalPeriod = cal(i.avgAlt);
      res.push(obj);
    }
    return res;
  }
}

找到你的另一半

都说优秀的程序员擅长面向对象编程，但却经常找不到另一半，这是为什么呢？因为你总是把自己局限成为一个程序员，没有打开自己的思维。

这是一个社群的时代啊，在这里你应该找到与你有相同价值观但又互补的另一半。

譬如：你编程能力强，估值11分，如果以20分为最佳情侣来计算，你应该找一个设计能力强，估值为9分的女生。

那么当你遇到一个设计能力为9分的女生，千万别犹豫，大胆去表白。千万别以为后面的瓜比前面的甜哦。

举个例子：有一个能力数组[7,9,11,13,15]，按照最佳组合值为20来计算，只有7+13和9+11两种组合。而7在数组的索引为0，13在数组的索引为3，9在数组的索引为1，11在数组的索引为2。

所以我们说函数：pairwise([7,9,11,13,15],20) 的返回值应该是0+3+1+2的和，即6。

我们可以通过表格来更直观地查看数组中索引和值的关系：

Index	0	1	2	3	4
Value	7	9	11	13	15
function pairwise(arr, arg) {
 var val=0; 
    for(var i = 0; i < arr.length; i++ ){  
            for(var j = i+1; j < arr.length; j++){ 
                if(arr[i] + arr[j] == arg){
                      val += i+j;    
    
                      arr[j] = "abc";
            　　　　　　break;
                }
            }
    }
  return val;
}


