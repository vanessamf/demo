# 长按弹出
## 实现效果 ##
?>  <a class="btn btn-success" href="https://vanessamf.github.io/psychological-counseling/chat.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

### html ###
```html
<body>
    <div class="container">
        <header class="header chat-header">
            <a href="javascript:history.back(-1)" class="back">
                <i class="iconfont icon-fanhui1"></i> 18
            </a>
            <span>陈一楠</span>
        </header>
        <div class="chat-container">
            <div class="time">11-30 下午9:30</div>
            <div class="item item-l">
                <div class="avatar">
                    <img src="images/891343.jpg" alt="" />
                </div>
                <div class="box">
                    <span>你好，在吗？</span>
                </div>
            </div>
            <div class="item item-r">
                <div class="avatar">
                    <img src="images/891343.jpg" alt="" />
                </div>
                <div class="box">
                    <span>嗯嗯，在的</span>
                </div>
            </div>
            <div class="item item-l">
                <div class="avatar">
                    <img src="images/891339.jpg" alt="" />
                </div>
                <div class="box">
                    <span>请问你需要咨询哪一方面的问题呢？adafafasd</span>
                </div>
            </div>
            <div class="time">11-30 下午11:30</div>
            <div class="item item-r">
                <div class="avatar">
                    <img src="images/891337.jpg" alt="" />
                </div>
                <div class="box">
                    <span>嗯嗯，在的</span>
                </div>
            </div>
        </div>
        <div class="chat-footer" id="chatFoot">
            <div class="voice" id="chatfootVoice">
                <i class="iconfont icon-yuyin"></i>
            </div>
            <div class="content" id="chatfootContent">
                <div class="text-box">
                    <span>按住说话</span>
                </div>
                <div class="input-wrapper">
                    <input type="text" />
                </div>
            </div>
            <div class="handle">
                <div class="emote">
                    <i class="iconfont icon-biaoqing"></i>
                </div>
                <div class="more">
                    <i class="iconfont icon-jia"></i>
                </div>
            </div>
        </div>
        <div id="toast" style=" opacity: 0; display: none;">
            <div class="weui-mask_transparent"></div>
            <div class="weui-toast">
                <i class="weui-icon-success-no-circle weui-icon_toast"></i>
                <p class="weui-toast__content">已完成</p>
            </div>
        </div>
    </div>
</body>
```


### 完整JS代码 ###
```javascript
<script type="text/javascript" class="searchbar js_show">
    $(function() {
        var $chatfootVoice = $('#chatfootVoice'),
            $chatFoot = $('#chatFoot');

        $chatfootVoice.on('click', function() {
            $chatFoot.toggleClass('focusing');
        });
        $(".text-box").on({
            touchstart: function(e) {
                e.preventDefault();
                timeOutEvent = setTimeout(function() {
                    //此处为长按事件-----在此显示遮罩层及删除按钮
                    $(".text-box").addClass("focusing");
                    $(".text-box span").text("松开结束");
                    $("#toast").css({
                        "opacity": "1",
                        "display": "block"
                    });
                    longClick = 1; //假如长按，则设置为1
                }, 500);
            },
            touchend: function(e) {
                clearTimeout(timeOutEvent);
                $(".text-box").removeClass("focusing");
                $(".text-box span").text("按住说话");
                $("#toast").css({
                    "opacity": "0",
                    "display": "none"
                });
            },
        })
    });
</script>
```