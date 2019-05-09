# 绝对定位布局


## 题目要求：##

?>针对如下DOM结构，编写CSS，实现三栏水平布局，其中left、right分别位于左右两侧，left宽度为200px，right宽度为180px，main处在中间，宽度自适应。

## 实现效果 ##

?> <a class="btn btn-success" href="https://vanessamf.github.io/demos/layout/index5.html" role="button" target="_blank">
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
### <span id="item_1" class="inline-toc">2.</span>css  ###
```css
.container{
    position:relative;
}
.middle {
    margin-left:200px;
    margin-right:180px;
    height: 300px;
    background-color: rgba(255, 0, 0, .5);
}
.left{
    position: absolute;
    top:0;
    left:0;
    width:200px;
    height: 300px;
    background-color: rgba(0, 255, 0, .5);
}
.right{
    position: absolute;
    top:0;
    right:0;
    width:180px;
    height: 300px;
    background-color: rgba(0, 0, 255, .5);
}
```

