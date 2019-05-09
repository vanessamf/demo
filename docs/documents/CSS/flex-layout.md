# flex布局


## 题目要求：##

?>针对如下DOM结构，编写CSS，实现三栏水平布局，其中left、right分别位于左右两侧，left宽度为200px，right宽度为180px，main处在中间，宽度自适应。

## 实现效果 ##

?> <a class="btn btn-success" href="https://vanessamf.github.io/demos/layout/index6.html" role="button" target="_blank">
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
        display: flex;
    }
.middle {
    flex: 1;
    height: 300px;
    background-color: rgba(255, 0, 0, .5);
}
.left{
    order: -1;
    flex: 0 0 200px;
    height: 300px;
    background-color: rgba(0, 255, 0, .5);
}
.right{
    flex: 0 0 180px;
    height: 300px;
    background-color: rgba(0, 0, 255, .5);
}
```

