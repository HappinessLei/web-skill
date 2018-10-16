## skrollr
skrollr是一个原生的JavaScript视差滚动插件库，没有使用jQuery等第三方框架，能够兼容移动设备的Android + iOS系统和普通的PC浏览器，代码量极其少，压缩版本的插件只有12K，设计友好和方便，没有什么JavaScript高级的使用，只是简单的CSS和HTML。
## 使用方法
### html
```html
<div id="container">
    <div id="box" 
         data-0="top:0px;left:0px;background-color:rgb(0,0,255)" 
         data-500="top:50px;left:200px;background-color:rgb(0,255,255)"
         data1000="top:100px;left:200px;background-color:rgb(0,0,255)"
         >
    </div>
</div>
```
### css
```css
*{
    margin: 0;
    padding: 0;
}
html,body{
  width: 100%;
  height: 100%;
  background: #fff;
}
#container {
  width: 100%;
  height: 100%;
  position: relative;
}

#box {
  width: 100px;
  height:100px;
  position: absolute;
}
```
### js
```js
<script type="text/javascript" src="skrollr.min.js" ></script> 
<script type="text/javascript" > 
  var s = skrollr.init(); //初始化
</script> 
</body>
```
## 语法解析
* `data-0`：Skrollr使用data来定义关键帧，0代表SkrollrTop的值：画面中有两个关键帧分别是`data-0`与`data-500`，而里面的值，则分别用CSS来定义它的过渡效果  
### 注意
* 默认情况下skrollr认为页面可以滚动到500px急即使你的页面长度不够500，如果想阻止这种情况发生只要使用forceHeight属性就可以默认是true，将其设为false就可以阻止。
* 单位取值，skrollr规定所有单位数值，必须是相同的单位，即使0，也需要添加单位，并且px和%不能同时使用，动画不可能从5%到100px过渡。
* 数值取值，当数值由多个数组成时，如`margin:0 0 0 0`，过渡值必须使用相同数量的值。如`margin:0px 0px 0px 0px`到`margin:0px 100px 50px 3px`是成立的，如果是`margin:10px`到`margin:5px 10px`或`margin:0px 5px`到`margin:5px 10px 15px 5px`这样是不起作用的。
* 颜色取值，最好不要使用#00f或者#0000ff，必须使用`rgb()`，`rgba()`，`hsl()`和`hsla()`。（可以使用[skrollr-colors](https://github.com/FezVrasta/skrollr-colors)插件）
* 颜色来做动画时一样，必须使用相同的颜色取值方法，比如`rgb()`到`rgb()`过渡，但不能`rgb()`到`hsl()`过渡。
* CSS过渡动画时，转换的顺序也要必须一致，才能起作用，如`rotate(0deg) scale(1)`到`rotate(1000deg) scale(5)`转换。
* 针对IE9以下的浏览器，可以引入`skrollr.ie.min.js`。
  
关于skrollr的更多api详情，请移步[官方文档](https://github.com/Prinzhorn/skrollr)
