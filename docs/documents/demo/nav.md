# 菜单
## 实现效果 ##
?>  <a class="btn btn-success" href="https://vanessamf.github.io/demos/nav/index.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

### html ###
```html
<div class="wrapper">
    <nav class="nav-menu">
        <a class="nav-trigger" href="#0">
            Menu
            <span aria-hidden="true"></span>
        </a>
        <ul>
            <li>
                <a href="#home"><span>主页</span></a>
            </li>
            <li>
                <a href="#about"><span>关于我</span></a>
            </li>
            <li>
                <a href="#skills"><span>知识技能</span></a>
            </li>
            <li>
                <a href="#experience"><span>工作经历</span></a>
            </li>
            <li>
                <a href="#education"><span>教育经历</span></a>
            </li>
            <li>
                <a href="#projects"><span>个人作品</span></a>
            </li>
            <li>
                <a href="#contact"><span>联系我</span></a>
            </li>
        </ul>
        <span class="nav-bg"></span>
    </nav>
</div>
```

### 未展开时的样子 ###
```css
.wrapper{
    height:3200px;
    background:#F3D250;
}
.nav-menu{
    position:fixed;
    top: 37px;
    right: 4%;
    z-index:2;
}
 /*未展开时的背景*/
.nav-menu .nav-bg{
    position: absolute;
    z-index: 1;
    top: 0;
    right: 0;
    width: 55px;
    height: 55px;
    border-radius: 30px;
    background:rgba(250,142,214, 0.8);
    
    -webkit-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
    -moz-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
    -o-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
    -ms-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
    
    -webkit-transition: height 0.2s, box-shadow 0.2s;
    -moz-transition: height 0.2s, box-shadow 0.2s; 
    -o-transition: height 0.2s, box-shadow 0.2s;
    -ms-transition: height 0.2s, box-shadow 0.2s;
    transition: height 0.2s, box-shadow 0.2s;
    /*背景展开高度动画和阴影动画*/
   
   
/*未展开时的按钮*/
.nav-trigger{
    position: absolute;
    z-index: 3;
    top: 0;
    right: 0;
    height: 55px;
    width: 55px;
    color: transparent !important;
}

.nav-trigger span,
.nav-trigger span::after,
.nav-trigger span::before{
    position: absolute;
    width: 23px;
    height: 2px;
    background-color: #ffffff;
}
.nav-trigger span{
    left: 50%;
    top: 50%;
    
    -webkit-transform: translateX(-50%) translateY(-50%);
    -moz-transform: translateX(-50%) translateY(-50%);
    -ms-transform: translateX(-50%) translateY(-50%);
    -o-transform: translateX(-50%) translateY(-50%);
    transform: translateX(-50%) translateY(-50%);
    /*过渡效果*/
    -webkit-transition: -webkit-transform 0.2s;
    -moz-transition: -moz-transform 0.2s;
    transition: transform 0.2s;
}
.nav-trigger span::after,
.nav-trigger span::before{
    content: '';
    top: 0;
    left: 0;
    
    -webkit-transition: -webkit-transform 0.2s;
    -moz-transition: -moz-transform 0.2s;
    transition: transform 0.2s;
}
.nav-trigger span::before {
    -webkit-transform: translateY(-7px);
    -moz-transform: translateY(-7px);
    -ms-transform: translateY(-7px);
    -o-transform: translateY(-7px);
    transform: translateY(-7px);
}
.nav-trigger span::after {
    -webkit-transform: translateY(7px);
    -moz-transform: translateY(7px);
    -ms-transform: translateY(7px);
    -o-transform: translateY(7px);
    transform: translateY(7px);
}
}
```

