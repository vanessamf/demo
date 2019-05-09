# 点菜
## 实现效果 ##
?>  <a class="btn btn-success" href="https://vanessamf.github.io/demos/menu/index.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

### html ###
```html
<body>
    <div class="gc-container menu-container">
        <!--头部-->
        <div class="header">
            <a href="javascript:void(0);">
                <i class="iconfont icon-zuo"></i>
            </a>
            <div class="title-wrapper">我家小馆</div>
            <a href="">
                <i class="iconfont icon-fenxiang"></i>
            </a>
        </div>
        <div class="menu-wrapper">
            <div class="menu-header">
                <a href="">
                    <i class="iconfont icon-saomiao"></i>
                </a>
                <div class="input-wrapper">
                    <input class="iconfont" type="search" placeholder="&#xe61c; 商品名称、简拼或编码">
                </div>
                <div class="num">人数：3</div>
            </div>
            <div class="menu-content">
                <!--左侧菜单-->
                <nav class="menu-nav">
                    <ul class="nav-list">
                        <li class="nav-item active" data-name="cate-0">
                            <a href="javascript:void(0);">
                                <img class="icon" src="images/hot@2x.png" alt="" /> 热销
                            </a>
                        </li>
                        <li class="nav-item" data-name="cate-1">
                            <a href="javascript:void(0);">
                                新品上市
                            </a>
                        </li>
                        <li class="nav-item" data-name="cate-2">
                            <a href="javascript:void(0);">
                                招牌推荐
                            </a>
                        </li>
                    </ul>
                </nav>
                <!--右侧菜品-->
                <div class="menu-foods" id="menu-foods">
                    <!--右侧固定头部-->
                    <div class="top-fixed-wrapper">
                        <div class="fixed-title">热销</div>
                    </div>
                    <!--右侧内容-->
                    <div class="foods-content" id="foods-content">
                        <div class="foods-list" id="cate-0">
                            <dl>
                                <dt class="food-title">热销</dt>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/1111.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/222222.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/3333.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/2222.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                            </dl>
                        </div>
                        <div class="foods-list" id="cate-1">
                            <dl>
                                <dt class="food-title">新品上市</dt>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/1111.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/1111.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                            </dl>
                        </div>
                        <div class="foods-list" id="cate-2">
                            <dl>
                                <dt class="food-title">招牌推荐</dt>
                                <dd class="food-item">
                                    <div class="img-wrapper">
                                        <img src="images/default.png" data-src="images/1111.jpg" alt="Image Not Found" />
                                    </div>
                                    <div class="content">
                                        <div class="name">XO酱蜜豆炒带子虾仁</div>
                                        <div class="price">￥54.00</div>
                                        <div class="cartcontrol">
                                            <div class="cart-decrease iconfont icon-jianhao1"></div>
                                            <div class="cart-count">0</div>
                                            <div class="cart-add iconfont icon-jiahao1"></div>
                                        </div>
                                    </div>
                                </dd>
                            </dl>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!--底部-->
        <div class="menu-footer">
            <div class="shopping-wrapper">
                <i class="shopping-btn iconfont icon-gouwuche"></i>
                <div class="num">0</div>
            </div>
            <div class="content-left">
                <div class="price">
                    <span>合计：</span>
                    <i>￥</i>
                    <span class="money">54.00</span>
                </div>
                <div>
                    <span>配送费0</span>
                    <span>打包费0</span>
                </div>
            </div>
            <div class="content-right pay-btn">付款</div>
        </div>
        <!--小球-->
        <i id="end" class="ball"></i>
        <!--购物车-->
        <div class="shopcart-container">
            <div class="shopcart-list">
                <div class="list-header">
                    <span id="">
                        已选商品
                    </span>
                    <span>
                        <i class="iconfont icon-lajitong6"></i>
                        清空
                    </span>
                </div>
                <div class="list-content">
                    <ul>
                        <li class="shop-item">
                            <div class="name">1.XO酱蜜豆炒带子虾仁</div>
                            <div class="price">￥18.00</div>
                            <div class="cartcontrol">
                                <div class="cart-decrease iconfont icon-jianhao1"></div>
                                <div class="cart-count">0</div>
                                <div class="cart-add iconfont icon-jiahao1"></div>
                            </div>
                        </li>
                        <li class="shop-item">
                            <div class="name">2.XO酱蜜豆炒带子虾仁</div>
                            <div class="price">￥18.00</div>
                            <div class="cartcontrol">
                                <div class="cart-decrease iconfont icon-jianhao1"></div>
                                <div class="cart-count">0</div>
                                <div class="cart-add iconfont icon-jiahao1"></div>
                            </div>
                        </li>
                        <li class="shop-item">
                            <div class="name">3.XO酱蜜豆炒带子虾仁</div>
                            <div class="price">￥18.00</div>
                            <div class="cartcontrol">
                                <div class="cart-decrease iconfont icon-jianhao1"></div>
                                <div class="cart-count">0</div>
                                <div class="cart-add iconfont icon-jiahao1"></div>
                            </div>
                        </li>
                        <li class="shop-item">
                            <div class="name">4.XO酱蜜豆炒带子虾仁</div>
                            <div class="price">￥18.00</div>
                            <div class="cartcontrol">
                                <div class="cart-decrease iconfont icon-jianhao1"></div>
                                <div class="cart-count">0</div>
                                <div class="cart-add iconfont icon-jiahao1"></div>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="shopcart-operation">
                <div class="content">
                    <div class="shopping-wrapper">
                        <i class="shopping-btn iconfont icon-gouwuche"></i>
                        <div class="num">0</div>
                    </div>
                    <div class="tips">
                        <span>配送费0</span>
                        <span>打包费0</span>
                    </div>
                    <div class="price">
                        <span>合计：</span>
                        <i>￥</i>
                        <span class="money">54.00</span>
                    </div>
                </div>
                <div class="btn-wrapper">
                    <div class="btn">付款</div>
                    <div class="btn-item">
                        <div class="btn-sm">先送</div>
                        <div class="btn-sm">挂单</div>
                    </div>
                </div>
            </div>
        </div>
        <!--蒙层-->
        <div class="overlay"></div>
    </div>
</body>
```

