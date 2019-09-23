### js由什么构成：
- 逻辑处理：ECMAscript 
- DOM操作：页面操作
- 浏览器BOM：浏览器的信息

## 给参数默认值
```
   // 给默认值 方法1
     if (time == undefined) {
         time = 7
     }
    // 给默认值 方法2
    time = time || 2

```
### 动态参数
```
    // 动态参数
function add() {
    var sum = 0
    for (var i = 0; i < arguments.length; i++) {
        sum += arguments[i]
    }
    return sum
}

var res = add(3,5,2,5,1)
```

### 预解析
- 浏览器全篇快速扫描
+ 变量预先解析
```
console.log(y)                  //y is not defined
function a(){
    var y = 0;
    y = 12
    console.log(y)
}
```

## 闭包：解决变量的私有化问题 有全局变量的生命周期 又可以私有化
```
// 闭包
function add() {
    var counter = 0                 // 局部变量
    //写法1
    plus = function () {            //plus属于全局函数
        counter++                   // 局部变量全局化 全局变量的生命周期 
        console.log(counter)
    }

      //写法2
    /* function plus() {            //plus属于全局函数
        counter++                   // 局部变量全局化 全局变量的生命周期 
        console.log(counter)
    }
    return plus */

}
//方法1调用方式
add()
plus()
//方法2调用方式
add()()
//或者
var plus = add()
plus()

//console.log(counter)//counter is not defined

                                //匿名函数写法 函数立即执行
var plus = (function() {
    var counter = 0             // 局部变量
    return function() {         //plus属于全局函数
        counter++               // 局部变量全局化 全局变量的生命周期 
        console.log(counter)
    }
})()

plus()
```

### OS 之 浏览器加载页面
1.输入网址 浏览器 把域名发给 DNS服务器
2.DNS 将 域名 转换为 ip地址
3.浏览器收到 ip地址 缓存在本地
4.浏览器 向服务器请求 http协议
5.服务器收到请求 并处理后返回

### 浏览器：多线程
- js引擎
- UI渲染
- 事件线程
- 发起请求的线程
- 定时器的线程

### js 单线程（编程方便） 类似银行排队 下面是js时间线
- 第一阶段：载入阶段 loading
+ 1.获取页面内容 获取.html内容 解析
+ 2.DOM树 ：html -》 head —》 meta title script
+ 3.同步：js解释器 对下载的脚本进行解析 执行
+ 4.继续生成 DOM树
+ 5.解析完成
+ 6.渲染 下载图片等文件
+ 7.载入阶段结束
- 第二阶段：事件阶段

### DOM BOM
- window对象 -》全局对象 全局方法

### DOM 文档对象模型
- document 节点 -》 标签节点、元素节点 -》 文本节点
- 常用查找节点方式：id、class、标签
+ 注意：id -》 节点；TagName、ClassName -》 数组
+ id 只能通过document获取；tag、class可以在任意节点上使用
- 创建节点：
```
var div1 = document.getElementById('div1')                   //添加到DOM树
var p = document.creatElement('p')                           //创建一个p标签
var p1txt = document.createTextNode('我是p标签里面的字')        //添加一个文本节点
p.appendChild(p1txt)
div1.appendChild(p)                                           //添加节点
```
- 删除节点 
```
//删除div1里面的子div2
 var div2 = document.getElementById('div2')
 div1.removeChild(div2)
 div2.parentNode.removeChild(div2)          // 自己干掉自己
```

- 操作节点的属性、内容
```
var img1 = doucumentById('img1')
img1.style.color='pink'
img1.getAttribute('属性名')                   //获取属性
img1.setAttribute('属性名','修改后的属性值')    //修改属性
img1.removeAttribute('属性名')              //删除属性

var p1 = document.getElementById('p1')
p1.innerHTML = '这是innerHTML<a href='www.baidu.com'>this is a</a>' //可以往里面添加标签
p1.textContent = '这个是纯文本'//往里面添加标签再页面上也是文本
```

### 数据结构
- 线性：单链表 循环链表 队列 栈 数组
- 树形：二叉树 平衡图 红黑树
- 网状：有向图 无向图 -》 寻路算法

### BOM 弹窗
- 1.alert('弹窗')
- confirm('有确定和取消按钮的弹窗')     //有两个参数，第二个参数是返回值的默认值，选填 
- prompt('有输入框的弹窗')

### window.location 对象
- url 各个部分
```
host: "www.baidu.com"
hostname: "www.baidu.com"
href: "https://www.baidu.com/"
origin: "https://www.baidu.com"
pathname: "/"
port: ""
protocol: "https:"
location.toString()
location.reload()                       //刷新页面
location.replace('http://www.xxx.com')  //跳转页面
```


### BOM 浏览器前进、后退
```
history.back()      //后退
history.forword()   //前进
history.go(-1)      //后退一页
```
-

### BOM 获取浏览器版本、信息
- navigator.userAgent

### BOM 获取浏览器屏幕的信息
- screen

### BOM  计时器
- 循环执行：var sil = setInterval(函数名,时间) 
+ 停掉：clearInterval(sil)
- 一次执行：var sil = setTimeout(函数名,时间)
+ clearTimeout(sil)
```
var n = 0

function add() {
    console.log('n = ' + ++n)
}
var sil = setInterval(add, 1000);

function end() {
    console.log('setTimeout claerInterval')
    clearInterval(sil)
}

setTimeout(end, 5000);
//每一秒n+1 然后打印n的值 五秒后 返回setTimeout claerInterval
```
### 事件
- 方式1:html属性
+ 属性名：on+事件名字 （eg：onclick）
+ <div id> = 'div1' onclick ='ev()'></div> 
+ 或者 div1.onclick = ev
- 方式2:通过调用方式 添加监听事件
```
div1.addEventListener(事件类型click,函数ev,选填:处理方式(默认冒泡false/捕获true))
eg:div1.addEventListener('click',ev)
div1.removeEventListener('click',ev)        //删掉ev方法
//注意:ie8 以下不支持addEventListener和removeEventListener ，提供了attachEvent() 和 detachEvent()

<div id="div1">div1</div>
    <script>
        var div1 = document.getElementById('div1')
        div1.addEventListener('click', add)

        function add(event) {
             var event = event|| window.event //兼容ie8
            console.log(event)
            // event :事件对象 提供事件详细信息 具体发生事件的元素、鼠标位置、点击的状态...
            // MouseEvent {isTrusted: true, screenX: 79, screenY: 238, clientX: 23, clientY: 22, …}

             // 取消默认操作 页面局部刷新 不弹开新的窗口
            event.preventDefault() //方式1
            // return false // 方式2 ：这种方式只针对 外部调用方式为：a1.onclick = add 
            //ie 8: event.returnValue = false
        }
         /* 
        screenX Y:基于屏幕的左上角      //screenX：1950,screenY:120
        clientX Y：基于浏览器的左上角   //clientX:21,clientY:18
        */
    </script>
    //
```
