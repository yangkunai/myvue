### 指令

v-model  双向数据绑定 只要input可以用  原理是属性绑定加上事件绑定   修饰符 .trim去除两边空白  .lazy 失去焦点数据才会收到影响

v-pre 指显示原始信息  

v-bind 用于将属性与数据绑定  简写:

v-if 值是一个布尔值  ture渲染,否则不渲染

v-show 用于显示与隐藏 改变displan的属性  和v-if的区别一个是删除没有,,一个是隐藏

v-else 需要与v-if 和v-else-if使用

v-else-if 值是一个布尔值,需要与v-fi使用

v-for 循环 三个参数第一个(item,index)in  属性名字

v-on 可以绑定js语句,可以绑定函数

### 事件修饰符

stop 阻止冒泡  

prevent 阻止默认行为

### 事件函数

methdos  定义对象方法

调用方式

直接绑定函数名称  调用函数

参数传递  普通参数和事件对象  $event

### mountedc

生命周期 当刷新页面后并生成vue实列后会执行函数