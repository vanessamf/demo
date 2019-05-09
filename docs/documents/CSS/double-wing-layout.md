# 双飞翼布局


## 题目要求：##

?>针对如下DOM结构，编写CSS，实现三栏水平布局，其中left、right分别位于左右两侧，left宽度为200px，right宽度为180px，main处在中间，宽度自适应。

## 实现效果 ##

?> <a class="btn btn-success" href="https://vanessamf.github.io/demos/layout/index4.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##
### <span id="item_1" class="inline-toc">1.</span> 结构 ###
```html
<div class="middle-container">
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
</div>
<div class="left"></div>
<div class="right"></div>
```
### <span id="item_1" class="inline-toc">2.</span> middle容器设置宽度100%，并左浮动 ###
```css
.middle-container{
    width:100%;
    float: left;
}
```
### <span id="item_1" class="inline-toc">3.</span> middle左右设置margin留出宽度 ###

```css
.middle {
    margin-left:200px;
    margin-right:180px;
    height: 300px;
    background-color: rgba(255, 0, 0, .5);
}
```
### <span id="item_1" class="inline-toc">4.</span> 左侧与middle容器左侧对齐,恰好到其位置 ###
```css
.left{
    float:left;
    width:200px;
    height: 300px;
    margin-left:-100%;
    background-color: rgba(0, 255, 0, .5);
}
```
### <span id="item_1" class="inline-toc">6.</span> 右侧与middle容器右侧对齐,恰好到其位置 ###
```css
.right{
    float:left;
    width:180px;
    height: 300px;
    margin-left:-180px;
    background-color: rgba(0, 0, 255, .5);
}
```

