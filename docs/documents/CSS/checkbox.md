# 单选/复选框

## 实现效果 ##

?> 单选/复选框样式
<a class="btn btn-success" href="https://vanessamf.github.io/demos/checked/index3.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

?>

## 具体过程 ##
### <span id="item_1" class="inline-toc">1.</span> 第一种 ###

![avatar](../../images/checkbox/checkbox1.png ':size=100') 


```html
<h3>magic<br/>默认</h3>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-radio" type="radio" name="radio" id="r1" value="1" checked="">
        <label for="r1">男</label>
    </div>
    <div class="gender">
        <input class="magic-radio" type="radio" name="radio" id="r2" value="2">
        <label for="r2">女</label>
    </div>
</div>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-radio" type="radio" name="radio2" id="r23" value="2" checked="checked" disabled="disabled">
        <label for="r23">男</label>
    </div>
    <div class="gender">
        <input class="magic-radio" type="radio" name="radio2" id="r24" value="2" disabled="disabled">
        <label for="r24">女</label>
    </div>
</div>
<div class="fruit-wrapper">
    <div class="fruit">
        <input class="magic-checkbox" type="checkbox" name="checkbox" id="r3" value="1" checked="">
        <label for="r3">草莓</label>
    </div>
    <div class="fruit">
        <input class="magic-checkbox" type="checkbox" name="checkbox" id="r4" value="2">
        <label for="r4">苹果</label>
    </div>
    
    <div class="fruit">
        <input class="magic-checkbox" type="checkbox" name="checkbox" id="r6" value="2" checked="checked" disabled="disabled">
        <label for="r5">香蕉</label>
    </div>
    <div class="fruit">
        <input class="magic-checkbox" type="checkbox" name="checkbox" id="r6" value="2" disabled="disabled">
        <label for="r6">樱桃</label>
    </div>
</div>
```

```css
.magic-radio,
.magic-checkbox {
    position: absolute;
    display: none;
}
.magic-radio+label,
.magic-checkbox+label {
    position: relative;
    display: block;
    padding-left: 30px;
    cursor: pointer;
    vertical-align: middle;
}
@keyframes hover-color {
    from {
        border-color: #c0c0c0;
    }
    to {
        border-color: #3e97eb;
    }
}
 /*hover添加边框颜色*/
.magic-radio+label:hover:before,
.magic-checkbox+label:hover:before {
    animation-duration: 0.4s;
    animation-fill-mode: both;
    animation-name: hover-color;
}

/*选中前公共边框样式*/
.magic-radio+label:before,
.magic-checkbox+label:before {
    position: absolute;
    top: 0;
    left: 0;
    display: inline-block;
    width: 20px;
    height: 20px;
    content: '';
    border: 1px solid #c0c0c0;
}
/*选中前radio边框样式*/
.magic-radio+label:before {
    border-radius: 50%;
}
/*选中前checkbox边框样式*/
.magic-checkbox+label:before {
    border-radius: 3px;
}

/*选中后公共边框样式*/
.magic-radio:checked+label:before,
.magic-checkbox:checked+label:before {
    animation-name: none;
}
/*选中后radio边框样式*/
.magic-radio:checked+label:before {
    border: 1px solid #3e97eb;
}
/*选中后checkbox边框和背景样式*/
.magic-checkbox:checked+label:before {
    /*border: #3e97eb;*/
    border: 1px solid #3e97eb;
    background: #3e97eb;
}

/*选中前公共内容样式*/
.magic-radio+label:after,
.magic-checkbox+label:after {
    position: absolute;
    display: none;
    content: '';
}

/*选中后公共内容样式*/
.magic-radio:checked+label:after,
.magic-checkbox:checked+label:after {
    display: block;
}
/*选中后radio内容样式*/
.magic-radio:checked+label:after {
    top: 7px;
    left: 7px;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #3e97eb;
}
/*选中后checkbox内容样式*/
.magic-checkbox:checked+label:after {
    /*top: 2px;
    left: 7px;*/
    top: 3px;
    left: 8px;
    box-sizing: border-box;
    width: 6px;
    height: 12px;
    transform: rotate(45deg);
    border-width: 2px;
    border-style: solid;
    border-color: #fff;
    border-top: 0;
    border-left: 0;
}
/*disabled效果*/
.magic-radio[disabled],
.magic-checkbox[disabled] {
    cursor: not-allowed;
}

.magic-radio[disabled]+label,
.magic-checkbox[disabled]+label {
    cursor: not-allowed;
    color: #e4e4e4;
}

.magic-radio[disabled]+label:before,
.magic-checkbox[disabled]+label:before {
    border-color: #e4e4e4;
}

.magic-radio[disabled]+label:hover,
.magic-radio[disabled]+label:before,
.magic-radio[disabled]+label:after,
.magic-checkbox[disabled]+label:hover,
.magic-checkbox[disabled]+label:before,
.magic-checkbox[disabled]+label:after {
    cursor: not-allowed;
}
/*防止hover添加之前的边框颜色*/
.magic-radio[disabled]+label:hover:before,
.magic-checkbox[disabled]+label:hover:before {
    border: 1px solid #e4e4e4;
    animation-name: none;
}

/*选中后disabled radio边框颜色*/
.magic-radio:checked[disabled]+label:before {
    border: 1px solid #c9e2f9;
}
/*选中后disabled radion内容颜色*/
.magic-radio:checked[disabled]+label:after {
    background: #c9e2f9;
}
/*选中后disabled checkbox边框和背景色*/
.magic-checkbox:checked[disabled]+label:before {
    /*border: #c9e2f9;*/
    border: 1px solid #c9e2f9;
    background: #c9e2f9;
}
```

