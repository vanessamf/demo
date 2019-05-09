# 轮播图二 —— 无缝轮播图

### 实现效果 ###

?> 五张图无缝轮播
<a class="btn btn-success" href="https://vanessamf.github.io/demos/carousel/index2.html" role="button" target="_blank">
查看演示
</a>

### 实现方式 ###

?> <a href="#/documents/demo/seamless-carousel?id=item_1"><span class="inline-toc" >1.</span>容器里面放上5张图、5个小圆点以及上一张和下一张按钮，并在最前面补上最后一张，在最后面补上第一张；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_2"><span class="inline-toc">2.</span>这7张图float:left并左移一张图的距离，让实际要显示的第一张图排在第一个，并超出隐藏；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_3"><span class="inline-toc">3.</span>设置圆点和上下页按钮的位置；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_4"><span class="inline-toc">4.</span>自动轮播，设置定时器；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_5"><span class="inline-toc">5.</span>如果滑动到最后一张转到要显示的第一张，如果滑动到第一张转到要显示的最后一张，并设置圆点的变化；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_6"><span class="inline-toc">6.</span>点击小圆点进行切换；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_7"><span class="inline-toc">7.</span>点击上下页按钮进行切换；</a>
    <br/>
    <a href="#/documents/demo/seamless-carousel?id=item_8"><span class="inline-toc">8.</span>手指滑动切换；</a>
    <br/>
    
### 具体过程 ###

<span id="item_1" class="inline-toc" >1.</span>容器里面放上5张图、5个小圆点以及上一张和下一张按钮，并在最前面补上最后一张，在最后面补上第一张；

```html
<div class="wrapper">
    <div class="banner">
        <ul class="banner-list">
            <!--最后一张-->
            <li class="item">
                <a href="#"><img src="images/499259.jpg" alt="" /></a>
            </li>
            <li class="item">
                <a href="#"><img src="images/351376.jpg" alt="" /></a>
            </li>
            <li class="item">
                <a href="#"><img src="images/360617.jpg" alt="" /></a>
            </li>
            <li class="item">
                <a href="#"><img src="images/363165.jpg" alt="" /></a>
            </li>
            <li class="item">
                <a href="#"><img src="images/43183.jpg" alt="" /></a>
            </li>
            <li class="item">
                <a href="#"><img src="images/499259.jpg" alt="" /></a>
            </li>
            <!--第一张-->
            <li class="item">
                <a href="#"><img src="images/351376.jpg" alt="" /></a>
            </li>
        </ul>
        <ul class="banner-num">
            <li class="num-text active"></li>
            <li class="num-text"></li>
            <li class="num-text"></li>
            <li class="num-text"></li>
            <li class="num-text"></li>
        </ul>
        <div class="prev">&lt;</div>
        <div class="next">&gt;</div>
    </div>
</div>
```

<span id="item_2" class="inline-toc">2.</span>这7张图float:left；并左移一张图的距离，让实际要显示的第一张图排在第一个，并超出隐藏；

```css
.wrapper{
    height:3200px;
    background:#F3D250;
}
.banner{
    position: relative;
    width:100%;
    overflow: hidden;
}
.banner-list{
    width:700%;
    transform: translate(-14.2857%);
    -webkit-transform:  translate(-14.2857%);
}
.banner-list .item{
    width:14.2857%;
    float:left;
}
.banner-list .item a{
    display: block;
    width:100%;
}
.banner-list .item img{
    width:100%;
    height:100%;
}
```


