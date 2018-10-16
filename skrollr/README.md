## 小程序开发学习总结

#### 1、如何创建新页面
    答：app.json中，pages数组下创建新的路径如“pages/文件夹名/文件名” 这样会自动在项目的pages文件夹下创建起的文件夹名，
    此文件夹下也会自动创建.js,.json,.wxml,.wxss四个文件，这四个文件是自动关联的，wxml文件就是我们创建的新页面。
#### 2、如何修改tabbar选中后字体的颜色
    答：app.json中，tabbar选项，添加selectedColor选项
#### 3、Canvas绘图以及分享截图，正式测试时，图片不显示问题
    答：需要使用wx.downloadFile()方法将图片缓存到本地
#### 4、授权不自动弹出授权窗口问题
    答：新版本不再支持自动弹出授权窗口，需要手动按钮触发，以示友好交互
#### 5、wx:if使用时，如果内部嵌套了label标签，使用<view wx:else></view>加载时候，将会出现小黑块。
    答：解决方法wx:else都换用wx:elif
#### 6、列表页跳转接收参数的内容页（带有参数）
    答：第一种：使用WXML<navigator url=””></navigator>标签
        第二种：wx.navigateTo({
 	                url: 'test?id=1'
                })
    建议使用第一种(如下图)，因为html，逻辑相对简单一些，传多个参数时，使用js时，数据接收是个问题。
