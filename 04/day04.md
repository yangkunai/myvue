#### promise

主要是解决函数嵌套异步的问题  ,Promise是一个构造函数，自己身上有all、reject、resolve这几个方法，原型上有then、catch等方法。这么说用Promise new出来的对象肯定就有then、catch方法.

创建一个:

```

```



Promise的构造函数接收一个参数，是函数，并且传入两个参数：resolve，reject，分别表示异步操作执行成功后的回调函数和异步操作执行失败后的回调函数

 .then方法  then里面的函数就跟我们平时的回调函数一个意思，能够在runAsync这个异步任务执行完成之后被执行。这就是Promise的作用了，简单来讲，就是能把原来的回调写法分离出来，在异步操作执行完后，用链式调用的方式执行回调函数  

Promise的优势在于，可以在then方法中继续写Promise对象并返回，然后继续调用then来进行回调操作。



catch 效果和写在then的第二个参数里面一样。不过它还有另外一个作用：在执行resolve的回调（也就是上面then中的第一个参数）时，如果抛出异常了（代码出错了），那么并不会报错卡死js，而是会进到这个catch方法中

```
getNumber()
.then(function(data){
    console.log('resolved');
    console.log(data);
    console.log(somedata); //此处的somedata未定义
})
.catch(function(reason){
    console.log('rejected');
    console.log(reason);
});
```

在resolve的回调中，我们console.log(somedata);而somedata这个变量是没有被定义的。如果我们不用Promise，代码运行到这里就直接在控制台报错了，不往下运行了。但是在这里，会得到这样的结果：

![img](https://images2015.cnblogs.com/blog/520134/201603/520134-20160311004747147-1508291069.png)

 

也就是说进到catch方法里面去了，而且把错误原因传到了reason参数中。即便是有错误的代码也不会报错了，这与我们的try/catch语句有相同的功能。

axios

​    async fn() {

​            const res = await axios.get('http://192.168.69.40:3000/a3');

​            const res2 = await axios.get('http://192.168.69.40:3000/a2');

​            const res1 = await axios.get('http://192.168.69.40:3000/a1');

​            this.msg = res.data;

​          },