<span id="item_3" class="inline-toc">3.</span>设置圆点和上下页按钮的位置；
```css
.banner-num{
    position: absolute;
    width:118px;
    height:6px;
    left:50%;
    margin-left:-59px;
    bottom:35px;
}
.num-text{
    width:8px;
    height:8px;
    border:1px solid #000;
    border-radius: 50%;
    margin-left:10px;
    float:left;
}
.num-text:first-child{
    margin-left:0;
}
.num-text.active{
    background:#000;
}
.prev{
    display: none;
    position: absolute;
    top:50%;
    left:0;
    margin-top:-25px;
    width:50px;
    height:50px;
    line-height: 50px;
    text-align: center;
    color:#fff;
    background: rgba(0,0,0,0.6);
}
.next{
    display: none;
    position: absolute;
    top:50%;
    right:0;
    margin-top:-25px;
    width:50px;
    height:50px;
    line-height: 50px;
    text-align: center;
    color:#fff;
    background: rgba(0,0,0,0.6);
}
```


<span id="item_4" class="inline-toc">4.</span>自动轮播，设置定时器；

```javascript
var banner = document.querySelector('.banner');
var width = banner.offsetWidth;
var imageBox = banner.querySelector('.banner-list');
/*点容器*/
var pointBox = banner.querySelector('.banner-num');
/*所有的点*/
var points = pointBox.querySelectorAll('.num-text');

var addTransition = function() {
    imageBox.style.transition = 'all 0.2s';
    imageBox.style.webkitTransition = 'all 0.2s';
}
var removeTransition = function() {
    imageBox.style.transition = 'none';
    imageBox.style.webkitTransition = 'none';
}
var setTranslateX = function(translateX) {
    imageBox.style.transform = 'translateX(' + translateX + 'px)';
    imageBox.style.webkitTransform = 'translateX(' + translateX + 'px)';
}

var index = 1;
var num = imageBox.querySelectorAll('.item').length;

var timer = null;
Carousel = function() {
    clearInterval(timer);
    timer = setInterval(function() {
        index++;
        addTransition();
        setTranslateX(-index * width);
    }, 2000);
}
Carousel();
```

<span id="item_5" class="inline-toc">5.</span>如果滑动到最后一张转到要显示的第一张，如果滑动到第一张转到要显示的最后一张，并设置圆点的变化；

```javascript
imageBox.addEventListener("transitionend", function() {
    if(index >= num - 1) {
        //最后一张的时候变为第二张，即要显示的第一张
        index = 1;
        removeTransition();
        setTranslateX(-index * width);
    } else if(index <= 0) {
        //第一张的时候变为倒数第二张，即要显示的最后一张
        index = num - 2;
        removeTransition();
        setTranslateX(-index * width);
    }
    setPoint();
})
var setPoint = function() {
    for(var i = 0; i < points.length; i++) {
        var obj = points[i];
        obj.classList.remove('active');
    }
    points[index - 1].classList.add('active');
}
```

<span id="item_6" class="inline-toc">6.</span>点击小圆点进行切换；

```javascript
//点击圆点切换
for(var i = 0; i < points.length; i++) {　
    (function(n) {
        points[i].onclick = function() {
            index = n + 1;
            addTransition();
            setTranslateX(-index * width);
            setPoint(); //等同于上面的
        }
    })(i)
}
```

<span id="item_7" class="inline-toc">7.</span>点击上下页按钮进行切换；

```javascript
document.querySelector(".prev").onclick = function() {
    clearInterval(timer);
    index = index - 1;
    addTransition(); //有transition才会执行transitionend
    setTranslateX(-index * width);
}
document.querySelector(".next").onclick = function() {
    clearInterval(timer);
    index = index + 1;
    addTransition();
    setTranslateX(-index * width);
}
//鼠标进入
banner.addEventListener('mouseover', function(e) {
    clearInterval(timer);
    document.querySelector(".prev").style.display="block";
    document.querySelector(".next").style.display="block";
})
//鼠标移出
banner.addEventListener('mouseout', function(e) {
    Carousel(index);
    document.querySelector(".prev").style.display="none";
    document.querySelector(".next").style.display="none";
})
```

<span id="item_8" class="inline-toc">8.</span>手指滑动切换；