### 图片懒加载 ###
```javascript
//图片懒加载
function isVisible($node) {
    var winH = $(window).height();
    //右侧容器的高度
    var mfHeight = $(".menu-foods").height();
    var fiHeight = $(".food-item").eq(0).outerHeight();
    //滚轮滚动高度
    var scrollTop = $("#foods-content")[0].scrollTop;
    offSetTop = $node[0].offsetTop;  //元素距离浏览器顶部的距离
    if(offSetTop+50 < mfHeight + scrollTop) {
        let src_value = $node.find("img").attr("data-src");
        $node.find("img").attr("src", src_value);
        return true;
    } else {
        return false;
    }
}

function loadPartImg() {
    $(".food-item").each(function() {
        var $img = $(this).find("img");
        if($img.attr("data-src") == undefined || $img.attr("data-src") == "") {
            return;
        } else {
            isVisible($(this));
        }
    });
}
loadPartImg();
$("#foods-content").on("scroll", function() {
    loadPartImg();
    $(".food-item img").one("error", function(e) {
        $(this).attr("src", "images/default.png");
    });
});

```

### 右侧内容滚动时固定标题变化 ###
```javascript
//头部的高度
var headHeight = $(".header").outerHeight() + $(".menu-header").outerHeight();
//右侧容器的高度
var mfHeight = $(".menu-foods").height();
var foodsList = $(".foods-list");
//补齐最后一列的高度
$(".foods-list:last-child").css("min-height", mfHeight + 1 + "px");

//右侧一级菜单滚动
function scrollTitle() {
    //右侧滚动的距离
    var scrollTop = $("#foods-content")[0].scrollTop;
    var titleHeight = $(".top-fixed-wrapper").outerHeight();
    for(var i = 0; i < foodsList.length; i++) {
        //当前list距容器顶部距离（固定不变）
        var offsetTop = foodsList[i].offsetTop;
        //var offsetTop2=foodsList[i+1].offsetTop;
        //下一个list距容器顶部距离（固定不变）
        var offsetTop2 = foodsList[i].offsetTop + foodsList.eq(i).outerHeight();
        if(scrollTop >= offsetTop - 1 && scrollTop < offsetTop2 - titleHeight) {
            //滚动的距离在当前list到下一个list的标题与固定标题相遇之间时，标题固定，显示当前标题内容
            $(".top-fixed-wrapper").css("top", "0");
            $(".fixed-title").text(foodsList.eq(i).find(".food-title").text());
            break;
        } else if(scrollTop >= offsetTop2 - titleHeight && scrollTop < offsetTop2 - 1) {
            //滚动的距离在下一个list的标题与固定标题相遇到下一个list滑到顶部之间时，固定标题往上移动，显示当前标题内容
            $(".top-fixed-wrapper").css("top", -(titleHeight + scrollTop - offsetTop2) + "px");
            $(".fixed-title").text(foodsList.eq(i).find(".food-title").text());
            break;
        } else if(scrollTop == offsetTop2 - 1) {
            //滚动的距离等于下一个list的offset时，标题固定，显示下一个标题内容
            $(".top-fixed-wrapper").css("top", "0");
            $(".fixed-title").text(foodsList.eq(i + 1).find(".food-title").text());
            break;
        }
    }
}
```

