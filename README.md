# 烟花特效

## 修改如下片段，修改固定的烟花爆炸的位置及爆炸后显示的文字
```JavaScript
//电脑浏览样式,浏览器宽度大于长度
var array;
if (window.innerWidth > window.innerHeight) {
    array = [{"text": "张", "x": window.innerWidth / 11, "y": window.innerHeight * 3 / 10},
        {"text": "景", "x": window.innerWidth * 2 / 11, "y": window.innerHeight * 4 / 10},
        {"text": "秀", "x": window.innerWidth * 3 / 11, "y": window.innerHeight * 7 / 20},
        {"text": "大", "x": window.innerWidth *4 / 11, "y": window.innerHeight * 3 / 11},
        {"text": "小", "x": window.innerWidth * 5 / 11, "y": window.innerHeight * 3 / 10},
        {"text": "姐", "x": window.innerWidth * 6 / 11, "y": window.innerHeight / 3},
        {"text": "生", "x": window.innerWidth * 7 / 11, "y": window.innerHeight * 3 / 11},
        {"text": "日", "x": window.innerWidth * 8 / 11, "y": window.innerHeight * 4 / 11},
        {"text": "快", "x": window.innerWidth * 9 / 11, "y": window.innerHeight / 3},
        {"text": "乐", "x": window.innerWidth * 10 / 11, "y": window.innerHeight / 3}];
}
//手机浏览样式
else {
    array = [{"text": "张", "x": window.innerWidth / 4, "y": window.innerHeight / 3},
        {"text": "景", "x": window.innerWidth / 2, "y": window.innerHeight / 3},
        {"text": "秀", "x": window.innerWidth * 3 / 4, "y": window.innerHeight / 3},
        {"text": "大", "x": window.innerWidth / 4, "y": window.innerHeight  / 2},
        {"text": "小", "x": window.innerWidth * 2 / 4, "y": window.innerHeight / 2},
        {"text": "姐", "x": window.innerWidth * 3 / 4, "y": window.innerHeight / 2},
        {"text": "生", "x": window.innerWidth / 5, "y": window.innerHeight * 2 / 3},
        {"text": "日", "x": window.innerWidth * 2 / 5, "y": window.innerHeight * 2 / 3},
        {"text": "快", "x": window.innerWidth * 3 / 5, "y": window.innerHeight * 2 / 3},
        {"text": "乐", "x": window.innerWidth * 4 / 5, "y": window.innerHeight * 2 / 3}];
}
```

## 修改如下片段，修改鼠标点击发射的烟花爆炸后的文字（当前为空字符）
```javascript
//鼠标点击发射烟花
document.addEventListener("mousedown", function (e) {
    var x = e.clientX;
    var y = e.clientY;
    createLaunchFireworks(x, window.innerHeight, x, y, "");
});
```
## 修改如下片段，修改随机发射的烟花的频率（当前为0.5秒）及爆炸后的文字（当前为空字符）
```javascript
//每0.5秒
setInterval(function () {
    var x = Math.random() * canvas.width;
    var y = Math.random() * canvas.height;
    if (y < window.innerHeight / 5 || y > window.innerHeight * 2 / 5)
        createLaunchFireworks(x, window.innerHeight, x, y, "");
}, 500);
```