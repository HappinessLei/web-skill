## 移动端常见问题解决
- [解决安卓手机软键盘挡住input输入框的问题](#jump1)
- [解决安卓手机软键盘弹出挤压背景页面导致变形问题](#jump2)
### <span id="jump1">解决安卓手机软键盘挡住input输入框的问题</span>
```js
if (/Android/gi.test(navigator.userAgent)) {
    window.addEventListener('resize', function () {
        if (document.activeElement.tagName == 'INPUT' || document.activeElement.tagName == 'TEXTAREA') {
            window.setTimeout(function () {
                document.activeElement.scrollIntoViewIfNeeded();
            }, 0);
        }
    })
}
```
监听窗口变化的时候，判断当前激活的元素是input或是textarea就让元素滚动到视图可见区域。

### <span id="jump2">解决安卓手机软键盘弹出挤压背景页面导致变形问题</span>
原因是苹果机软键盘和页面是分层上下覆盖的，而安卓机中相当于同层且不是浮动上下分层导致页面被软键盘顶上来。   
解决方法就是把当前页面的body内容层固定好：
```js
$('body').height($('body')[0].clientHeight);
```
