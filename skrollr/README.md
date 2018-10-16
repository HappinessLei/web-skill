## skrollr
skrollr是一个原生的JavaScript视差滚动插件库，没有使用jQuery等第三方框架，能够兼容移动设备的Android + iOS系统和普通的PC浏览器，代码量极其少，压缩版本的插件只有12K，设计友好和方便，没有什么JavaScript高级的使用，只是简单的CSS和HTML。
## 使用方法
### html
```
<div id="container">
    <div id="box" 
         data-0="top:0px;left:0px" 
         data-500="top:50px;left:200px"
         data1000="top:100px;left:200px"
         >
    </div>
</div>
```
### css
```
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
```
<script type= "text/javascript"  src= "skrollr.min.js" ></script> 
<script type= "text/javascript" > 
  var  s  =  skrollr . init (); //初始化
</script> 
</body>
```