### 左侧根据右侧当前滚动到的类别添加active ###
```javascript
// 左侧根据右侧当前滚动到的类别添加active
function scrollactive() {
    //右侧滚动的距离
    var scrollTop = $("#foods-content")[0].scrollTop;
    for(var i = 0; i < foodsList.length; i++) {
        var offsetTop = foodsList[i].offsetTop;
        var offsetTop2 = foodsList[i].offsetTop + foodsList.eq(i).outerHeight();
        if(scrollTop >= offsetTop - 1 && scrollTop < offsetTop2 - 1) {
            $(".nav-list .nav-item").eq(i).siblings("li.nav-item").removeClass("active");
            $(".nav-list .nav-item").eq(i).addClass("active");
            break;
        }
    }
}

document.getElementById('foods-content').onscroll = function() {
    scrollTitle();
    scrollactive();
};

```

### 左侧菜单点击时样式变化以及右侧滚动到相应位置 ###
```javascript
//左侧点击列表切换
$(".nav-list .nav-item").on("click", function() {
    if(!$(this).hasClass("active")) {
        //点击的时候页面滑动会添加active
        //$(this).siblings("li.nav-item").removeClass("active");
        //$(this).addClass("active");
        //点击左侧跳转到右侧对应列表
        //window.location.hash = "#"+$(this).attr("data-name");
        $("#foods-content").animate({
            //scrollTop: $("#"+$(this).attr("data-name")).offset().top-headHeight
            scrollTop: $("#" + $(this).attr("data-name"))[0].offsetTop
        }, {
            duration: 200,
            easing: "swing"
        });
        return false;
    }
});
```

### 购物车列表的显示与隐藏 ###

```javascript
//购物车列表
$(".menu-footer").on("click", function() {
    $(".menu-container .overlay").show();
    $(".shopcart-container").addClass("active");
})
$(".shopcart-operation").on("click", function() {
    $(".menu-container .overlay").hide();
    $(".shopcart-container").removeClass("active");
})

$(".menu-container .overlay").on("click", function() {
    $(".menu-container .overlay").hide();
    $(".shopcart-container").removeClass("active");
})
```


