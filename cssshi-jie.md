# CSS世界

# 1. 概述

## 1.4 CSS世界的开启从IE8开始

本书说的CSS世界是CSS2.1 世界, 并不包括CSS3.0

现在前端技术发展迅猛，加上气氛略显浮躁, 有必要让广大前端开发者静下来认识CSS2.1的世界

否则面对CSS3的真正到来, 只能是浅水游弋, 搬砖打杂

## 1.5 table自己的世界

table比css还要老

流的CSS世界并不包括table, table有自己的世界

本书并不阐述

# 2. 需提前了解的术语和概念

# 3. 流、元素与基本尺寸

## 3.1 块级元素

常见的块级元素有`<div>` `<li>` `<table>`等

需要注意的是 `块级元素`和`disaply为block`的元素不是一个概念

例如 `<li>`元素默认的display为list-item, `<table>`的默认display为`table`

但是他们都是`块级元素`

因为符合块级元素的基本特征: 在一个水平流上智能单独显示一个元素, 多个块级元素则换行显示

正是因为`块级元素`具有换行特性，因此理论上它都可以配合clear属性来清除浮动带来的影响

```css
.clear:after{
    content: '';
    display: block;
    clear: both;
}
```

`tips: IE浏览器包括(IE11)不支持伪元素的display设置为list-item`

> 为什么list-tiem会出现项目符号

一开始只有块级盒子和内联盒子

块级盒子负责 结构

内联盒子负责 内容

突然来了一个list-item, 浏览器不知道怎么归类. 

就叫做`附加盒子`

也就是所有块级元素都有一个主块级盒子, 除此之外还有一个list-tem'附加盒子'

而IE浏览器是因为伪元素不支持list-item或许就是无法创建这个`标记盒子`导致的

之后...

又来了一个display: 'inline-block'

这个就又无法解释了

后来造物主认为每个元素都有两个盒子: `外在盒子`和`内在盒子(容器盒子)`

外在盒子负责元素是可以一行显示还是换行显示

内在盒子负责 宽高 内容显示

现在就比较好理解为什么inline-block即可图文一行展示又可以设置width/height了吧

实际上

display: 'block'是display: block-block

display: table是display: block-table



