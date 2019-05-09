# 相册

## 实现效果 ##

?> <a class="btn btn-success" href="https://vanessamf.github.io/demos/gallery/index.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

```html
<section class="gallery-section" id="projects">
    <div class="container">
        <h2>个人作品</h2>
        <div class="col-md-3 col-sm-3 item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" class=""/>
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3  item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" class=""/>
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3  item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" class=""/>
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3 item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" />
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3  item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" class=""/>
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3 item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/580783.jpg" alt="" />
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3  item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" class=""/>
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-3 col-sm-3  item-container">
            <div class="item-wrapper">
                <div class="item-image">
                    <img src="img/touxiang.png" alt="" class=""/>
                    <div class="item-overlay "></div>
                    <div class="item-button">
                        <a href="javascript:void(0)">查看详情</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
```

```css
.gallery-section {
    background: rgba(249, 255, 89, 0.5);
}

.container {
    padding: 10% 0;
}

.item-container {}

/*@media (min-width: 768px) and (max-width:992px) {
    .item-container {
        width: 33.3%;
    }
}*/

@media (min-width: 320px) and (max-width:767px) {
    .item-container {
        width: 50%;
      float: left;
    }
}
@media (max-width:319px) {
    .item-container {
        width: 100%;
        float: left;
    }
}
/*图片包裹层 外边框*/
.item-wrapper {
    border: 1px solid #eee;
    padding: 5px;
    margin-top: 30px;
    /*height:250px;*/
}

.item-image {
    position: relative;
    overflow: hidden;
    /*width: 50%;*/
}

.item-image:before {
    content: "";
    display: block;
    padding-top: 100%;
    /*这里的 padding-top 是相对于元素的 width 的。*/
    /*padding-top: 100%;直接写到item-image上也行。*/
}

.item-image img {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
}


/*方式一*/
/*.item-button{
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0px;
    left: 0px;
    
    transform: scale(0);
    -webkit-transition: all 0.7s ease;
    transition: all 0.7s ease;
    background-color: rgba(249,255,89,0.3);
}

.item-wrapper:hover  .item-button {
-webkit-transform: scale(1);
transform: scale(1);
}*/

.item-overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    opacity: 0;
    -webkit-transition: opacity 0.5s ease-in 0s;
    -moz-transition: opacity 0.5s ease-in 0s;
    -o-transition: opacity 0.5s ease-in 0s;
    -ms-transition: opacity 0.5s ease-in 0s;
    transition: opacity 0.5s ease-in 0s;
    background-color: rgb(249, 255, 89);
}

.item-wrapper:hover .item-overlay {
    opacity: 0.3;
    /*background-color:rgba(249,255,89,0.3);*/
}

.item-button {
    text-align: center;
    position: absolute;
    left: 25%;
    right: 25%;
    bottom: 0;
    -webkit-transform: scale(0);
    -moz-transform: scale(0);
    -o-transform: scale(0);
    -ms-transform: scale(0);
    transform: scale(0);
    -webkit-transition: transform 0.7s ease;
    -moz-transition: transform 0.7s ease;
    -o-transition: transform 0.7s ease;
    -ms-transition: transform 0.7s ease;
    transition: transform 0.7s ease;
}

.item-wrapper:hover .item-button {
    -webkit-transform: scale(1);
    -moz-transform: scale(1);
    -o-transform: scale(1);
    -ms-transform: scale(1);
    transform: scale(1);
}

.item-button a {
    background: rgba(250, 142, 214, 0.6);
    /*text-transform: uppercase;*/
    font-size: 15px;
    letter-spacing: 2px;
    padding: 10px 15px;
}

.item-button a:focus {
    color: #fff;
}

.item-button a:hover {
    background: #FF8AD8;
    color: #fff;
}

.item-button a:focus,
.item-button a:link,
.item-button a:visited,
.item-button a:hover,
.item-button a:active {
    /*outline: 0;*/
    /*color:#fff;*/
    text-decoration: none;
}

```