```javascript
//手指滑动切换
var startX = 0;
var distanceX = 0;
var isMove = false;
imageBox.addEventListener('touchstart', function(e) {
    /*清除定时器*/
    clearInterval(timer);
    /*记录起始位置的X坐标*/
    startX = e.touches[0].clientX;
});

imageBox.addEventListener('touchmove', function(e) {
    /*记录滑动过程当中的X坐标*/
    var moveX = e.touches[0].clientX;
    /*计算位移  有正负方向*/
    distanceX = moveX - startX;
    /*计算目标元素的位移  不用管正负*/
    /*元素将要的定位=当前定位+手指移动的距离*/
    var translateX = -index * width + distanceX;
    /*滑动--->元素随着手指的滑动做位置的改变*/
    removeTransition();
    setTranslateX(translateX);
    isMove = true;
});

imageBox.addEventListener('touchend', function(e) {
    /*4. 滑动结束的时候    如果滑动的距离不超过屏幕的1/3  吸附回去   过渡*/
    /*5. 滑动结束的时候    如果滑动的距离超过屏幕的1/3  切换（上一张，下一张）根据滑动的方向，过渡*/
    /*要使用移动的距离*/
    if(isMove) {
        if(Math.abs(distanceX) < width / 3) {
            /*吸附*/
            addTransition();
            setTranslateX(-index * width);
        } else {
            /*切换*/
            /*右滑动 上一张*/
            if(distanceX > 0) {
                index--;
            }
            /*左滑动 下一张*/
            else {
                index++;
            }
            /*根据index去动画的移动*/
            addTransition();
            setTranslateX(-index * width);
        }
    }
    /*最好做一次参数的重置*/
    startX = 0;
    distanceX = 0;
    isMove = false;
    /*加上定时器*/
    Carousel();
});
```