### <span id="item_1" class="inline-toc">2.</span>换颜色 ###

![avatar](../../images/checkbox/checkbox2.png ':size=100') 

```html
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-radio magic-green" type="radio" name="radio9" id="r91" value="1" checked="">
        <label for="r91">男</label>
    </div>
    <div class="gender">
        <input class="magic-radio magic-green" type="radio" name="radio9" id="r92" value="2">
        <label for="r92">女</label>
    </div>
</div>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-radio magic-green" type="radio" name="radio99" id="r23" value="93" checked="checked" disabled="disabled">
        <label for="r93">男</label>
    </div>
    <div class="gender">
        <input class="magic-radio magic-green" type="radio" name="radio99" id="r24" value="94" disabled="disabled">
        <label for="r94">女</label>
    </div>
</div>
<div class="fruit-wrapper">
    <div class="gender">
        <input class="magic-checkbox magic-green" type="checkbox" name="checkbox10" id="r101" value="1" checked="">
        <label for="r101">草莓</label>
    </div>
    <div class="fruit">
        <input class="magic-checkbox magic-green" type="checkbox" name="checkbox10" id="r102" value="2">
        <label for="r102">苹果</label>
    </div>
    
    <div class="fruit">
        <input class="magic-checkbox magic-green" type="checkbox" name="checkbox10" id="r103" value="2" checked="checked" disabled="disabled">
        <label for="r103">香蕉</label>
    </div>
    <div class="fruit">
        <input class="magic-checkbox magic-green" type="checkbox" name="checkbox10" id="r104" value="2" disabled="disabled">
        <label for="r104">樱桃</label>
    </div>
</div>
```

```css
@keyframes hover-color-green {
    from {
        border-color: #c0c0c0;
    }
    to {
        border-color: #0eb58c;
    }
}
.magic-radio.magic-green+label:hover:before,
.magic-checkbox.magic-green+label:hover:before {
    animation-name: hover-color-green;
}
.magic-radio.magic-green[disabled]+label:hover:before,
.magic-checkbox.magic-green[disabled]+label:hover:before {
    border: 1px solid #e4e4e4;
    animation-name: none;
}

/*选中后radio边框颜色*/
.magic-radio.magic-green:checked+label:before {
    border: 1px solid #0eb58c;
}
/*选中后radio内容颜色*/
.magic-radio.magic-green:checked+label:after {
    background: #0eb58c;
}
/*选中后disabled radio边框颜色*/
.magic-radio.magic-green:checked[disabled]+label:before {
    border: 1px solid #bbe6dc;
}
/*选中后disabled radio内容颜色*/
.magic-radio.magic-green:checked[disabled]+label:after {
    background: #bbe6dc;
}
/*选中后checkbox边框和背景颜色*/
.magic-checkbox.magic-green:checked+label:before {
    border: 1px solid #0eb58c;
    background: #0eb58c;
}
/*选中后disabled checkbox边框和背景色*/
.magic-checkbox.magic-green:checked[disabled]+label:before {
    border: 1px solid #bbe6dc;
    background: #bbe6dc;
}
```

