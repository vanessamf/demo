# 回到顶部
## 实现效果 ##

?> 
<a class="btn btn-success" href="https://vanessamf.github.io/demos/toTop/index.html" role="button" target="_blank">
查看演示
</a>

## 具体过程 ##

```html
<div class="wrapper">
    <a href="javascript:void(0);" id="toTop" class="to-top fa fa-arrow-circle-up">
    </a>
</div>
```

```css
.wrapper{
    height:3200px;
    background:#F3D250;
}
.to-top{
    display: none;
    position: fixed;
    bottom: 30px;
    right: 4%;
    text-decoration: none;
    color:rgba(250,142,214, 0.8);
    font-size:50px;
    }   
     
.to-top:focus,
.to-top:link,  
.to-top:visited,  
.to-top:hover,
.to-top:active {
 /*color:rgb(250,142,214);*/
    text-decoration: none;
}

.to-top:focus{
    color:#FF8AD8;
}

.to-top:hover{
    color:#FF8AD8;
}
```

```javascript
//回到顶部
backButton = $('.to-top');

function backToTop() {
    $('html,body').animate({
        scrollTop: 0
    }, 800)
}
backButton.on('click', backToTop);

$(window).on('scroll', function() {
    if($(window).scrollTop() > $(window).height())
        backButton.fadeIn();
    else
        backButton.fadeOut();
})
$(window).trigger('scroll'); //只要一刷新让程序自己触发事件
```