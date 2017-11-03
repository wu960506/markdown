#css3复习

标签（空格分隔）： css

---

圆角
border-radius
```
radius:25px radius像素越大就越圆（‘%’同样可以表示）
border-radius:1px(左上) 2px（右上） 3px（左下） 4px（右下）
```
```
div
{
border:2px solid;
border-radius:25px;
border-radius:50%（圆）
}

```
阴影
box-shadow
```
box-shadow:hoffer(水平偏移左正右负) voffeset（上下偏移正下负上） blur（模糊值） spred（阴影延伸半径）color（颜色）  inset（默认：盒子内部）
```
box-shadow: 10px 10px 5px #888888;
[阴影链接网址][1]
边界图片
```
border-image：source（图片链接） slice（截取的长宽） width（实际宽度） repeat
```
border-image:url(“border.png”)  15 / 15px repeat  
背景图片
```
background-image
background-size(大小)
background-position（位置）
background-clip（背景剪裁属性是从指定位置开始绘制）
```

```
div
{
    background:url(img_flwr.gif);
    background-size:80px 60px;
    background-size:100% 100%;（充满内容区域）
    background-position:left（偏左）
     border: 10px（间距） dotted（形状） black（颜色）; 
    background-repeat:no-repeat;
}
```
***
###渐变

```
//线性渐变 方向参数可以省略，默认从底部往上渐变
div{
width:300px;
height:100px;
background:linear-gradient(135reg,red 0%,yellow 50%,blue 100%)
}
```
```
//径向渐变
//类型参数可以省略，默认是椭圆ellips，可以设置为圆circle
div{
width:300px;
height:100px;
 background: radial-gradient(red 5%, green 15%, blue 60%);
}
```
***
###转换2D
>translate()
rotate()
scale()
skew()
matrix()

rotate()方法，在一个给定度数顺时针旋转的元素。负值是允许的，这样是元素逆时针旋转。
```
div
{	
width:200px;
height:100px;
background-color:yellow;
transform:rotate(3deg);//旋转的度数
}
```
translate()方法，根据左(X轴)和顶部(Y轴)位置给定的参数，从当前元素位置移动
```
<style> 
div
{
	width:100px;
	height:75px;
	background-color:red;
	border:1px solid black;
}
//div移动的距离
div#div2
{
	transform:translate(50px,100px);
	//把元素从左侧移动 50 像素，从顶端移动 100 像素
	-ms-transform:translate(50px,100px); /* IE 9 */
	-webkit-transform:translate(500px,10px); /* Safari and Chrome */
}
</style>
</head>
<body>

<div>Hello. This is a DIV element.</div>

<div id="div2">Hello. This is a DIV element.</div>

</body>
</html>
```
scale()方法，该元素增加或减少的大小，取决于宽度（X轴）和高度（Y轴）的参数：(放大缩小)
```
div {
    margin: 150px;
    width: 200px;
    height: 100px;
    background-color: yellow;
    border: 1px solid black;
    transform: scale(2,3);//div 元素的宽度是原始大小的两倍，高度是原始大小的三倍
}
```
skew() 方法
```
包含两个参数值，分别表示X轴和Y轴倾斜的角度，如果第二个参数为空，则默认为0，参数为负表示向相反方向倾斜。
skewX(<angle>);表示只在X轴(水平方向)倾斜。
skewY(<angle>);表示只在Y轴(垂直方向)倾斜。
```
```
<html>
<head>
<meta charset="utf-8"> 
<style> 
div
{
	width:100px;
	height:75px;
	background-color:red;
	border:1px solid black;
}
div#div2
{
	transform:skew(300deg,20deg);//水平方向 垂直方向
}
</style>
</head>
<body>

<div>Hello. This is a DIV element.</div>

<div id="div2">Hello. This is a DIV element.</div>

</body>
</html>
```
matrix() 方法
```
matrix()方法和2D变换方法合并成一个。
matrix 方法有六个参数，包含旋转，缩放，移动（平移）和倾斜功能。
```
```
<html>
<head>
<meta charset="utf-8"> 
<style> 
div
{
	width:100px;
	height:75px;
	background-color:red;
	border:1px solid black;
}
div#div2
{
		transform:matrix(0.866,0.5,-0.5,0.866,0,0);
}
</style>
</head>
<body>

<div>Hello. This is a DIV element.</div>

<div id="div2">Hello. This is a DIV element.</div>

</body>
</html>
```
***
####3D转换
rotateX()方法，围绕其在一个给定度数X轴旋转的元素。
rotateY()方法，围绕其在一个给定度数X轴旋转的元素。
```
<html>
<head>
<meta charset="utf-8"> 
<style> 
div
{
	width:100px;
	height:75px;
	background-color:red;
	border:1px solid black;
}
div#div2
{
     transform:scale3d(x,y,z)//转换
     transform:translate3d(x,y,z)//转化
     transform:rotate3d(-10,10,2,70deg)//旋转
    //transform:perspective(20px)      
}
</style>
</head>
<body>
<div>Hello. This is a DIV element.</div>
<div id="div2">Hello. This is a DIV element.</div>
</body>
</html>
```
***
####过渡
transition	简写属性，用于在一个属性中设置四个过渡属性。	

transition-property	规定应用过渡的 CSS 属性的名称。	

transition-duration	定义过渡效果花费的时间。默认是 0。	

transition-timing-function	规定过渡效果的时间曲线。默认是 "ease"。	

transition-delay	规定过渡效果何时开始。默认是 0。	

下面的两个例子设置所有过渡属性：
```
transition:width 2s;
transition:height 2s;
transition:width 1s linear 2s;//过渡效果延迟2秒
```
应用于宽高属性的过渡效果，时长为 2 秒：
```
<style> 
div {
    width: 100px;
    height: 100px;
    background: red;
    transition: width 2s, height 2s, transform 2s;
}

div:hover {
    width: 200px;
    height: 200px;
    transform: rotate(180deg);
}
</style>
<div></div>

```
***
####动画
```
当在 @keyframes 创建动画，把它绑定到一个选择器，否则动画不会有任何效果。
规定动画的名称
规定动画的时长 
```
```
//渐变颜色
<html>
<head>
<meta charset="utf-8"> 
<style> 
div
{
	width:100px;
	height:100px;
	background:red;
	animation:myfirst 5s;
	//动画名称 myfirst, 时长 5s
}

@keyframes myfirst
{
	from {background:red;}
	to {background:yellow;}
}
</style>
</head>
<body>
<div></div>
</body>
</html>
```
```
请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%。
0% 是动画的开始，100% 是动画的完成。
```
```
div
{
	width:100px;
	height:100px;
	background:red;
	position:relative;
	animation:myfirst 5s linear 2s infinite alternate;
}
@keyframes myfirst
{
	0%   {background:red; left:0px; top:0px;}
	25%  {background:yellow; left:200px; top:0px;}
	50%  {background:blue; left:200px; top:200px;}
	75%  {background:green; left:0px; top:200px;}
	100% {background:red; left:0px; top:0px;}
}
```
  [1]: http://www.cssmatic.com/box-shadow