### <span id="item_1" class="inline-toc">3.</span>第二种 ###

![avatar](../../images/checkbox/checkbox3.png ':size=100') 

```html
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio" type="radio" name="radio5" id="r51" value="1" checked="">
        <label for="r51">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio" type="radio" name="radio5" id="r52" value="2">
        <label for="r52">女</label>
    </div>
</div>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio" type="radio" name="radio55" id="r53" value="2" checked="checked" disabled="disabled">
        <label for="r53">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio" type="radio" name="radio55" id="r54" value="2" disabled="disabled">
        <label for="r54">女</label>
    </div>
</div>
<div class="fruit-wrapper">
    <div class="fruit">
        <input class="magic-square-checkbox" type="checkbox" name="checkbox6" id="r61" value="1" checked="">
        <label for="r61">草莓</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox" type="checkbox" name="checkbox6" id="r62" value="2">
        <label for="r62">苹果</label>
    </div>
    
    <div class="fruit">
        <input class="magic-square-checkbox" type="checkbox" name="checkbox6" id="r63" value="2" checked="checked" disabled="disabled">
        <label for="r63">香蕉</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox" type="checkbox" name="checkbox6" id="r64" value="2" disabled="disabled">
        <label for="r64">樱桃</label>
    </div>
</div>
```

```css
.magic-square-radio,
.magic-square-checkbox {
    position: absolute;
    display: none;
}

.magic-square-radio+label,
.magic-square-checkbox+label {
    position: relative;
    display: block;
    padding-left: 30px;
    cursor: pointer;
    vertical-align: middle;
}
@keyframes square-hover-color {
    from {
        border-color: #c0c0c0;
    }
    to {
        border-color: #3e97eb;
    }
}
/*hover添加边框颜色*/
.magic-square-radio+label:hover:before,
.magic-square-checkbox+label:hover:before {
    animation-duration: 0.4s;
    animation-fill-mode: both;
    animation-name: square-hover-color;
}
/*选中前公共边框样式*/
.magic-square-radio+label:before,
.magic-square-checkbox+label:before {
    position: absolute;
    top: 0;
    left: 0;
    display: inline-block;
    width: 20px;
    height: 20px;
    content: '';
    border: 1px solid #c0c0c0;
}
/*选中前radio边框样式*/
.magic-square-radio+label:before {
    border-radius: 50%;
}
/*选中前checkbox边框样式*/
.magic-square-checkbox+label:before {
    border-radius: 3px;
}
/*选中后公共边框和背景颜色*/
.magic-square-radio:checked+label:before,
.magic-square-checkbox:checked+label:before {
    animation-name: none;
    border: 1px solid #3e97eb;
    background: #3e97eb;
}
.magic-square-radio:checked+label:before,
.magic-square-checkbox:checked+label:before {
    /*border: #3e97eb;*/
}
/*选中前公共内容样式*/
.magic-square-radio+label:after,
.magic-square-checkbox+label:after {
    position: absolute;
    display: none;
    content: '';
}
/*选中后公共内容样式*/
.magic-square-radio:checked+label:after,
.magic-square-checkbox:checked+label:after {
    display: block;
}
/*选中后公共内容样式*/
.magic-square-radio:checked+label:after,
.magic-square-checkbox:checked+label:after {
    /*top: 2px;
    left: 7px;*/
    top: 3px;
    left: 8px;
    box-sizing: border-box;
    width: 6px;
    height: 12px;
    transform: rotate(45deg);
    border-width: 2px;
    border-style: solid;
    border-color: #fff;
    border-top: 0;
    border-left: 0;
}
/*disabled效果*/
.magic-square-radio[disabled],
.magic-square-checkbox[disabled] {
    cursor: not-allowed;
}
.magic-square-radio[disabled]+label,
.magic-square-checkbox[disabled]+label {
    cursor: not-allowed;
    color: #e4e4e4;
}
.magic-square-radio[disabled]+label:before,
.magic-square-checkbox[disabled]+label:before {
    border-color: #e4e4e4;
}
.magic-square-radio[disabled]+label:hover,
.magic-square-radio[disabled]+label:before,
.magic-square-radio[disabled]+label:after,
.magic-square-checkbox[disabled]+label:hover,
.magic-square-checkbox[disabled]+label:before,
.magic-square-checkbox[disabled]+label:after {
    cursor: not-allowed;
}
/*防止hover添加之前的边框颜色*/
.magic-square-radio[disabled]+label:hover:before,
.magic-square-checkbox[disabled]+label:hover:before {
    border: 1px solid #e4e4e4;
    animation-name: none;
}

/*选中后disabled 公共边框和背景色*/
.magic-square-radio:checked[disabled]+label:before,
.magic-square-checkbox:checked[disabled]+label:before {
    /*border: #c9e2f9;*/
    border: 1px solid #c9e2f9;
    background: #c9e2f9;
}
```

