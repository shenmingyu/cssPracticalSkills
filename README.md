# CSS实用小技巧记录

本仓库仅用于个人学习复习操作，其中样式完全个人完成，希望可以和大家共同进步！

本文件用于记录样式，方便查找。

[TOC]

## CSS实现水平/垂直/水平垂直居中

> 这里不考虑通过具体的元素宽高来进行计算后得到的居中位置，仅为使用固有的css属性来进行居中操作



下文中的HTML结构：

```html
<body style="background-color: #242424;width: 100vw;height: 100vh;">
  <div class="mediate" style="width: 100px;height: 100px;background-color: #00FFCC;">请把我居中</div>
```



### 水平居中

#### `margin`

```css
body {
  position: relative;
}

.mediate {
  margin: 0 auto;
  line-height: 100px;
  text-align: center;
}
```

#### `left`+`transform:translateX`

```css
body {
  position: relative;
}

.mediate {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  line-height: 100px;
  text-align: center;
}
```



### 垂直居中

#### `top`+`transform:translateY`

```css
body {
  position: relative;
}

.mediate {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  line-height: 100px;
  text-align: center;
}
```



#### `table-cell`+`text-align`+`vertical-align`

```css
body {
display: table-cell;
vertical-align: middle;
}

.mediate {
line-height: 100px;
text-align: center;
}
```



### 水平垂直居中

#### `flex`+`justify-content`+`align-items`

使用 `flex` 布局居中块元素以及内文本

`flex` 中的 `justify-content` 和 `align-items`

```css
body {
  display: flex;
  justify-content: center;
  align-items: center;
}

.mediate {
  display: flex;
  justify-content: center;
  align-items: center;
}
```



#### `grid`+`justify-self`+`align-self`

使用 `grid` 布局居中块元素以及内文本

`grid` 中的 `justify-self` 和 `align-self`

```css
body {
  display: grid;
}

.mediate {
  justify-self: center;
  align-self: center;
  line-height: 100px;
  text-align: center;
}
```



#### `top`+`left`+`transform:translate`

使用 `inlilne` 布局居中块元素以及内文本

`top` 和 `left` 以及 `transform: translate()`

```css
body {
  position: relative;
}

.mediate {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  line-height: 100px;
  text-align: center;
}
```

