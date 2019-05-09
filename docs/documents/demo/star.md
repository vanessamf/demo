# 五星评分
## 实现效果 ##
?>  <a class="btn btn-success" href="https://vanessamf.github.io/demos/star/index.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

### html ###
```html
<body>
    <div class="star-wrapper">
        <div class="star" data-num="4.6">
        </div>
    </div>
    <div class="star-wrapper">
        <div class="star" data-num="3.3">
        </div>
    </div>
</body>
```

### CSS ###
```css
/* 五角星评分 */
.star-wrapper{
    padding:60px;
}
.star {
    font-size: 0;
}

.star .star-item {
    display: inline-block;
    background-repeat: no-repeat;
    width: 30px;
    height: 30px;
    margin-right: 10px;
    background-size: 30px 30px;
}

.star .star-item:last-child {
    margin-right: 0;
}

.star .star-item.on {
    background-image: url("../images/star_on@2x.png");
}

.star .star-item.half {
    background-image: url("../images/star_half@2x.png");
}

.star .star-item.off {
    background-image: url("../images/star_off@2x.png");
}

@media (-webkit-min-device-pixel-ratio:3),
(min-device-pixel-ratio:3) {
    .star .star-item.on {
        background-image: url("../images/star_on@3x.png");
    }

    .star .star-item.half {
        background-image: url("../images/star_half@3x.png");
    }

    .star .star-item.off {
        background-image: url("../images/star_off@3x.png");
    }
}
```
### 完整JS代码 ###
```javascript
<script type="text/javascript">
    function itemStar(star, num) {
        var result = [];
        var LENGTH = 5;
        var CLS_ON = 'on';
        var CLS_HALF = 'half';
        var CLS_OFF = 'off';
        
        //Math.floor向下取整
        var score = Math.floor(num * 2) / 2;
        //判断是否为小数
        var hashDecimal = score % 1 !== 0;
        //向下取整数部分
        var integer = Math.floor(score);
        //五角星置空
        star.empty();
        for(var i = 0; i < integer; i++) {
            //整数部分显示整星
            result.push(CLS_ON);
            star.append('<i class="star-item ' + CLS_ON + '"></i>');
        }
        if(hashDecimal) {
            //小数部分显示半星
            result.push(CLS_HALF);
            star.append('<i class="star-item ' + CLS_HALF + '"></i>');
        }
        while(result.length < LENGTH) {
            //不够五星的部分用默认灰色星星补齐
            result.push(CLS_OFF);
            star.append('<i class="star-item ' + CLS_OFF + '"></i>');
        }
        //return result;
    }
    var starItems = $(".star");
    for(var i = 0; i < starItems.length; i++) {
        var dataNum = starItems.eq(i).attr("data-num");
        itemStar(starItems.eq(i), dataNum);
    }
</script>
```