
### null / undefined
- 都表示没有
- null：意料之中 一般是开始不知道值，我们手动设置为null，后期再赋值；用null作为初始的空值，不占位置；设置为0 会再栈内存中有自己的存储空间
- undefined：意料之外 

### object 对象数据类型-普通对象
> {[key]:[value],...}键值对（属性名：属性值） 属性名不可重复

### js 4种数据类型检测
- typeof [val]:用来检测数据类型的运算符
- instanceof ：用来检测当前实例是否隶属于某个类
- constructor ： 基于构造函数检测数据类型（基于类的方式）
- Object.prototype.toString.call():检测数据类型的最好方法

### JS 判断语句
> 条件成立做是吗？不成立做什么？
- if/else if/else
- 三元运算符
- switch case

1.if/else
```
if(条件){
    条件成立执行
}else if(条件2){
    条件2成立执行
}
...
else{
    以上条件都不成立 
    执行
}
//三元
let a = 10
a >= 10? console.log('haha'):console.log('xixi')

//switch case (不加break 不论后面条件是否成立都要执行，直到break为止；每个case用的都是‘===’绝对相等)
let a = 10
switch(a){
    case 1:
        console.log('i am 1')
        break
    case 5:
        console.log('i am 5')
        break
    case 10:
        console.log('i am 10')
        break
    default:
        console.log('i don\'t know')
}
```

### 循环
- for
- for in
- for of (ES6新增)
- while
- do while 
< continue：结束此次循环（continue后面的代码不再执行） 继续执行下一次循环
< break：强调结束整个循环（break后面的代码也不执行）整个循环直接结束

### for in
```
var obj = {
    name : 'haha',
    age : 19,
    friends:'xixi,lili,kim',
    1:20,
    2:140,
    3:144
}
//优先遍历数字 从小到大
for (var key in obj){
   //key 当前对象属性名
    console.log(key,obj[key])
}
```

#### newsBox li:nth-child(even)

### 函数 function
> 函数：一个方法 / 一个功能体 ，把实现某个功能的代码放在一起进行封装， 以后想要操作这个功能，就只要执行函数即可 =>封装：减少页面冗余代码，提高代码复用率（低耦合高内聚）
- 创建函数
    + 形参
    + 返回值
- 执行函数
    + 实参
- arguments
- 函数底层运行机制

#### 创建函数
```
function[函数名]([形参变量1],...){
    //函数体：基于js完成需要实现的功能
    return [处理后的结果]
}
[函数名]([实参1],...)
//创建函数的时候我们设置了形参变量，如果执行的时候没有传递对应的实参 那么默认：undefined

// 函数返回值
// 没有写return 函数默认值为undefined
// 函数遇到return 后面的代码就不执行了

```

### 匿名函数
```
// ES5匿名函数
// 匿名函数之函数表达式 把一个匿名函数本身作为值赋值给其他东西
// 这种函数一般不是手动触发执行，一般靠其他程序驱动触发执行
document.body.onclick = function(){
    // 设置定时器
    // setTimeout(() => {
    // }, timeout);

    setTimeout(function(){

    },1000)
}
// 自执行函数:创建完一个匿名函数 立马执行
(function(n){

})(100) //n = 100
```
### 保留字和关键字
```
let a = {
    n:1
}
let b = a
a.x = a ={
    n:2
}
console.log(a.x)
console.log(b)

```
```
var c = 100+true+21.2+null+undefined+'Tencent'+[]+null+9+false
//122.2+undefined -> NaN
NaNTencent+[] -> NaNTencent
NaNTencentnull9false

console.log(alert(1))
alert 没有返回值 默认返回undefined

```

### == VS ===
> ==:相等 数据类型不同，先转为一样的再比较
> ===:绝对相等 要求类型和值相同才为true （switch 判断中，每一种case值的比较都是基于===来完成的）

```
let i = '10'
i = i+1 -> '10'+1 -> '101'
i += 1 -> '101'
i++ -> i=11 //纯粹的数字运算

```
### i++ vs ++i
> 都是数学运算中的累加1 区别是计算的顺序
5+(i++) //先算5+i=6 然后i+1 （i=2） ->6
5+(++i) //先i+1（i=2） 然后再5+i    ->7

### 同源策略
### 跨域方法
> jsonp 
> CORS(ACAC:true 说明存在安全问题 携带cookie访问 可以获取个人敏感信息 有漏洞) 如果CORS头缺少ACAO 则浏览器拦截跨域请求
> CORS漏洞和CSRF漏洞
+ 同：都要借助第三方网站、借助ajax异步过程、都要用户登陆
+ 异：第三方网站可以利用CORS漏洞可以读取受害者敏感信息、第三方网站可以利用CSRF漏洞替受害者完成转账等敏感操作、有CORS漏洞一般都有CSRF漏洞
- 防御：ACAO 严格校验来自请求数据包的：Origin；避免ACAC设置为true；减少ACAMs所允许的方法