### 完整JS代码 ###
```javascript
window.onload = function() {
    banner();
}
window.onresize = function() {
    //  banner();
}
var banner = function() {
    /*1. 自动轮播图且无缝   定时器，过渡*/
    /*2. 点要随着图片的轮播改变  根据索引切换*/ 
    /*3. 滑动效果  利用touch事件完成*/
    /*4. 滑动结束的时候    如果滑动的距离不超过屏幕的1/3  吸附回去   过渡*/
    /*5. 滑动结束的时候    如果滑动的距离超过屏幕的1/3  切换（上一张，下一张）根据滑动的方向，过渡*/
    /*轮播图*/
    var banner = document.querySelector('.banner');
    /*屏幕宽度*/
    var width = banner.offsetWidth;
    /*图片容器*/
    var imageBox = banner.querySelector('.banner-list');
    /*点容器*/
    var pointBox = banner.querySelector('.banner-num');
    /*所有的点*/
    var points = pointBox.querySelectorAll('.num-text');

    var addTransition = function() {
        imageBox.style.transition = 'all 0.2s';
        imageBox.style.webkitTransition = 'all 0.2s';
    }
    var removeTransition = function() {
        imageBox.style.transition = 'none';
        imageBox.style.webkitTransition = 'none';
    }
    var setTranslateX = function(translateX) {
        imageBox.style.transform = 'translateX(' + translateX + 'px)';
        imageBox.style.webkitTransform = 'translateX(' + translateX + 'px)';
    }

    var index = 1;
    //var num = $(".banner-list .item").length;
    var num = imageBox.querySelectorAll('.item').length;

    //  var timer = setInterval(function() {
    //      index++;
    //      addTransition();
    //      if(index<num){
    //          setTranslateX(-index * width);
    //      }else{
    //          index=0;
    //          removeTransition();
    //          setTranslateX(-index * width);
    //      }
    //  }, 1000);
    var timer = null;
    Carousel = function() {
        clearInterval(timer);
        timer = setInterval(function() {
            index++;
            addTransition();
            setTranslateX(-index * width);
        }, 2000);
    }
    Carousel();
    //  var timer = setInterval(function() {
    //      index++;
    //      addTransition();
    //      setTranslateX(-index * width);
    //  }, 2000);

    /*需要等最后一张动画结束去判断 是否瞬间定位第一张*/
    imageBox.addEventListener("transitionend", function() {
        if(index >= num - 1) {
            //最后一张的时候变为第二张，即要显示的第一张
            index = 1;
            removeTransition();
            setTranslateX(-index * width);
        } else if(index <= 0) {
            //第一张的时候变为倒数第二张，即要显示的最后一张
            index = num - 2;
            removeTransition();
            setTranslateX(-index * width);
        }
        setPoint();
    })
    var setPoint = function() {
        for(var i = 0; i < points.length; i++) {
            var obj = points[i];
            obj.classList.remove('active');
        }
        points[index - 1].classList.add('active');
    }

    //点击圆点切换
    for(var i = 0; i < points.length; i++) {　
        (function(n) {
            points[i].onclick = function() {
                //for(var i = 0; i < points.length; i++) {
                //  points[i].classList.remove('active');
                //}
                //points[n].classList.add('active');
                index = n + 1;
                addTransition();
                setTranslateX(-index * width);
                setPoint(); //等同于上面的
            }
        })(i)
    }
    document.querySelector(".prev").onclick = function() {
        clearInterval(timer);
        index = index - 1;
        addTransition(); //有transition才会执行transitionend
        setTranslateX(-index * width);
    }
    document.querySelector(".next").onclick = function() {
        clearInterval(timer);
        index = index + 1;
        addTransition();
        setTranslateX(-index * width);
    }
    //鼠标进入
    banner.addEventListener('mouseover', function(e) {
        clearInterval(timer);
        document.querySelector(".prev").style.display="block";
        document.querySelector(".next").style.display="block";
    })
    //鼠标移出
    banner.addEventListener('mouseout', function(e) {
        Carousel(index);
        document.querySelector(".prev").style.display="none";
        document.querySelector(".next").style.display="none";
    })
    
    //手指滑动切换
    var startX = 0;
    var distanceX = 0;
    var isMove = false;
    imageBox.addEventListener('touchstart', function(e) {
        /*清除定时器*/
        clearInterval(timer);
        /*记录起始位置的X坐标*/
        startX = e.touches[0].clientX;
    });

    imageBox.addEventListener('touchmove', function(e) {
        /*记录滑动过程当中的X坐标*/
        var moveX = e.touches[0].clientX;
        /*计算位移  有正负方向*/
        distanceX = moveX - startX;
        /*计算目标元素的位移  不用管正负*/
        /*元素将要的定位=当前定位+手指移动的距离*/
        var translateX = -index * width + distanceX;
        /*滑动--->元素随着手指的滑动做位置的改变*/
        removeTransition();
        setTranslateX(translateX);
        isMove = true;
    });

    imageBox.addEventListener('touchend', function(e) {
        /*4. 滑动结束的时候    如果滑动的距离不超过屏幕的1/3  吸附回去   过渡*/
        /*5. 滑动结束的时候    如果滑动的距离超过屏幕的1/3  切换（上一张，下一张）根据滑动的方向，过渡*/
        /*要使用移动的距离*/
        if(isMove) {
            if(Math.abs(distanceX) < width / 3) {
                /*吸附*/
                addTransition();
                setTranslateX(-index * width);
            } else {
                /*切换*/
                /*右滑动 上一张*/
                if(distanceX > 0) {
                    index--;
                }
                /*左滑动 下一张*/
                else {
                    index++;
                }
                /*根据index去动画的移动*/
                addTransition();
                setTranslateX(-index * width);
            }
        }
        /*最好做一次参数的重置*/
        startX = 0;
        distanceX = 0;
        isMove = false;
        /*加上定时器*/
        //clearInterval(timer);
        //      timer = setInterval(function() {
        //          index++;
        //          addTransition();
        //          setTranslateX(-index * width);
        //      }, 2000);
        Carousel();
    });
}
```