### 数量加减 ###

```javascript
//加
$(".cart-add").on("click", function() {
    $(this).parent().find(".cart-decrease").css({
        "display": "inline-block"
    });
    $(this).parent().find(".cart-count").css({
        "display": "inline-block"
    });
    //数量增加
    var tmp = parseInt($(this).parent().find(".cart-count").text());
    tmp += 1;
    $(this).parent().find(".cart-count").text(tmp);
    //计算总数
    var sum = 0;
    for(var i = 0; i < $(".cart-count").length; i++) {
        sum = sum + parseInt($(".cart-count").eq(i).text());
    }
    //购物车显示总数
    $(".shopping-wrapper .num").addClass("active");
    $(".shopping-wrapper .num").text(sum);
})
//减
$(".cart-decrease").on("click", function() {
    //数量减少
    var tmp = parseInt($(this).parent().find(".cart-count").text());
    tmp -= 1;
    $(this).parent().find(".cart-count").text(tmp);
    //计算总数
    var sum = 0;
    for(var i = 0; i < $(".cart-count").length; i++) {
        sum = sum + parseInt($(".cart-count").eq(i).text());
    }
    //购物车显示总数
    $(".shopping-wrapper .num").text(sum);
    //少于0时隐藏减号
    if($(this).parent().find(".cart-count").text() == 0) {
        $(this).parent().find(".cart-decrease").hide();
        $(this).parent().find(".cart-count").hide();
    }
    //少于0时修改购物车颜色
    if($(".shopping-wrapper .num").text() == 0) {
        $(".shopping-wrapper .num").removeClass("active");
    }
})
```
### 添加菜品动画效果(插件) ###

?> 相关插件  https://github.com/amibug/fly

```javascript
//添加菜品动画效果
$(".food-item .cart-add").on("click", addProduct);

function addProduct(event) {
    var x = event.pageX - $(document).scrollLeft();
    var y = event.pageY - $(document).scrollTop();
    var t = $(document).scrollTop();
    var l = $(document).scrollLeft();
    var offset = $('.ball').offset();
    var flyer = $("<lable class='pointer'></label>");
    flyer.fly({
        start: {
            left: x,//开始位置
            top: y//开始位置
        },
        end: {
            left: offset.left,//结束位置
            top: offset.top,//结束位置
            width: 10,//结束时宽度
            height: 10//结束时高度
        },
        onEnd: function() { //结束回调
            this.destroy(); //移除dom
        }
    });
}
```
### 提示弹框 ###
?>基于bootStrap修改的公共弹框
```javascript
//提示框dialog.js
function promptDialog(id, title,content, width){
    var html = "";
    html += '<div class="public-modal modal fade" id="' + id + '" tabindex="-1" role="dialog" aria-labelledby="myModalLabel">';
    html += '<div class="modal-dialog" role="document" style="width:' + width + '">';
    html += '<div class="modal-content">';
    html += '<div class="modal-header">';
    html += '<h4 class="modal-title" id="myModalLabel">' + title + '</h4>';
    html += '</div>';
    html += '<div class="modal-body">';
    html+='<div class="prompt-content">'+content+'</div>';
    html += '</div>';
    html += '<div class="mf modal-footer no-border">';
    html += '<button type="button" class="btn confirm-btn modal-btn" data-dismiss="modal">确认</button>';
    html += '</div>';
    html += '</div>';
    html += '</div>';
    html += '</div>';
    $('body').append(html);
}
```

弹框引用
```javascript
promptDialog("paymentModal", "提示", "订单120007付款成功！", "80%");
$(".pay-btn").on("click", function(event) {
    //阻止冒泡
    event.stopPropagation();
    $('#paymentModal').modal('show')
})
```