### <span id="item_1" class="inline-toc">4.</span>换颜色 ###

![avatar](../../images/checkbox/checkbox4.png ':size=100') 

```html
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio magic-green" type="radio" name="radio7" id="r71" value="1" checked="">
        <label for="r71">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio magic-green" type="radio" name="radio7" id="r72" value="2">
        <label for="r72">女</label>
    </div>
</div>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio magic-green" type="radio" name="radio77" id="r73" value="2" checked="checked" disabled="disabled">
        <label for="r73">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio magic-green" type="radio" name="radio77" id="r54" value="2" disabled="disabled">
        <label for="r74">女</label>
    </div>
</div>
<div class="fruit-wrapper">
    <div class="fruit">
        <input class="magic-square-checkbox magic-green" type="checkbox" name="checkbox8" id="r81" value="1" checked="">
        <label for="r81">草莓</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox magic-green" type="checkbox" name="checkbox8" id="r82" value="2">
        <label for="r82">苹果</label>
    </div>
    
    <div class="fruit">
        <input class="magic-square-checkbox magic-green" type="checkbox" name="checkbox8" id="r83" value="2" checked="checked" disabled="disabled">
        <label for="r83">香蕉</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox magic-green" type="checkbox" name="checkbox8" id="r84" value="2" disabled="disabled">
        <label for="r84">樱桃</label>
    </div>
</div>
```

```css
/*magic-square magic-green*/
/*选中后disabled 公共边框和背景色*/
@keyframes square-hover-color-green {
    from {
        border-color: #c0c0c0;
    }
    to {
        border-color: #0eb58c;
    }
}

.magic-square-radio.magic-green+label:hover:before,
.magic-square-checkbox.magic-green+label:hover:before {
    animation-name: square-hover-color-green;
}

/*选中后公共边框和背景颜色*/
.magic-square-radio.magic-green:checked+label:before,
.magic-square-checkbox.magic-green:checked+label:before {
    border: 1px solid #0eb58c;
    background: #0eb58c;
}

/*防止hover添加之前的边框颜色*/
.magic-square-radio.magic-green[disabled]+label:hover:before,
.magic-square-checkbox.magic-green[disabled]+label:hover:before {
    border: 1px solid #e4e4e4;
    animation-name: none;
}
/*选中后disabled 公共边框和背景色*/
.magic-square-radio.magic-green:checked[disabled]+label:before,
.magic-square-checkbox.magic-green:checked[disabled]+label:before {
    border: 1px solid #bbe6dc;
    background: #bbe6dc;
}
```

### <span id="item_1" class="inline-toc">5.</span>第三种 ###

![avatar](../../images/checkbox/checkbox5.png ':size=100') 

