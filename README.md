# Tampermonkey-Scripts
> 网页脚本收集
## 1.解决网页中文字无法选中的问题
1. 浏览器打开目标界面，按下F12

2. 在Console命令行中输入以下代码：
  ```javascript
var eles = document.getElementsByTagName('*');
for (var i = 0; i < eles.length; i++) {
    eles[i].style.userSelect = 'text';
}
```
3. 再按下F12退出命令模式，返回原界面，就可以选中文字了
## 2.编辑整个网页