### 展开时的样子 ###
```css
.nav-menu .nav-trigger:hover ~ .nav-bg {
    /*background:#2B542C;*/
    -webkit-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    -moz-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    -o-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    -ms-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
}
/*显示展开背景*/
.nav-menu.navShow .nav-bg{
    height: 100%;
    -webkit-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    -moz-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    -ms-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    -o-box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
    box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
}

/*展开时的按钮*/
/*显示menu*/
.nav-menu.navShow .nav-trigger span {
    background-color: transparent;
}
/*显示menu动画*/
.nav-menu.navShow .nav-trigger span::before {
    -webkit-transform: rotate(-45deg);
    -moz-transform: rotate(-45deg);
    -ms-transform: rotate(-45deg);
    -o-transform: rotate(-45deg);
    transform: rotate(-45deg);
}
.nav-menu.navShow .nav-trigger span::after {
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    transform: rotate(45deg);
}
```

### 未展开时的菜单 ###
```css
/*未展开时的菜单*/
.nav-menu ul{
    position: relative;
    z-index: 2;
    padding: 60px 0 10px; 
    visibility: hidden;
}
```

### 展开时的菜单 ###
```css
.nav-menu.navShow ul {
    visibility: visible;
}
.nav-menu ul li {
}
.nav-menu ul a {
    position: relative;
    width: 55px;
    height: 40px;
    color: rgba(255, 255, 255, 0.7); 
}
.nav-menu ul a::after {
    content: "\f015";
    position: absolute;
    right: 19px;
    top: 50%;

    opacity: .6;
    font: 14px/1 FontAwesome;
    font-size:1.2em;
} 
.nav-menu ul li:nth-of-type(2) a::after {
    content: "\f05a";
}
.nav-menu ul li:nth-of-type(3) a::after {
    content: "\f085";
}
.nav-menu ul li:nth-of-type(4) a::after {
    content: "\f0f2";
}
.nav-menu ul li:nth-of-type(5) a::after {
    content: "\f02d";
}
.nav-menu ul li:nth-of-type(6) a::after {
     content: "\f03e";
}
.nav-menu ul li:nth-of-type(7) a::after {
    content: "\f003";
}
.nav-menu ul .cur-page::after{
    color: #ffffff;
    opacity: 1;
}
/*显示a*/
.nav-menu.navShow ul a::after {
    /*transform: translateY(-50%) scale(0);*/
    /*both应用开始属性和保留最后一个属性*/
    -webkit-animation: scaleIn 0.15s both;
    -moz-animation: scaleIn 0.15s both;
    animation: scaleIn 0.15s both;
}

.nav-menu.navShow ul li:first-of-type a::after,
.nav-menu.navShow ul li:first-of-type span {
    -webkit-animation-delay: 0.05s;
    -moz-animation-delay: 0.05s;
    animation-delay: 0.05s;
}
.nav-menu.navShow ul li:nth-of-type(2) a::after,
.nav-menu.navShow ul li:nth-of-type(2) span {
    -webkit-animation-delay: 0.1s;
    -moz-animation-delay: 0.1s;
    animation-delay: 0.1s;
}

.nav-menu.navShow ul li:nth-of-type(3) a::after,
.nav-menu.navShow ul li:nth-of-type(3) span {
    -webkit-animation-delay: 0.15s;
    -moz-animation-delay: 0.15s;
    animation-delay: 0.15s;
}
.nav-menu.navShow ul li:nth-of-type(4) a::after,
.nav-menu.navShow ul li:nth-of-type(4) span {
    -webkit-animation-delay: 0.2s;
    -moz-animation-delay: 0.2s;
    animation-delay: 0.2s;
}
.nav-menu.navShow ul li:nth-of-type(5) a::after,
.nav-menu.navShow ul li:nth-of-type(5) span {
    -webkit-animation-delay: 0.25s;
    -moz-animation-delay: 0.25s;
    animation-delay: 0.25s;
}
.nav-menu.navShow ul li:nth-of-type(6) a::after,
.nav-menu.navShow ul li:nth-of-type(6) span {
    -webkit-animation-delay: 0.3s;
    -moz-animation-delay: 0.3s;
    animation-delay: 0.3s;
}
.nav-menu.navShow ul li:nth-of-type(7) a::after,
.nav-menu.navShow ul li:nth-of-type(7) span {
    -webkit-animation-delay: 0.35s;
    -moz-animation-delay: 0.35s;
    animation-delay: 0.35s;
}
/*跟下面的效果一样*/
 /*keyframes scaleIn {
    0% {transform: translateY(-50%) scale(0); }
}*/

@-webkit-keyframes scaleIn {
  from {
    -webkit-transform: translateY(-50%) scale(0);
  }
  to {
    -webkit-transform: translateY(-50%) scale(1);
  }
}
@-moz-keyframes scaleIn {
  from {
    -moz-transform: translateY(-50%) scale(0);
  }
  to {
    -moz-transform: translateY(-50%) scale(1);
  }
}

@keyframes scaleIn {
  from {
    -webkit-transform: translateY(-50%) scale(0);
    -moz-transform: translateY(-50%) scale(0);
    -ms-transform: translateY(-50%) scale(0);
    -o-transform: translateY(-50%) scale(0);
    transform: translateY(-50%) scale(0);
  }
  to {
    -webkit-transform: translateY(-50%) scale(1);
    -moz-transform: translateY(-50%) scale(1);
    -ms-transform: translateY(-50%) scale(1);
    -o-transform: translateY(-50%) scale(1);
    transform: translateY(-50%)  scale(1);
  }
 } 
 
.nav-menu.navShow ul a:hover::after{
    color: #ffffff;
    opacity: 1;
}
```

