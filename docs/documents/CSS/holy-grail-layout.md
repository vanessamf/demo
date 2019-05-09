# 圣杯布局


## 题目要求：##

?>针对如下DOM结构，编写CSS，实现三栏水平布局，其中left、right分别位于左右两侧，left宽度为200px，right宽度为180px，main处在中间，宽度自适应。

## 实现效果 ##

?> <a class="btn btn-success" href="https://vanessamf.github.io/demos/layout/index3.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##
### <span id="item_1" class="inline-toc">1.</span> 结构 ###
```html
<div class="container">
    <div class="middle">
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
        <p>sdfsdfsdf</p>
    </div>
    <div class="left"></div>
    <div class="right"></div>
</div>
```
### <span id="item_1" class="inline-toc">2.</span> 容器设置padding留出左右宽度 ###
```css
.container {
    padding-left: 200px;
    padding-right: 180px;
}
```
### <span id="item_1" class="inline-toc">3.</span> 3块添加宽度并浮动显示 ###

```css
.middle {
    float: left;
    width: 100%;
    height: 300px;
    background-color: rgba(255, 0, 0, .5);
}
.left{
    float:left;
    width:200px;
    height: 300px;
    background-color: rgba(0, 255, 0, .5);
}
.right{
    float:left;
    width:180px;
    height: 300px;
    background-color: rgba(0, 0, 255, .5);
}
```
### <span id="item_1" class="inline-toc">4.</span> 左侧与容器内容左侧对齐 ###
```css
.left{
    margin-left:-100%;
}
```
### <span id="item_1" class="inline-toc">5.</span> 使用相对定位，其偏移量恰好是左列的宽度。 ###
```css
.left{
    position:relative;
    left:-200px;
}
```
### <span id="item_1" class="inline-toc">6.</span> 右侧与容器内容右侧对齐 ###
```css
.right{
    margin-left:-180px;
}
```
### <span id="item_1" class="inline-toc">7.</span> 右侧与容器内容右侧对齐 ###
```css
.right{
    position:relative;
    right:-180px;
}
```

### <span id="item_1" class="inline-toc">8.</span> 6,7或者写成 ###
```css
.right{
    margin-right:-180px;
}
```

还需要考虑最后一步，那就是页面的最小宽度：要想保证该布局效果正常显示，由于两侧都具有固定的宽度，所以需要给定页面一个最小的宽度，但这并不只是简单的200+180=380px。回想之前left使用了position: relative，所以就意味着在middle开始的区域，还存在着一个left的宽度。所以页面的最小宽度应该设置为200+180+200=580px：
```css
body {
  min-width: 580px;
}
```

### <span id="item_1" class="inline-toc">9.</span> 完整代码 ###

```css
body {
    min-width: 580px;
}

.container {
    padding-left: 200px;
    padding-right: 180px;
}

.middle {
    float: left;
    width: 100%;
    height: 300px;
    background-color: rgba(255, 0, 0, .5);
}
.left{
    position:relative;
    left:-200px;
    float:left;
    width:200px;
    height: 300px;
    margin-left:-100%;
    background-color: rgba(0, 255, 0, .5);
}
.right{
    position:relative;
    right:-180px;
    float:left;
    width:180px;
    height: 300px;
    margin-left:-180px;
    background-color: rgba(0, 0, 255, .5);
}

.clearfloat{
    zoom:1;
}
.clearfloat:after{
    display:block;
    clear:both;
    content: "";
    visibility:hidden;
    height:0;
}
```