```html
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio2  magic-scale" type="radio" name="radio912" id="r991" value="1" checked="">
        <label for="r991">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio2  magic-scale" type="radio" name="radio912" id="r992" value="2">
        <label for="r992">女</label>
    </div>
</div>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio2  magic-scale" type="radio" name="radio191" id="r993" value="2" checked="checked" disabled="disabled">
        <label for="r993">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio2  magic-scale" type="radio" name="radio191" id="r994" value="2" disabled="disabled">
        <label for="r994">女</label>
    </div>
</div>
<div class="fruit-wrapper">
    <div class="fruit">
        <input class="magic-square-checkbox2 magic-scale" type="checkbox" name="checkbox12" id="r921" value="1" checked="">
        <label for="r921">草莓</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox2  magic-scale" type="checkbox" name="checkbox12" id="r922" value="2">
        <label for="r922">苹果</label>
    </div>
    
    <div class="fruit">
        <input class="magic-square-checkbox2  magic-scale" type="checkbox" name="checkbox12" id="r923" value="2" checked="checked" disabled="disabled">
        <label for="r923">香蕉</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox2  magic-scale" type="checkbox" name="checkbox12" id="r924" value="2" disabled="disabled">
        <label for="r924">樱桃</label>
    </div>
</div>
```

```css
/*scale*/
/*背景在after上*/
.magic-square-radio2,
.magic-square-checkbox2 {
    position: absolute;
    display: none;
}

.magic-square-radio2+label,
.magic-square-checkbox2+label {
    position: relative;
    display: block;
    padding-left: 30px;
    cursor: pointer;
    vertical-align: middle;
}
@keyframes hover-color2 {
    from {
        border-color: #c0c0c0;
    }
    to {
        border-color: #0eb58c;
    }
}
/*hover添加边框颜色*/
.magic-square-radio2+label:hover:before,
.magic-square-checkbox2+label:hover:before {
    animation-duration: 0.4s;
    animation-fill-mode: both;
    animation-name: hover-color2;
}
/*选中前公共边框样式*/
.magic-square-radio2+label:before,
.magic-square-checkbox2+label:before {
    position: absolute;
    top: 0;
    left: 0;
    display: inline-block;
    width: 20px;
    height: 20px;
    content: '';
    border: 1px solid #c0c0c0;
}
/*选中前radio边框样式*/
.magic-square-radio2+label:before {
    border-radius: 50%;
}
/*选中前checkbox边框样式*/
.magic-square-checkbox2+label:before {
    border-radius: 3px;
}
/*选中后公共边框颜色*/
.magic-square-radio2:checked+label:before,
.magic-square-checkbox2:checked+label:before {
    animation-name: none;
    border: 1px solid #3e97eb;
}
/*选中前公共内容样式*/
.magic-square-radio2+label:after,
.magic-square-checkbox2+label:after {
    position: absolute;
    content: "\f00c";
    font-size: 14px;
    font-family: FontAwesome;
    font-weight: 400;
    text-align: center;
    top: 1px;
    left: 1px;
    color: #fff;
    box-sizing: border-box;
    width: 20px;
    height: 20px;
    background: #3e97eb;
}
/*选中前radio内容样式*/
.magic-square-radio2+label:after{
    border-radius: 50%;
}
/*选中后公共内容样式*/
.magic-square-radio2:checked+label:after,
.magic-square-checkbox2:checked+label:after {
    display: block;
}

/*disabled效果*/
.magic-square-radio2[disabled],
.magic-square-checkbox2[disabled] {
    cursor: not-allowed;
}

.magic-square-radio2[disabled]+label,
.magic-square-checkbox2[disabled]+label {
    cursor: not-allowed;
    color: #e4e4e4;
}

.magic-square-radio2[disabled]+label:before,
.magic-square-checkbox2[disabled]+label:before {
    border-color: #e4e4e4;
}

.magic-square-radio2[disabled]+label:hover,
.magic-square-radio2[disabled]+label:before,
.magic-square-radio2[disabled]+label:after,
.magic-square-checkbox2[disabled]+label:hover,
.magic-square-checkbox2[disabled]+label:before,
.magic-square-checkbox2[disabled]+label:after {
    cursor: not-allowed;
}
/*防止hover添加之前的边框颜色*/
.magic-square-radio2[disabled]+label:hover:before,
.magic-square-checkbox2[disabled]+label:hover:before {
    border: 1px solid #e4e4e4;
    animation-name: none;
}
/*选中后disabled 公共边框颜色*/
.magic-square-radio2:checked[disabled]+label:before,
.magic-square-checkbox2:checked[disabled]+label:before {
    /*border: #c9e2f9;*/
    border: 1px solid #c9e2f9;
}
/*选中后disabled 公共内容颜色*/
.magic-square-radio2:checked[disabled]+label:after,
.magic-square-checkbox2:checked[disabled]+label:after {
    /*border: #c9e2f9;*/
    background: #c9e2f9;
}

/*选中前内容缩放*/
.magic-square-radio2.magic-scale+label:after,
.magic-square-checkbox2.magic-scale+label:after{
    opacity: 0;
    -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=0)";
    -webkit-transform: scale(0.3);
    transform: scale(0.3);
    -webkit-transition: opacity .25s linear, -webkit-transform .25s linear;
    transition: opacity .25s linear, -webkit-transform .25s linear;
    transition: opacity .25s linear, transform .25s linear;
    transition: opacity .25s linear, transform .25s linear, -webkit-transform .25s linear;
}
/*选中后内容缩放*/
.magic-square-radio2.magic-scale:checked+label:after,
.magic-square-checkbox2.magic-scale:checked+label:after {
    opacity: 1;
    -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=100)";
    -webkit-transform: scale(1);
    transform: scale(1);
}
```

