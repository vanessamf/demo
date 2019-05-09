# 安全检测
## 实现效果 ##
?>  <a class="btn btn-success" href="https://vanessamf.github.io/demos/detection/index.html" role="button" target="_blank">
查看演示
</a>

## 实现方式 ##

## 具体过程 ##

### html ###
```html
 <body>
    <div class="detection-wrapper">
        <!--<section class="content-header p-2" style="">
            <div class="container-fluid p-1">
                <div class="row justify-content-center position-relative">
                    <h1>安全检测</h1>
                </div>
            </div>
        </section>-->

        <section class="content">
            <div class="title">
                 <h1 >安全检测</h1>
            </div>
            
            <div class="detection-container">
                <div class="detection-content">
                    <div class="text-wrapper">
                        <span class="num" id="counter">100</span>
                        <span class="text">分</span>
                    </div>
                </div>
                <div class="loader">Loading...</div>
                <a href="javascript:void(0)" class="detection-btn uncheck btn btn-sm btn-outline-info">立即检测</a>
            </div>
            <div class="detection-detail">
                <ul>
                </ul>
            </div>
        </section>
    </div>
    <!--弹框-->
    <div class="modal fade in" id="detectionModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel">
        <div class="modal-dialog sm-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header bg-base">
                    <h4 class="modal-title" id="myModalLabel">提示</h4></div>
                <div class="modal-body">
                    <div class="detection-result-detail">
                        <ul>
                            <li>
                                <i class="fa fa-exclamation-circle"></i>
                                手机剩余空间较低1
                            </li>
                            <li>
                                <i class="fa fa-exclamation-circle"></i>
                                手机剩余空间较低2
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>
```

