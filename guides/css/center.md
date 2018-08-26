# CSS 与居中

点击查看此文件关联 [ Demo 文件](../../demos/css/center.html)

在 CSS 中居中是一个常见的问题，也是一个基本问题。既然是常见的基本问题，那真是有必要加以研究和加以总结。

## 行内元素的居中

### 使用 text-align:center 实现行内元素的水平居中

`text-align:center` 估计是最古老 CSS 居中技术了。
适用于文本，`span`,`a`等行内元素。

### 使用 line-height 实现行内元素实现垂直居中

这一技巧也是适用于行内元素。
具体的实现是将 `line-height` 设置成跟元素高度一致来实现行内元素的垂直居中。
详情见示例中 `.primary-button` 类的 CSS。

## 块元素居中技术

### 块元素水平居中经典技术：margin 与 auto

以前块级元素居中常用的技术便是通过如下的设置来实现块级元素的水平居中.(此法不适用内联块级元素)

```css
div {
  width: 720px; /*指定块元素的宽度*/
  margin: 0 auto; /*指定自动计算左右外边距*/
}
```

### 绝对定位+ margin:auto 实现水平居中，垂直居中布局

布局实例： http://jsfiddle.net/01527xba/31/

1. 为了启用绝对定位，先将父元素设置为相当定位。

2. 元素设置类似如下属性

```
  margin:auto;
  position: absolute;
  left: 0;
  top: 0;
  bottom:0;
  right: 0;
  width:160px;
  max-height:50px;
```

### 块元素水平居中新手法: transform

可以通过如下属性实现块级元素及内联块级元素的水平居中。

```css
margin-left: 50%;
transform: translateX(-50%);
```

值得说明的是，此方法无法实现垂直居中，因为`margin-top:50%` 相当于 `margin-top: 最近的块元素容器的宽度` ,所以`margin` 中的百分比的计算方式限制其无法应用于垂直居中.

## 居中大法: flex

flex 布局技术的出现，解决了 CSS 没有正式的居中布局技术的尴尬。
以 `flex-direction` 的默认设置 `flex-direction:row` 为例。
`justify-content:center` 可实现水平居中对齐，`align-items:center` 可实现垂直居中对齐。
flex 作为通用的布局技术，居中只是其中的一点点组合特性。

值得注意的是，除了使用 flex, CSS 中没有其他的通用的垂直居中的技术。
