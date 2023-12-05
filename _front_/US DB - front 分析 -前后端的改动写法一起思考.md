
mixin 其实也可以 相当于 本module的几个组件的 公用函数
见 FormatProfile  中的mixin 

对啊， 否则 一个组件没法调另一个组件的函数
不对， 为什么不直接放js文件呢。 啊， mixin就是js文件啊

---
### ⛳️ mixin可以定义prop， 相当于抽象基类的构造参数

不要光看有什么，要看为什么这么写这个mixin. 
主要是 background , 等等很多 to client的邮件 都要 去判断task的 属性 决定怎么渲染，或者共用advisor bios如nominal rate这样的取值逻辑

那么，相当于background , GA, MCK这些客户的定制组件 里都要引用这个mixin , 

<span style="background:#fff88f">ProfileIndex这个组件</span>
<font color="#ff0000">为什么把 有些东西放props里， 而不是放在要调用的函数的  参数里？？</font>



#可以用鼠标来navigation代码跳转返回 