### 文字描述 ###

```css
.nav-menu ul span {
    position: absolute;
    top: 6px;
    right: 64px;
    height: 30px;
    width:100px;
    line-height: 30px;
    padding: 0 10px;
    opacity: 0;
    background-color: rgba(0, 0, 0, 0.55);
    border-radius: 2px;
    text-align: center;
    font-size: 1.1em;
    font-weight: 300;
    /*font-family:'Montserrat', sans-serif;*/
}
/*小三角*/
.nav-menu ul span::after {
  /* triangle below the tooltip */
  content: '';
  position: absolute;
  left: 100%;
  top: 50%;
  bottom: auto;
  -webkit-transform: translateY(-50%);
  -moz-transform: translateY(-50%);
  -ms-transform: translateY(-50%);
  -o-transform: translateY(-50%);
  transform: translateY(-50%);
  height: 0;
  width: 0;
  border: 4px solid transparent;
  border-left-color: rgba(0, 0, 0, 0.55);
}

/*显示span*/
.nav-menu.navShow ul a:hover span{
    opacity: 1; 
    animation: scaleIn2 0.15s both;
}

@keyframes scaleIn2 {                          
from {transform: scale(0); }  
to {transform: scale(1); }
}
```

### js ###

```javascript
if($('.nav-menu').length > 0) {
    var navMenu = $('.nav-menu');

    navMenu.each(function() {
        var navMenu = $(this);
        var snavMenuTrigger = navMenu.find('.nav-trigger');

        snavMenuTrigger.on('click', function(event) {
            event.preventDefault();
            navMenu.toggleClass('navShow');
        });
    });

    $(document).on('click', function(event) {
        (!$(event.target).is('.nav-trigger') && !$(event.target).is('.nav-trigger span')) && navMenu.removeClass('navShow');
    });
}

$(".nav-menu ul a").click(function() {
    $(".nav-menu ul li a").removeClass("cur-page");
    $(this).addClass("cur-page");
});

$(window).on('scroll', function() {
    if($(window).scrollTop() < 500) {
        $(".nav-menu ul li a").removeClass("cur-page");
        $(".nav-menu ul li:nth-child(1) a").addClass("cur-page");
    }
    if($(window).scrollTop() >= 500) {
        $(".nav-menu ul li a").removeClass("cur-page");
        $(".nav-menu ul li:nth-child(2) a").addClass("cur-page");
    }
})
```