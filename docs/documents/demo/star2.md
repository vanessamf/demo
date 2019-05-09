# 五星评分二
## 实现效果 ##
?>  <a class="btn btn-success" href="https://vanessamf.github.io/demos/star/index2.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

### html ###
```html
 <body>
    <div class="rating-wrapper">
        <span>评价</span>
        <ul class="star-wrapper">
            <li class="rating-item iconfont icon-xingzhuang60kaobei2"></li>
            <li class="rating-item iconfont icon-xingzhuang60kaobei2"></li>
            <li class="rating-item iconfont icon-xingzhuang60kaobei2"></li>
            <li class="rating-item iconfont icon-xingzhuang60kaobei2"></li>
            <li class="rating-item iconfont icon-xingzhuang60kaobei2"></li>
        </ul>
    </div>
</body>
```

### CSS ###
```css
/* 五星评分 */
.rating-wrapper{
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.rating-wrapper span{
    font-size: 30px;
    /* color:#ffa043; */
}
.star-wrapper {
    text-align: center;
}   
.star-wrapper li{
    display: inline-block;
    color:#b5b5b5;
    cursor: pointer;
    font-size: 30px;
    margin-left:10px;
}
.star-wrapper li.active{
    color:#ffa043;
}
```

### 完整JS代码 ###
```javascript
<script type="text/javascript">
    // 五星评分
    var num = 5;
    var $rating = $('.star-wrapper');
    var $item = $rating.find('.rating-item');

    //点亮星星
    var lightOn = function(num) {
        $item.each(function() {
            if($(this).index() < num) {
                $(this).addClass("active");
            } else {
                $(this).removeClass("active");
            }
        });
    }

    //初始化,点亮num个星星
    lightOn(num);

    $item.on('mouseover', function() { //鼠标移入时,触发相应操作
        lightOn($(this).index() + 1);
    }).on('click', function() { //鼠标点击时,触发相应操作
        num = $(this).index() + 1;
    });

    //鼠标移出是,触发相应的操作
    $rating.on('mouseout', function() {
        lightOn(num);
    });
</script>
```