### CSS ###
```css
/*安全监测*/
html,body{
    height:100%;
}
.detection-wrapper{
    height:100%;
}
.detection-wrapper .content{
    position: relative;
    height: 100%;
        overflow: hidden;
        background: #eee;
}
.detection-wrapper .content .title{
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    width:100%;
        height: 3rem;
}
.detection-wrapper .content .title h1{
    font-size: 1.3rem;
    font-weight: 400;
     color:#fff;
}
.detection-container {
    display: flex;
    align-items: center;
    flex-direction: column;
    background: #40c8de;
    color: #fff;
    height: 100%;
    transition: all .5s;
    -webkit-transition: all .5s;
}

.detection-container.active {
    height: 80%;
}
.detection-container.actived {
    height: 60%;
}
.detection-content {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 6.3rem;
    width: 10rem;
    height: 10rem;
    border: 1px solid #fff;
    border-radius: 50%;
}

.detection-content.active {
    border: none;
}

.detection-content .num {
    font-size: 48px;
    font-weight: 600;
}

.detection-content .text {}

.loader {
    position: absolute;
    margin: 11rem auto;
    /*margin: 5.5em auto;*/
    font-size: 25px;
    width: 1em;
    height: 1em;
    border-radius: 50%;
    text-indent: -9999em;
}

.loader.active {
    -webkit-animation: load5 1.1s infinite ease;
    animation: load5 1.1s infinite ease;
}


/*@-webkit-keyframes load5 {
  0%,
  100% {
    box-shadow: 0em -2.6em 0em 0em #ffffff, 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2), 2.5em 0em 0 0em rgba(255, 255, 255, 0.2), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.2), 0em 2.5em 0 0em rgba(255, 255, 255, 0.2), -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.2), -2.6em 0em 0 0em rgba(255, 255, 255, 0.5), -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.7);
  }
  12.5% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.7), 1.8em -1.8em 0 0em #ffffff, 2.5em 0em 0 0em rgba(255, 255, 255, 0.2), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.2), 0em 2.5em 0 0em rgba(255, 255, 255, 0.2), -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.2), -2.6em 0em 0 0em rgba(255, 255, 255, 0.2), -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.5);
  }
  25% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.5), 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.7), 2.5em 0em 0 0em #ffffff, 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.2), 0em 2.5em 0 0em rgba(255, 255, 255, 0.2), -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.2), -2.6em 0em 0 0em rgba(255, 255, 255, 0.2), -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2);
  }
  37.5% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.2), 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.5), 2.5em 0em 0 0em rgba(255, 255, 255, 0.7), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.2), 0em 2.5em 0 0em rgba(255, 255, 255, 0.2), -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.2), -2.6em 0em 0 0em rgba(255, 255, 255, 0.2), -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2);
  }
  50% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.2), 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2), 2.5em 0em 0 0em rgba(255, 255, 255, 0.5), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.7), 0em 2.5em 0 0em #ffffff, -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.2), -2.6em 0em 0 0em rgba(255, 255, 255, 0.2), -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2);
  }
  62.5% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.2), 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2), 2.5em 0em 0 0em rgba(255, 255, 255, 0.2), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.5), 0em 2.5em 0 0em rgba(255, 255, 255, 0.7), -1.8em 1.8em 0 0em #ffffff, -2.6em 0em 0 0em rgba(255, 255, 255, 0.2), -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2);
  }
  75% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.2), 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2), 2.5em 0em 0 0em rgba(255, 255, 255, 0.2), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.2), 0em 2.5em 0 0em rgba(255, 255, 255, 0.5), -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.7), -2.6em 0em 0 0em #ffffff, -1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2);
  }
  87.5% {
    box-shadow: 0em -2.6em 0em 0em rgba(255, 255, 255, 0.2), 1.8em -1.8em 0 0em rgba(255, 255, 255, 0.2), 2.5em 0em 0 0em rgba(255, 255, 255, 0.2), 1.75em 1.75em 0 0em rgba(255, 255, 255, 0.2), 0em 2.5em 0 0em rgba(255, 255, 255, 0.2), -1.8em 1.8em 0 0em rgba(255, 255, 255, 0.5), -2.6em 0em 0 0em rgba(255, 255, 255, 0.7), -1.8em -1.8em 0 0em #ffffff;
  }
}*/

@keyframes load5 {
    0%,
    100% {
        box-shadow: 0em -3em 0em 0em #ffffff, 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2), 3em 0em 0 0em rgba(255, 255, 255, 0.2), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), 0em 3em 0 0em rgba(255, 255, 255, 0.2), -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), -3em 0em 0 0em rgba(255, 255, 255, 0.5), -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.7);
    }
    12.5% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.7), 2.15em -2.15em 0 0em #ffffff, 3em 0em 0 0em rgba(255, 255, 255, 0.2), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), 0em 3em 0 0em rgba(255, 255, 255, 0.2), -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), -3em 0em 0 0em rgba(255, 255, 255, 0.2), -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.5);
    }
    25% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.5), 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.7), 3em 0em 0 0em #ffffff, 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), 0em 3em 0 0em rgba(255, 255, 255, 0.2), -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), -3em 0em 0 0em rgba(255, 255, 255, 0.2), -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2);
    }
    37.5% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.2), 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.5), 3em 0em 0 0em rgba(255, 255, 255, 0.7), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), 0em 3em 0 0em rgba(255, 255, 255, 0.2), -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), -3em 0em 0 0em rgba(255, 255, 255, 0.2), -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2);
    }
    50% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.2), 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2), 3em 0em 0 0em rgba(255, 255, 255, 0.5), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.7), 0em 3em 0 0em #ffffff, -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), -3em 0em 0 0em rgba(255, 255, 255, 0.2), -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2);
    }
    62.5% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.2), 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2), 3em 0em 0 0em rgba(255, 255, 255, 0.2), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.5), 0em 3em 0 0em rgba(255, 255, 255, 0.7), -2.15em 2.15em 0 0em #ffffff, -3em 0em 0 0em rgba(255, 255, 255, 0.2), -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2);
    }
    75% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.2), 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2), 3em 0em 0 0em rgba(255, 255, 255, 0.2), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), 0em 3em 0 0em rgba(255, 255, 255, 0.5), -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.7), -3em 0em 0 0em #ffffff, -2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2);
    }
    87.5% {
        box-shadow: 0em -3em 0em 0em rgba(255, 255, 255, 0.2), 2.15em -2.15em 0 0em rgba(255, 255, 255, 0.2), 3em 0em 0 0em rgba(255, 255, 255, 0.2), 2.15em 2.15em 0 0em rgba(255, 255, 255, 0.2), 0em 3em 0 0em rgba(255, 255, 255, 0.2), -2.15em 2.15em 0 0em rgba(255, 255, 255, 0.5), -3em 0em 0 0em rgba(255, 255, 255, 0.7), -2.15em -2.15em 0 0em #ffffff;
    }
}

.detection-btn {
    width: 10rem;
    margin-top: 2.6rem;
    font-size: 1.2rem;
    border-radius: 1rem;
    background: #fff;
}
.btn {
    display: inline-block;
    font-weight: 400;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    user-select: none;
    border: 1px solid transparent;
     padding: .25rem .5rem;
    line-height: 1.5;
    transition: color .15s ease-in-out, background-color .15s ease-in-out, border-color .15s ease-in-out, box-shadow .15s ease-in-out;
}
.btn:focus, .btn:hover {
    text-decoration: none;
}
.btn-outline-info {
    color: #17a2b8;
    /*background-color: transparent;
    background-image: none;*/
    border-color: #17a2b8;
}
.btn-outline-warning {
    color: #ffc107;
    /*background-color: transparent;
    background-image: none;*/
    border-color: #ffc107;
}
.btn-outline-info:hover {
    color: #fff;
    background-color: #17a2b8;
    border-color: #17a2b8;
}
.btn-outline-warning:hover {
    /* color: #1f2d3d; */
    color: #fff;
    background-color: #ffc107;
    border-color: #ffc107;
}
.btn-outline-danger {
    color: #dc3545;
    /*background-color: transparent;
    background-image: none;*/
    border-color: #dc3545;
}
.btn-outline-danger:hover {
    color: #fff;
    background-color: #dc3545;
    border-color: #dc3545;
}
.detection-detail {
    height: 20%;
    overflow-y: auto;
}

.detection-detail.actived {
    height: 40%;
}

.detection-detail ul {
    /*height:20px;*/
    /*overflow:hidden;*/
    padding: .5rem 1rem;
    /*transform: translateY(-100%);*/
    /*transition:transform .2s;*/
}

.detection-detail.actived ul {
    /*transform: translateY(0);*/
}

.detection-detail ul li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 1rem;
    line-height: 2rem;
}

.detection-detail ul li .badge {
    padding: .25em .6em;
    /*height:1.2rem;
    line-height: 1.2rem;*/
    font-size: .8rem;
}
.badge {
    display: inline-block;
    /*min-width: 1.1rem;
    min-height: 1.1rem;*/
    padding: .25em .4em;
    font-size: 75%;
    font-weight: 700;
    line-height: 1;
    text-align: center;
    white-space: nowrap;
    vertical-align: baseline;
    border-radius: .25rem;
    color: #fff!important;
}
.bg-success{
    background-color: #28a745!important;
}
.bg-danger {
    background-color: #dc3545!important;
}
.detection-result-detail {
    padding: 1rem;
    font-size: 1rem;
}

.detection-result-detail li {
    line-height: 1.6rem;
}

.detection-result-detail li i {
    color: #dc3545!important;
}

/*弹框*/
.modal.in .modal-dialog {
    -webkit-transform: translate(0, 50%);
    -ms-transform: translate(0, 50%);
    -o-transform: translate(0, 50%);
    transform: translate(0, 50%);
}
.bg-base {
    background-color: #40c8de!important;
    color: #fff;
}
.modal-header {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    padding: .5rem;
    border-bottom: 1px solid #e9ecef;
    border-top-left-radius: .3rem;
    border-top-right-radius: .3rem;
}
h4.modal-title{
    font-size:1.5rem;
}
```
### 完整JS代码 ###
```javascript
<script type="text/javascript">
    $(function() {
        $(document).on('click', '.detection-btn.uncheck', function() {
            startDetection(this);
            downCounter();
        });
        $(document).on('click', '.detection-btn.check', function() {
            pauseDetection(this);
        });
    });
    //安全检测
    
    //开始的样式
    var startDetection = function(_this) {
        $(".detection-detail ul").empty();
        $(".detection-btn").addClass("btn-outline-info");
        $(".detection-btn").removeClass("btn-outline-warning");
        $(".detection-btn").removeClass("btn-outline-danger");
        $("#counter").text(100);
        $(".detection-container").css("background-color", "#40c8de");
        //$(".content-wrapper.detection-wrapper .content-header").css("background-color", "#40c8de");
        $(".detection-container").addClass("active");
        $(".detection-container").removeClass("actived");
        $(".detection-content").addClass("active");
        $(".loader").addClass("active");
        $(_this).removeClass("uncheck");
        $(_this).addClass("check");
        $(_this).text("正在检测…");
    };
    //中止检测
    var pauseDetection = function(_this) {
        $(".detection-container").removeClass("active");
        $(".detection-content").removeClass("active");
        $(".loader").removeClass("active");
        $(_this).addClass("uncheck");
        $(_this).removeClass("check");
        $(_this).text("立即检测");
    };
    //检测结束
    var endDetection = function() {
        $(".detection-container").removeClass("active");
        $(".detection-container").addClass("actived");
        $(".detection-detail").addClass("actived");
        $(".detection-content").removeClass("active");
        $(".loader").removeClass("active");
        $(".detection-btn").addClass("uncheck");
        $(".detection-btn").removeClass("check");
        $(".detection-btn").text("立即检测");
    };
    //修改背景色
    var bgColor = function() {
        if($("#counter").text() >= 80) {
            $(".detection-container").css("background-color", "#40c8de");
            //$(".content-wrapper.detection-wrapper .content-header").css("background-color", "#40c8de");
            $(".detection-btn").addClass("btn-outline-info");
            $(".detection-btn").removeClass("btn-outline-warning");
            $(".detection-btn").removeClass("btn-outline-danger");
        } else if($("#counter").text() >= 60 & $("#counter").text() < 80) {
            $(".detection-container").css("background-color", "rgb(247, 207, 88)");
            //$(".content-wrapper.detection-wrapper .content-header").css("background-color", "rgb(247, 207, 88)");
            $(".detection-btn").removeClass("btn-outline-info");
            $(".detection-btn").addClass("btn-outline-warning");
            $(".detection-btn").removeClass("btn-outline-danger");
        } else {
            $(".detection-container").css("background-color", "rgb(228, 86, 100)");
            //$(".content-wrapper.detection-wrapper .content-header").css("background-color", "rgb(228, 86, 100)");
            $(".detection-btn").removeClass("btn-outline-info");
            $(".detection-btn").removeClass("btn-outline-warning");
            $(".detection-btn").addClass("btn-outline-danger");
        }
    }
    var downCounter = function() {
        var startVal = 100; //开始分数
        var time = 1000;//检测间隔时间
        var liList = [{
                "dataName": "20",
                "dataType": "0",//失败
                "dataText": "检测项一"
            },
            {
                "dataName": "10",
                "dataType": "0",
                "dataText": "检测项二"
            },
            {
                "dataName": "5",
                "dataType": "1",//成功
                "dataText": "检测项三"
            },
            {
                "dataName": "15",
                "dataType": "0",
                "dataText": "检测项四"
            },
            {
                "dataName": "20",
                "dataType": "0",
                "dataText": "检测项五"
            },
            {
                "dataName": "5",
                "dataType": "0",
                "dataText": "检测项六"
            },
            {
                "dataName": "15",
                "dataType": "0",
                "dataText": "检测项七"
            },
            {
                "dataName": "10",
                "dataType": "1",
                "dataText": "检测项八"
            },
        ];
        var index = 0;
        var htmlArray = [];
        for(var i = 0; i < liList.length; i++) {
            var html = '';
            if(liList[i].dataType == 1) {
                html += '<li data-name="' + liList[i].dataName + '" data-type="' + liList[i].dataType + '"><span>' + liList[i].dataText + '</span><span class="badge bg-success">成功</span></li>';
            } else {
                html += '<li data-name="' + liList[i].dataName + '" data-type="' + liList[i].dataType + '" data-toggle="modal" data-target="#detectionModal"><span>' + liList[i].dataText + '</span><span class="badge bg-danger">失败</span></li>';
            }
            htmlArray.push(html);
        }
        var timer = setInterval(function() {
            index++;
            $(".detection-detail ul").prepend(htmlArray[index - 1]);
            var score = liList[index - 1].dataName;
            if(liList[index - 1].dataType == 0) {
                startVal = startVal - score;
            }
            $('#counter').text(startVal);
            bgColor();
            //检测完成后
            if(index == htmlArray.length) {
                clearInterval(timer);
                endDetection();
            }
            //中止的时候
            if($(".detection-btn").hasClass("uncheck")) {
                clearInterval(timer);
            }
        }, time)
    }
    //安全检测END
</script>
```