### 完整JS代码 ###
```javascript
<script type="text/javascript">
    $(document).ready(function() {
        promptDialog("paymentModal", "提示", "订单120007付款成功！", "80%");
        $(".pay-btn").on("click", function(event) {
            event.stopPropagation();
            $('#paymentModal').modal('show')
        })
    })
    //图片懒加载
    function isVisible($node) {
        var winH = $(window).height();
        //右侧容器的高度
        var mfHeight = $(".menu-foods").height();
        var fiHeight = $(".food-item").eq(0).outerHeight();
        //滚轮滚动高度
        var scrollTop = $("#foods-content")[0].scrollTop;
        offSetTop = $node[0].offsetTop;  //元素距离浏览器顶部的距离
        if(offSetTop+50 < mfHeight + scrollTop) {
            let src_value = $node.find("img").attr("data-src");
            $node.find("img").attr("src", src_value);
            return true;
        } else {
            return false;
        }
    }

    function loadPartImg() {
        $(".food-item").each(function() {
            var $img = $(this).find("img");
            if($img.attr("data-src") == undefined || $img.attr("data-src") == "") {
                return;
            } else {
                isVisible($(this));
            }
        });
    }
    loadPartImg();
    $("#foods-content").on("scroll", function() {
        loadPartImg();
        $(".food-item img").one("error", function(e) {
            $(this).attr("src", "images/default.png");
        });
    });
    
    window.onresize = function() {}
    window.onload = function() {
        //头部的高度
        var headHeight = $(".header").outerHeight() + $(".menu-header").outerHeight();
        //右侧容器的高度
        var mfHeight = $(".menu-foods").height();
        var foodsList = $(".foods-list");
        //补齐最后一列的高度
        $(".foods-list:last-child").css("min-height", mfHeight + 1 + "px");
        //左侧点击列表切换
        $(".nav-list .nav-item").on("click", function() {
            if(!$(this).hasClass("active")) {
                //点击的时候页面滑动会添加active
                //$(this).siblings("li.nav-item").removeClass("active");
                //$(this).addClass("active");
                //点击左侧跳转到右侧对应列表
                //window.location.hash = "#"+$(this).attr("data-name");
                $("#foods-content").animate({
                    //scrollTop: $("#"+$(this).attr("data-name")).offset().top-headHeight
                    scrollTop: $("#" + $(this).attr("data-name"))[0].offsetTop
                }, {
                    duration: 200,
                    easing: "swing"
                });
                return false;
            }
        });
        
        //右侧一级菜单滚动
        function scrollTitle() {
            //右侧滚动的距离
            var scrollTop = $("#foods-content")[0].scrollTop;
            var titleHeight = $(".top-fixed-wrapper").outerHeight();
            for(var i = 0; i < foodsList.length; i++) {
                //当前list距容器顶部距离（固定不变）
                var offsetTop = foodsList[i].offsetTop;
                //var offsetTop2=foodsList[i+1].offsetTop;
                //下一个list距容器顶部距离（固定不变）
                var offsetTop2 = foodsList[i].offsetTop + foodsList.eq(i).outerHeight();
                if(scrollTop >= offsetTop - 1 && scrollTop < offsetTop2 - titleHeight) {
                    //滚动的距离在当前list到下一个list的标题与固定标题相遇之间时，标题固定，显示当前标题内容
                    $(".top-fixed-wrapper").css("top", "0");
                    $(".fixed-title").text(foodsList.eq(i).find(".food-title").text());
                    break;
                } else if(scrollTop >= offsetTop2 - titleHeight && scrollTop < offsetTop2 - 1) {
                    //滚动的距离在下一个list的标题与固定标题相遇到下一个list滑到顶部之间时，固定标题往上移动，显示当前标题内容
                    $(".top-fixed-wrapper").css("top", -(titleHeight + scrollTop - offsetTop2) + "px");
                    $(".fixed-title").text(foodsList.eq(i).find(".food-title").text());
                    break;
                } else if(scrollTop == offsetTop2 - 1) {
                    //滚动的距离等于下一个list的offset时，标题固定，显示下一个标题内容
                    $(".top-fixed-wrapper").css("top", "0");
                    $(".fixed-title").text(foodsList.eq(i + 1).find(".food-title").text());
                    break;
                }
            }
        }
        
        //左侧根据右侧当前滚动到的类别添加active
        function scrollactive() {
            //右侧滚动的距离
            var scrollTop = $("#foods-content")[0].scrollTop;
            for(var i = 0; i < foodsList.length; i++) {
                var offsetTop = foodsList[i].offsetTop;
                var offsetTop2 = foodsList[i].offsetTop + foodsList.eq(i).outerHeight();
                if(scrollTop >= offsetTop - 1 && scrollTop < offsetTop2 - 1) {
                    $(".nav-list .nav-item").eq(i).siblings("li.nav-item").removeClass("active");
                    $(".nav-list .nav-item").eq(i).addClass("active");
                    break;
                }
            }
        }

        document.getElementById('foods-content').onscroll = function() {
            scrollTitle();
            scrollactive();
        };

        //购物车列表
        $(".menu-footer").on("click", function() {
            $(".menu-container .overlay").show();
            $(".shopcart-container").addClass("active");
        })
        $(".shopcart-operation").on("click", function() {
            $(".menu-container .overlay").hide();
            $(".shopcart-container").removeClass("active");
        })

        $(".menu-container .overlay").on("click", function() {
            $(".menu-container .overlay").hide();
            $(".shopcart-container").removeClass("active");
        })
        
        //加
        $(".cart-add").on("click", function() {
            $(this).parent().find(".cart-decrease").css({
                "display": "inline-block"
            });
            $(this).parent().find(".cart-count").css({
                "display": "inline-block"
            });
            //数量增加
            var tmp = parseInt($(this).parent().find(".cart-count").text());
            tmp += 1;
            $(this).parent().find(".cart-count").text(tmp);
            //计算总数
            var sum = 0;
            for(var i = 0; i < $(".cart-count").length; i++) {
                sum = sum + parseInt($(".cart-count").eq(i).text());
            }
            //购物车显示总数
            $(".shopping-wrapper .num").addClass("active");
            $(".shopping-wrapper .num").text(sum);
        })
        //减
        $(".cart-decrease").on("click", function() {
            //数量减少
            var tmp = parseInt($(this).parent().find(".cart-count").text());
            tmp -= 1;
            $(this).parent().find(".cart-count").text(tmp);
            //计算总数
            var sum = 0;
            for(var i = 0; i < $(".cart-count").length; i++) {
                sum = sum + parseInt($(".cart-count").eq(i).text());
            }
            //购物车显示总数
            $(".shopping-wrapper .num").text(sum);
            //少于0时隐藏减号
            if($(this).parent().find(".cart-count").text() == 0) {
                $(this).parent().find(".cart-decrease").hide();
                $(this).parent().find(".cart-count").hide();
            }
            //少于0时修改购物车颜色
            if($(".shopping-wrapper .num").text() == 0) {
                $(".shopping-wrapper .num").removeClass("active");
            }
        })
        
        //添加菜品动画效果
        $(".food-item .cart-add").on("click", addProduct);

        function addProduct(event) {
            var x = event.pageX - $(document).scrollLeft();
            var y = event.pageY - $(document).scrollTop();
            var t = $(document).scrollTop();
            var l = $(document).scrollLeft();
            var offset = $('.ball').offset();
            var flyer = $("<lable class='pointer'></label>");
            flyer.fly({
                start: {
                    left: x,//开始位置
                    top: y//开始位置
                },
                end: {
                    left: offset.left,//结束位置
                    top: offset.top,//结束位置
                    width: 10,//结束时宽度
                    height: 10//结束时高度
                },
                onEnd: function() { //结束回调
                    this.destroy(); //移除dom
                }
            });
        }
    }
</script>
```