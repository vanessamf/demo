# 懒加载

## 实现效果 ##

?> <a class="btn btn-success" href="https://vanessamf.github.io/demos/lazyLoad/index4.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

```html
<div>
    <img class="pic" src="img/load.gif" data-src="img/12254.jpg" alt="Image Not Found" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/12262.jpg" alt="" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/1957.jpg" alt="" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/3092.jpg" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/4000.jpg" alt="" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/12261.jpg" alt="" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/17254.jpg" alt="" />
</div>
<!--<div>
    <img class="pic" src="img/load.gif" data-src="img/2222" onerror="javascript:this.src='img/load.gif';this.onerror = null" alt="Image Not Found" />
</div>-->
<div>
    <img class="pic" src="img/load.gif" data-src="img/33333.jpg" alt="Image 33333 Not Found" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="img/44835.jpg" alt="" />
</div>
<div>
    <img class="pic" src="img/load.gif" data-src="" alt="" />
</div>
```

```css
img {
    width: 600px;
    height: 260px;
}
```

```javascript
function isVisible1($node) {
    var winH = $(window).height(),
    //浏览器窗口高度
    scrollTop = $(document).scrollTop(),
    //滚轮滚动高度
    offSetTop = $node.offset().top; //元素距离浏览器顶部的距离
    if(offSetTop < winH + scrollTop) {
        let src_value = $node.attr("data-src");
        $node.attr("src", src_value);
        return true;
    } else {
        return false;
    }
}

function loadPartImg1() {
    $(".pic").each(function() {
        if($(this).attr("data-src") == undefined || $(this).attr("data-src") == "") {
            return;
        } else {
            isVisible1($(this));
        }
    });
}
loadPartImg1();
$(window).on("scroll", function() {
    loadPartImg1();
    $(".pic").one("error", function(e) {
    $(this).attr("src", "img/load.gif");
    });
});
```