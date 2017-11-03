# javascript

标签（空格分隔）： 事件

---

onchange()事件常结合对输入字段的验证来使用
```
//文本框的字体同意变成大写
<input type="text" id="fame" onchange="my()">
  function my() {
        var fame= document.getElementById('fame');
        fame.value=fame.value.toUpperCase()
    }
```
onmouseover 和 onmouseout 事件可用于在用户的鼠标移至 HTML 元素上方或移出元素时触发函数。
```
<div id="d1" onmouseout="_this(this)" onmousemove="_ths(this)">你好</div>
function _ths(i) {
    i.innerHTML='知道'
}
function _this(i) {
    i.innerHTML='你好'
}
```
```
<div id="d1">你好</div>
function _this() {
    d1.innerHTML='不好'
}
function _thi() {
    d1.innerHTML='你好'
}
    window.onload =function() {
       var d1= document.getElementById('d1');
       d1.onmousemove=_this
       d1.onmouseout=_thi
    }
```
onfocus() onblur()获得失去焦点
```
<input type="text" onfocus="myFunction(this)" onblur="myFunctio(this)">
function myFunction(x)
{
x.style.background="yellow";
}
function myFunctio(x)
{
x.style.background="red";
}
```
onclick()点击事件
```
<input id="btn02" type="button" value="点我" onclick="abc()">
function abc() {
            alert('我是事件')
        }
```
```
   <input id="btn03" type="button" value="点我" >
       function show01() {
            alert('我是动态绑定事件')
        }
    window.onload=function () {
            var show = document.getElementById('btn03');
            show.onclick=show01;
            }
```





