# Tampermonkey-Scripts
> 网页脚本收集
## 1.解除网页文字无法选中
1. 浏览器打开目标界面，按下F12

2. 在Console命令行中输入以下代码：
  ```javascript
var eles = document.getElementsByTagName('*');
for (var i = 0; i < eles.length; i++) {
    eles[i].style.userSelect = 'text';
}
```
3. 再按下F12退出命令模式，返回原界面，就可以选中文字了
## 2.实现网页内容可编辑
```javascript
document.body.contentEditable='true'
```
## 3.解除网页无法复制限制
```javascript
javascript: (function () {
  function R(a) {
    ona = "on" + a;
    if (window.addEventListener)
      window.addEventListener(
        a,
        function (e) {
          for (var n = e.originalTarget; n; n = n.parentNode) n[ona] = null;
        },
        true
      );
    window[ona] = null;
    document[ona] = null;
    if (document.body) document.body[ona] = null;
  }
  R("contextmenu");
  R("click");
  R("mousedown");
  R("mouseup");
  R("selectstart");
})();
```
