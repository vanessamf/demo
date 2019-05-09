# 轮播图一 
### 实现效果 ###

?> 五张图轮换显示 
<a class="btn btn-success" href="https://vanessamf.github.io/demos/carousel/index.html" role="button" target="_blank">
查看演示
</a>

### 实现方式 ###

?> <a href="#/documents/demo/carousel?id=item_1"><span class="inline-toc" >1.</span>容器里面放上5张图以及5个小圆点；</a>
    <br/>
    <a href="#/documents/demo/carousel?id=item_2"><span class="inline-toc">2.</span>这5张图绝对定位重叠在一起，此时最后一张在最上面；</a>
    <br/>
    <span class="inline-toc">3.</span>将每张图片的容器opacity设置为0；
    <br/>
    <span class="inline-toc">4.</span>将当前active图片的容器opacity设置为1；
    <br/>
    <span class="inline-toc">5.</span>设置banner高度；
    <br/>
    1.窗口宽度大于1440px的时候，banner高度为500px;
     <br/>
    2.窗口宽度大于960px，小于1440px的时候，banner高度/500px等于宽度/1440;
     <br/>
    3.其它时候banner高度为333.3333px；
     <br/>
     <span class="inline-toc">6.</span>根据图片数量设置圆点数量；
    <br/>
    <span class="inline-toc">7.</span>点击圆点设置图片的显示与隐藏；
    <br/>
     <span class="inline-toc">8.</span>自动轮播，设置定时器；
    <br/>

### 具体过程 ###

<span id="item_1" class="inline-toc">1.</span>容器里面放上5张图以及5个小圆点；

HTML:
```html
<div class="wrapper">
    <div class="banner">
        <ul class="banner-list">
            <li class="item active">
                <img src="images/351376.jpg" alt="" />
            </li>
            <li class="item">
                <img src="images/360617.jpg" alt="" />
            </li>
            <li class="item">
                <img src="images/363165.jpg" alt="" />
            </li>
            <li class="item">
                <img src="images/43183.jpg" alt="" />
            </li>
            <li class="item">
                <img src="images/499259.jpg" alt="" />
            </li>
        </ul>
        <div class="banner-num">
        </div>
    </div>
</div>
```

<span id="item_2" class="inline-toc">2.</span>这5张图绝对定位重叠在一起，此时最后一张在最上面；

CSS:
```css
.wrapper {
    height: 3200px;
    background: #F3D250;
}

.banner {
    position: relative;
    min-width: 960px;
}

.banner-list {
    position: relative;
    width: 100%;
    height: 100%;
}

.banner-list .item {
    position: absolute;
    width: 100%;
    height: 100%;
    opacity: 0;
    transition: opacity .8s ease-in-out;
}

.banner-list .item.active {
    opacity: 1;
}

.banner-list .item img {
    width: 100%;
    height: 100%;
}

.banner-num {
    position: absolute;
    bottom: 35px;
    left: 50%;
    transform: translateX(-50%);
}

.num-text {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: rgba(0, 0, 0, .4);
    margin-right: 15px;
}

.num-text:last-child {
    margin-right: 0;
}

.num-text.active {
    background-color: rgba(0, 0, 0, 1);
}
```

<span class="inline-toc">5.</span>设置banner高度；

JavaScript:
```javascript
banner();
function banner() {
    var _win_width = $(window).width(),
        _header_hei = $(window).height();
    if(_win_width > 1440) {
        $('.banner').height('500px');
    } else if(_win_width < 1440 && _win_width > 960) {
        _header_hei = 500 * _win_width / 1440;
        $('.banner').height(_header_hei);
    } else {
        $('.banner').height("333.3333px");
    }
}
```

<span class="inline-toc">6.</span>根据图片数量设置圆点数量；

JavaScript:
```javascript
var num = $(".banner-list .item").length;

for(var i = 0; i < num; i++) {
    $(".banner-num").append("<a class='num-text' href='javascript:void(0);'>" + "</a>");
}
$(".banner-num .num-text").eq(0).addClass("active");    
```

<span class="inline-toc">7.</span>点击圆点设置图片的显示与隐藏；

JavaScript:
```javascript
$(".banner-num .num-text").each(function(i) {
    $(this).click(function() {
        change(i);
    })
})

function change(i) {
    $(".banner-list .item").eq(i).siblings(".item").removeClass("active");
    $(".banner-list .item").eq(i).addClass("active");
    $(".banner-num .num-text").eq(i).siblings(".num-text").removeClass("active");
    $(".banner-num .num-text").eq(i).addClass("active");
}
```

<span class="inline-toc">8.</span>自动轮播，设置定时器；

JavaScript:
```javascript
var theInt = null;
Carousel = function(p) {
    clearInterval(theInt);
    theInt = setInterval(function() {
        p++;
        if(p < num) {
            change(p);
        } else {
            p = 0;
            change(p);
        }
    }, 2000);
}
Carousel(0);
```

### 完整JS代码 ###
```javascript
$(function() {
    banner();

    function banner() {
        var _win_width = $(window).width(),
            _header_hei = $(window).height();
        if(_win_width > 1440) {
            $('.banner').height('500px');
        } else if(_win_width < 1440 && _win_width > 960) {
            _header_hei = 500 * _win_width / 1440;
            $('.banner').height(_header_hei);
        } else {
            $('.banner').height("333.3333px");
        }
    }
    //      window.onresize=function(){
    //              banner();
    //      }
    $(window).resize(function() {
        //调整窗口大小时显示
        banner();
    });

    var theInt = null;
    var num = $(".banner-list .item").length;

    for(var i = 0; i < num; i++) {
        $(".banner-num").append("<a class='num-text' href='javascript:void(0);'>" + "</a>");
    }
    $(".banner-num .num-text").eq(0).addClass("active");

    $(".banner-num .num-text").each(function(i) {
        $(this).click(function() {
            change(i);
        })
    })

    Carousel = function(p) {
        clearInterval(theInt);
        theInt = setInterval(function() {
            p++;
            if(p < num) {
                change(p);
            } else {
                p = 0;
                change(p);
            }
        }, 2000);
    }
    Carousel(0);

    function change(i) {
        $(".banner-list .item").eq(i).siblings(".item").removeClass("active");
        $(".banner-list .item").eq(i).addClass("active");
        $(".banner-num .num-text").eq(i).siblings(".num-text").removeClass("active");
        $(".banner-num .num-text").eq(i).addClass("active");
    }
})
```