### <span id="item_1" class="inline-toc">6.</span>换颜色 ###

![avatar](../../images/checkbox/checkbox6.png ':size=100')

```html
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio2 magic-orange magic-scale" type="radio" name="radio11" id="r111" value="1" checked="">
        <label for="r111">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio2 magic-orange magic-scale" type="radio" name="radio11" id="r112" value="2">
        <label for="r112">女</label>
    </div>
</div>
<div class="gender-wrapper">
    <div class="gender">
        <input class="magic-square-radio2 magic-orange magic-scale" type="radio" name="radio111" id="r113" value="2" checked="checked" disabled="disabled">
        <label for="r113">男</label>
    </div>
    <div class="gender">
        <input class="magic-square-radio2 magic-orange magic-scale" type="radio" name="radio111" id="r114" value="2" disabled="disabled">
        <label for="r114">女</label>
    </div>
</div>
<div class="fruit-wrapper">
    <div class="fruit">
        <input class="magic-square-checkbox2 magic-orange magic-scale" type="checkbox" name="checkbox12" id="r121" value="1" checked="">
        <label for="r121">草莓</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox2 magic-orange magic-scale" type="checkbox" name="checkbox12" id="r122" value="2">
        <label for="r122">苹果</label>
    </div>
    
    <div class="fruit">
        <input class="magic-square-checkbox2 magic-orange magic-scale" type="checkbox" name="checkbox12" id="r123" value="2" checked="checked" disabled="disabled">
        <label for="r123">香蕉</label>
    </div>
    <div class="fruit">
        <input class="magic-square-checkbox2 magic-orange magic-scale" type="checkbox" name="checkbox12" id="r124" value="2" disabled="disabled">
        <label for="r124">樱桃</label>
    </div>
</div>
``` 

```css
/*magic-square magic-orange magic-scale*/
@keyframes hover-color-orange {
    from {
        border-color: #c0c0c0;
    }
    to {
        border-color: #ea923c;
    }
}
.magic-square-radio2.magic-orange+label:hover:before,
.magic-square-checkbox2.magic-orange+label:hover:before {
    animation-name: hover-color-orange;
}
/*选中后公共边框颜色*/
.magic-square-radio2.magic-orange:checked+label:before,
.magic-square-checkbox2.magic-orange:checked+label:before {
    border: 1px solid #ea923c;
}
/*选中后公共背景颜色*/
.magic-square-radio2.magic-orange+label:after,
.magic-square-checkbox2.magic-orange+label:after {
    background: #ea923c;
}
/*防止hover添加之前的边框颜色*/
.magic-square-radio2.magic-orange[disabled]+label:hover:before,
.magic-square-checkbox2.magic-orange[disabled]+label:hover:before {
    border: 1px solid #e4e4e4;
    animation-name: none;
}
/*选中后disabled 公共边框色*/
.magic-square-radio2.magic-orange:checked[disabled]+label:before,
.magic-square-checkbox2.magic-orange:checked[disabled]+label:before {
    border: 1px solid #f5cba2;
}
/*选中后disabled 公共背景色*/
.magic-square-radio2.magic-orange:checked[disabled]+label:after,
.magic-square-checkbox2.magic-orange:checked[disabled]+label:after {
    background: #f5cba2;
}
```