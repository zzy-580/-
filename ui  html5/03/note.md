# `HTML5`新特性 -- `Unit03`

# 1.`canvas`

· `textAlign`属性

`textAlign` 属性用于设置文本的水平对齐方式，其语法结构是：

```javascript

ctx.textAlign = 'left|center|right'

```

·  `clearRect()`方法

`clearRect()`方法用于擦除指定的矩形区域，其语法结构是：

```javascript

ctx.clearRect(x,y,width,height)

```

· 路径

路径(`path`)将预先设置的坐标点顺序连接形成的图形。

路径的绘制步骤：

A.通过`ctx.beginPath()`方法开始新的路径

B.通过`ctx.moveTo()`方法指定路径的起点坐标

C.绘制基本路径内容(如`lineTo`()方法用于绘制线段等)

D.通过`stroke()`或`fill()`方法完成路径的绘制

·  `beginPath()`方法

`beginPath()`方法用于新始一个新的路径，其语法结构是：

```javascript

ctx.beginPath()

```

·  `moveTo()`方法

`moveTo()`方法用于指定路径的起点，其语法结构是：

```javascript

ctx.moveTo(x,y)

```

· `lineTo()`方法 

`lineTo()`方法用于绘制线段，其语法结构是：

```javascript

ctx.lineTo(x,y)

```

· `arc()`方法

`arc()`方法用于绘制圆弧路径，其语法结构是：

```javascript

ctx.arc(x,y,radius,start_angle,end_angle)

```

> 圆弧的起点和终点用弧度表示。
>
> 弧度的计算公式为：角度 * `Math.PI` / `180`

· `stroke()`方法

`stroke()`方法用于根据当前的描边样式来绘制路径，其语法结构是:

```javascript

ctx.stroke()

```

# 2.`window`对象

· `requestAnimationFrame()`方法
`requestAnimationFrame()`方法用于在浏览器中定时循环执行一个操作。其优点是：

A.该方法充利用显示器的刷新频率，不会出现卡顿、丢帧的现象；

B.如果当前选项卡没有被激话的话，动画将自动停止，以节省计算机资源

`requestAnimationFrame()`方法的语法结构是：

```javascript

variable = window.requestAnimationFrame(callback)

```

· `cancelAnimationFrame()`方法

`cancelAnimationFrame()`方法用于清理由`requestAnimationFrame()`方法返回的`requestId`。其语法结构是：

```javascript

window.cancelAnimationFrame(requestId)

```

