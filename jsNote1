
    md用法学习网站：
    <!-- https://maxiang.io -->
### 常用浏览器
- webkit 内核（V8引擎）
    + 谷歌
    + Safari
    + Opera >=V14
    + 国产、手机浏览器
- Gecko
    + 火狐
- Presto
    + OPera <V14
- Trident
    + IE
    + IE EDGE 开始使用双内核

QQ 百度 谷歌 火狐 360 UC Safari Opera 搜狗...
- Elements：查看结构样式 可修改内容
- console：调试代码
- Sources：查看源码
- Network：查看网站所有资源请求信息（HTTP报文信息）、加载时间
- Application：查看网站数据存储和资源文件
- Storage：信息存储

### JS 做客户端语言
> 按照JS语法，操作页面元素，操作浏览器里面的一些功能
- ECMAScript ：JS语法规范
- DOM：文档对象模型，提供一些JS属性和方法，操作页面中的DOM元素
- BOM：浏览器对象模型，提供一些JS属性和方法，操作浏览器

### JS中的变量 variable
> 变量：可变的值 用来存储和代表不同值的东西
```
// ES3
    var a =12
    a = 15
    console.log(a) //15
// ES6
    let b = 100
    b = 200

    const c = 1000
    c = 2000 //const 创建的特殊变量 不可修改 即常量

    // 创建函数
    functiong fn(){}
    // 创建类
    class A{}
    //模块导入
    import B from './b.js'
    //Symbol 创建唯一值
    let s1 = Symbol(100)
    let s2 = Symbol(100)
    s1 == s2 //false
```
### JS 中的命名规范
- 严格区分大小写
- 使用数字、字母、下划线、$、不能以数字开头
- 驼峰命名发：首字母小写，其余每个有意义单词的首字母大写，尽可能语义化
- 拒绝关键字和保留字


### JS 常用数据类型
- 基本数据类型
    + number（数字和NaN）、String、boolean、null空对象指针、undefined
- 引用数据类型
    + 对象数据类型object
        + {} 普通对象
        + [] 数组对象
        + /^[+-]?(\d|([1-9]\d+))(\.\d+)?$/ 正则对象
        + Math 数学函数对象
        + Date 对象
    + 函数数据类型function

### NaN
> not a number: 不是一个数
NaN != NaN
###isNaN
> 检测一个值是否为：非有效数字，基于Number() 把值转换为数字类型再检测，如果不是则返回true 反之返回false
> Number(12.5) // NaN
> Number([32]) //32
> Number([23,32])//NaN
> Number(true) // 1
> Number(false) // 0
> Number(null) // 0
> Number(undefined) // NaN
> isNaN(false) // false

### String : 字符串
> 单引号、双引号、反引号 包起来的
### 把其他类型转为字符串
- [val].toString()
- 字符串拼接 加法
### Boolean() 转换
> 0、NaN、''、null、undefined ：false ;其他都是true
### ! ：取反

### null / undefined
- 都表示没有
- null：意料之中 一般是开始不知道值，我们手动设置为null，后期再赋值；用null作为初始的空值，不占位置；设置为0 会再栈内存中有自己的存储空间
- undefined：意料之外 
