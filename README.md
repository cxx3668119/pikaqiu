# 会动的皮卡丘

## 皮卡丘制作


## 制作过程

### HTML && CSS 部分

参考博客：[皮卡丘制作](https://github.com/Jsmond2016/make-a-pikachu/blob/master/README.md)

###  打字机动画

主要是用 js 控制css，写入 style 样式中

使用 setInterval 实现等间隔时间做相同的动作，使用  substring(0,n) 实现字符串切割

在展示页面逐步展示整个皮卡丘 的制作过程。

### 调速

因为 `setInterval(()=>{},n)` 的 n 只会读取一次，意味着只有一次赋值的机会，无法实现调速；

巧妙地使用 `setTimeout(()=>{},time)` 间隔时间递归调用可以等价的实现和 `setInterval()` 一样的功能，同时，它的每一次递归都会重新读取一次时间参数 `time` ，从而实现调速功能 。

```
let n=0
let id = setInterval(()=>{
  n+=1
  console.log(n)
  if(n>=10){
    window.clearInterval(id)
  }
},10)

//使用setTimeout实现同等功能

let m = 0
let id2 = setTimeout(function fn(){
  m+=1
  console.log(m)
  if(m <= 10){
    setTimeout(fn,10)
  }
},10)

```



