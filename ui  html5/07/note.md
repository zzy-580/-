# `HTML5`新特性 -- `Unit07`

# 1.`SVG`

## 1.1 什么是`SVG`?

`SVG(Scalable Vector Graphic)`，可缩放的矢量图形。`SVG`是基于`XML`的`2D`的图形格式。

## 1.2 `SVG`的使用方式

### · 直接通过`<img>`标签

示例代码如下：

```html

<img src="svg/logo.svg" width="180" height="80">

```

## · 通过`CSS`中的`background`属性

示例代码如下:

```css

#container{
    width: 900px;
    height: 550px;
    margin: 0 auto;
    border: 2px solid #f00;
    background: url(svg/logo.svg) no-repeat center center;
}

```

## ·  `<object>`标签

```html

<object data="URL地址" type="MIME类型">
	浏览器不支持该类型文件时的提示信息
</object>

```

> `SVG`文件的`MIME`类型是：`image/svg+xml`

## · `<embed>`标签

```html

<embed src="URL地址" type="MIME类型" width="宽度" height="高度">
	浏览器不支持该类型文件时的提示信息
</embed>

```

## · `<iframe>`标签

```html

<iframe src="URL地址" width="宽度" height="高度" scrolling="是否显示滚动条(yes|no|auto)">
    浏览器不支持该类型文件时的提示信息
</iframe>

```

## · `<svg>`标签

```html

<svg version="1.1" xmlns="http://www.w3.org/2000/svg" width="宽度" height="高度">
    ...
</svg>

```

> `xmlns`是`XML Namespace`的缩写，意为`XML`命名空间，其根本作用是为了解决标签名称冲突。

## 1.3 `svg`元素

## · 元素属性

`stroke-width`属性用于设置描边的宽度

`stroke`属性用于设置描边的颜色

### ·  `<line>`元素

`<line>`元素用于绘制线段，其语法结构是：

```html

<line x1="起点X轴" y1="起点Y轴" x2="终点X轴" y2="终点Y轴"></line>

```

### · `<polyline>`元素

`<polyline>`元素用于绘制折线，其语法结构是：

```html

<polyline points="x1,y1,x2,y2,...">

</polyline>

```

### · `<rect>`元素

`<rect>`元素用于绘制(圆角)矩形，其语法结构是：

```html

<rect 
      x="起点的X轴" y="起点的Y轴" 
      width="宽度" height="高度"
      rx="rx" ry="ry">
    
</rect>


```

### · `<a>`元素

`<a>`元素用于实现链接，其语法结构是：

```html

<a 
   xlink:href="目标文档URL" 
   xmlns:xlink="http://www.w3.org/1999/xlink">
    ...
</a>

```

http://www.zuohaotu.com/svg/

## 1.4 `SVG DOM API`

·  `document.createElementNS()`方法

`document.createElementNS()`方法用于创建指定命名空间内的元素，其语法结构是：

```javascript

Element document.createElementNS('命名空间','元素名称')

```

·  设置与获取元素属性

```javascript

Element.setAttribute(name,value)

Element.getAttribute(name)

```

· 添加/删除子元素

```

Node Node.appendChild(subNode)

Node.removeChild(subNode)

```

# 2.`ECharts`

## 2.1 概述

`ECharts`是百度推出的开源的数据可视化工具 --- 基于`Javascript`的图表库。

https://echarts.apache.org/zh/index.html

## 2.2 安装

· 浏览器

```shell

https://echarts.apache.org/zh/download.html

```

· `npm`

```shell

npm install --save echarts

```

## 2.3 基本使用

当在浏览器中引入外部的`JS`文件后，系统将自动暴露名称为`echarts`的对象

示例代码如下：

```html

<script src="scripts/echarts.min.js"></script>
<script>
console.log(echarts);
</script>

```

## 2.4 基本术语

· 实例

在一个网页中可以存在多个实例，每个实例中可以有多个图表类型（如折线、柱形等）![](assets/note/multiple-ec-instance.jpg)

·  系列

系列是实例中绘制的图表，一个实例中至少存在一个系列。

![](assets/note/series-all-a.jpg)

· 组件指图表的各个组件部分，如标题、X轴、Y轴等。

![](assets/note/components.jpg)

## 2.4 基本用法

A.在`HTML`页面中创建`DIV`元素，该`DIV` 将作为图表渲染容器出现，必须为该`DIV`元素设置明确的宽度和高度

B.书写`<script>`标签，并且调用`echarts`对象的`init()`方法以完成图表实例的创建，init()方法的语法结构建如下：

```javascript



```

C.通过**图表实例**的`setOption()`方法实现实例的配置

```javascript

instance.setOption({...})

```

## 2.5 配置项

### · `title`组件

`title`组件用于控制标题信息，其语法结构如下：

```javascript

title:{
    show:是否显示标题信息(true|false),
    text:'控制主标题文本信息',
    link:'控制主标题的链接URL地址',
    target:'控制打开主标题链接的窗口形式(blank|self)',
    //控制主标题文本的样式
    textStyle:{
        color:'主标题文本颜色',
        fontSize:主标题文本字号(整数),
        fontFamily:'主标题文本字体',
        fontWeight:'主标题文本的加粗(normal|bold)',
        fontStyle:'主标题文本的倾斜(normal|italic)'
    },
    subtext:'副标题的文本信息',
    sublink:'控制副标题的链接URL地址',
    subtarget:'控制打开副标题链接的窗口形式(blank|self)', 
    top:'title 组件离容器上侧的距离'(数字或字符串top|middle|bottom),
    right:
    bottom:
    left:'title 组件离容器左侧的距离'(数字或字符串left|center|right)
}

```

### ·`xAxis` 

`xAxis`属性用于控制X轴信息，其语法结构是：

```javascript

xAxis:{
	show:是否显示X轴(true|false),
    type:'X轴的类型(category|time)',
    data:该属性在type属性为category时必须存在,数组类型
}

```

### · `yAxis`

`yAxis`属性用于控制Y轴信息，参见X轴

### · `series`

`series`属性用于控制图表系列，其语法结构是：

```javascript

series:[
	{
		type:'系列的名称(line|bar|pie)',
		data:系列的数据(数组·)
	},
	{
		type:'系列的名称(line|bar|pie)',
		data:系列的数据(数组·)
	}
]


```

A.注册一个全新的邮箱

B.下载微信小程序开发者工具

https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html